---
title: 将可管理性应用程序与 Microsoft 365 应用程序集成即点即用安装程序
manager: lindalu
ms.date: 09/28/2020
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何将 Microsoft 365 应用即点即用安装程序与软件管理解决方案集成。
ms.openlocfilehash: eccd634f7906acf25b521ed2deb456ca914f37da
ms.sourcegitcommit: c8c51bd3f51c0a59fe44c014c8e56f1ba7c7aa03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48297312"
---
# <a name="integrating-manageability-applications-with-microsoft-365-apps-click-to-run-installer"></a>将可管理性应用程序与 Microsoft 365 应用程序集成即点即用安装程序

了解如何将 Microsoft 365 应用即点即用安装程序与软件管理解决方案集成。
  
Microsoft 365 应用程序即点即用安装程序提供了一个 COM 接口，使 IT 专业人员和软件管理解决方案可以编程方式控制更新管理。 此接口提供了 Office 部署工具所提供功能之外的其他管理功能。
  
> [!NOTE]
> 本文适用于使用即点即用安装程序的 Office 应用程序。 
  
## <a name="integrating-with-the-click-to-run"></a>与即点即用集成

若要使用此接口，可管理性应用程序将调用 COM 接口，并调用与即点即用安装服务直接通信的公开 Api。 
  
> [!NOTE]
> 可以通过命令行运行 Office 即点即用安装程序，这些参数可以控制针对即点即用的 [Office 部署工具](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool)中所述的行为。 
  
**以下是 COM 接口的概念图**

![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在 Office 即点即用安装程序上使用 COM 接口的关系图")
  
Microsoft 365 应用程序即点即用安装程序实现基于 COM 的接口， **IUpdateNotify** 注册到 CLSID **CLSID_UpdateNotifyObject**。
  
可以按如下方式调用此接口：
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

仅当呼叫者在提升的权限下运行时，调用才会成功，因为必须使用提升的权限运行即点即用安装程序。
  
**IUpdateNotify** COM 接口公开三个异步功能，负责验证命令和参数，并使用即点即用安装服务执行计划的运行。 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

" **状态**" 方法可用于获取有关上次执行的命令状态的信息，或当前正在执行的命令的状态 (即 "成功"、"失败"、"详细" 错误代码) 。
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

在其生命周期中，即点即用安装服务可能处于运行状态的四种状态，在此期间可以调用 **IUpdateNotify** 方法;重新启动、空闲、下载和应用。 
  
**以下是 COM 接口状态机关系图**

![COM 接口的状态图。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口的状态图")
  
> [!NOTE]
> **重新启动**：当计算机启动时，即点即用安装程序服务不可用时的一段时间。 重新启动后，对 Status 方法的成功调用将返回 eUPDATE_UNKNOWN。 
  
**空闲：** 当即点即用安装程序处于空闲状态时，您可以调用： 
  
- **应用**：安装以前下载的内容。
    
- **取消**：返回  `0x800000e` "在意外的时间调用方法"。
    
- **下载**：将新内容下载到客户端，以供以后安装。
    
- **Status**：返回上次完成的操作的结果，如果操作在失败时结束，则返回错误消息。 如果没有上一个操作， **状态** 将返回  `eUPDATE_UNKNOWN` 。
    
**下载：** 当即点即用安装程序处于下载状态时，您可以调用： 
  
- **应用**：返回值**HRESULT**为 `0x800000e` "在意外的时间调用了某个方法的 HRESULT"。
    
- **取消**：停止下载并删除部分下载的内容。
    
- **下载**：返回值**HRESULT**为 `0x800000e` "在意外时间调用方法" 的 HRESULT。 
    
- **Status**：返回 **DOWNLOAD_WIP** 以指示正在进行下载工作。 
    
**应用：** 当即点即用安装程序安装之前的下载内容的过程中： 
  
- **应用**：返回值**HRESULT**为 `0x800000e` "在意外的时间调用了某个方法的 HRESULT"。
    
- **取消**：返回  `0x800000e` ，无法取消应用操作。
    
- **下载**：返回值**HRESULT**为 `0x800000e` "在意外时间调用方法" 的 HRESULT。 
    
- **Status**：返回 **APPLY_WIP** 以指示应用工作正在进行中。 
    
> [!NOTE]
> 由于 OfficeC2RCOM 是 COM + 服务并且已动态加载，因此您需要在每次调用此类上的方法时调用 **CoCreateInstance** ，以确保获得预期的结果。 如果需要，COM + 服务将处理创建新实例的情况。 当首次调用其中一种方法时，COM + 将加载 **IUpdateNotify** 对象并在其中一个 dllhost.exe 实例中运行它。 新对象将保持活动状态大约3分钟，并处于空闲状态。 如果在最后一次呼叫的三分钟内进行后续调用，则 **IUpdateNotify** 对象将保持加载，并且不会创建新的实例。 如果在三分钟内未进行任何调用，则将卸载 IUpdateNotify 对象，并在下一次调用时创建一个新的 **IUpdateNotify** 对象。 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a>即点即用安装程序 COM API 参考指南

在下面的 API 参考文档中：
  
- 参数的键/值对格式由空格分隔。
    
- 参数不区分大小写。
    
- 有可用的带有文档 [的参数的列表](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) 。 
    
- IUpdateNotify2 接口摘要现已包括在内。
    
### <a name="apply"></a>应用

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_： **true** 以在更新过程中显示安装状态（包括错误）; **如果为 false** ，则在更新过程中隐藏安装状态，包括错误。 默认值为 **false**。
    
-  _forceappshutdown_： **True** 以强制 Office 应用程序在触发 **应用** 程序操作时立即关闭; **假** 如果有任何 Office 应用程序在运行时失败。 默认值为 **false**。 有关详细信息，请参阅 " [备注](#bk_ApplyRemark) "。 
    
  如果在触发 **应用** 操作时任何 Office 应用程序正在运行，则 **apply** 操作通常会失败。 传递  `forceappshutdown=true` 给 **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭应用程序并应用更新。 在这种情况下，用户可能会遇到数据丢失。 
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许执行操作。 有关详细信息，请参阅 " [备注](#bk_ApplyRemark) "。  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a>说明

- 如果在触发 **应用** 操作时任何 Office 应用程序正在运行，则 **应用** 操作将失败。 传递  `forceappshutdown=true` 给 **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭任何正在运行的 Office 应用程序并应用更新。 用户可能会遇到数据，因为不提示他们保存对打开文档所做的更改。。 
    
- 仅当 COM 状态为以下情况之一时，才能触发此操作： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果在不下载内容的情况下调用 **Apply** 方法，则 **Apply** 方法将报告 **成功** ，因为它检测到什么内容未成功应用并已完成 **应用** 过程。 
    
### <a name="cancel"></a>取消

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|S_OK  <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|E_ILLEGAL_METHOD_CALL  <br/> |此时不允许执行操作。 有关详细信息，请参阅 " [备注](#bk_CancelRemarks) " 部分  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a>说明

- 仅当 COM 状态 id **eDOWNLOAD_WIP**时，才能触发此方法。 它将尝试取消当前的下载操作。 COM 状态将更改为 " **eDOWNLOAD_CANCELLING** "，并最终更改为 " **eDOWNLOAD_CANCELED**"。 如果在任何其他时间触发，COM 状态将返回 **E_ILLEGAL_METHOD_CALL** 。 
    
### <a name="download"></a>下载

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_： **true** 以在更新过程中显示安装状态（包括错误）; **如果为 false** ，则在更新过程中隐藏安装状态，包括错误。 默认值为 **false**。
    
-  _updatebaseurl_：指向备用下载源的 URL。
    
-  _updatetoversion_：将 Office 更新到的版本。 如果要更新到比当前安装的版本更旧的版本，请定义此参数。
    
-  _downloadsource_：自定义 **IBACKGROUNDCOPYMANAGER** 实现 (BITS 管理器的 CLSID) 。 
    
-  _contentid_：标识要通过自定义的 BITS 管理器从内容服务器下载的内容。 此值通过 BITS 接口传递以用于解释。
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许执行操作。 有关详细信息，请参阅 " [备注](#bk_DownloadRemark) "。  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a>说明

- 必须将  _downloadsource_ 和  _contentid_ 指定为一对。 如果不是，则 **下载** 方法将返回一个 **E_INVALIDARG** 错误。 
    
- 如果提供了  _downloadsource_、  _contentid_和  _updatebaseurl_ ，则将忽略  _updatebaseurl_ 。 
    
- 仅当 COM 状态为以下情况之一时，才能触发此操作： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果在未下载内容的情况下调用 **apply** 方法，则 **Apply** 方法将报告 **成功** ，因为它检测到什么内容未成功应用并已完成 **应用** 过程。 
    
#### <a name="examples"></a>示例

- 若要从自定义的 BITS 管理器下载内容：调用 **下载 ( # B1 ** 函数传递以下参数： 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- 若要从 Office 内容传递网络 (CDN) 下载内容，请在未指定_downloadsource_、 _contentid_或_Updatebaseurl_参数的情况下调用**下载 ( # B3**函数。 
    
- 若要从自定义位置下载内容：调用 **下载 ( # B1 ** 函数传递以下参数： 
    
  ```cpp
  "updatebaseurl=yourcontentserverurl"
  ```

### <a name="status"></a>状态

```cpp
typdef struct _UPDATE_STATUS_REPORT
{
    UPDATE_STATUS status;
    UINT error;
    LPCWSTR contentid;
}UPDATE_STATUS_REPORT;
HRESULT status([out] _UPDATE_STATUS_REPORT& pUpdateStatusReport) // Get status of current action
```

#### <a name="parameters"></a>参数

|||
|:-----|:-----|
| _pUpdateStatusReport_ <br/> |指向 UPDATE_STATUS_REPORT 结构的指针。  <br/> |
   
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |**Status**方法始终返回此结果。 检查  `UPDATE_STATUS_RESULT` 当前操作的状态的结构。  <br/> |
   
#### <a name="remarks"></a>说明

- 的 "状态" 字段  `UPDATE_STATUS_REPORT` 包含当前操作的状态。 将返回以下状态值之一： 
    
  ```cpp
  typedef enum _UPDATE_STATUS
  {
  eUPDATE_UNKNOWN = 0,
  eDOWNLOAD_PENDING,
  eDOWNLOAD_WIP,
  eDOWNLOAD_CANCELLING,
  eDOWNLOAD_CANCELLED,
  eDOWNLOAD_FAILED,
  eDOWNLOAD_SUCCEEDED,
  eAPPLY_PENDING,
  eAPPLY_WIP,
  eAPPLY_SUCCEEDED,
  eAPPLY_FAILED,
  } UPDATE_STATUS;
  
  ```

- 如果最后一个命令导致错误，则中的 "错误" 字段  `UPDATE_STATUS_REPORT` 包含有关错误的详细信息。 **状态**方法返回两种类型的错误代码。 
    
- 如果错误小于，则此  `UPDATE_ERROR_CODE::eUNKNOWN` 错误为下列预定义的错误代码之一：
    
  ```cpp
  typedef enum _UPDATE_ERROR_CODE
  {
  eOK = 0,
  eFAILED_UNEXPECTED,
  eTRIGGER_DISABLED,
  ePIPELINE_IN_USE,
  eFAILED_STOP_C2RSERVICE,
  eFAILED_GET_CLIENTUPDATEFOLDER,
  eFAILED_LOCK_PACKAGE_TO_UPDATE,
  eFAILED_CREATE_STREAM_SESSION,
  eFAILED_PUBLISH_WORKING_CONFIGURATION,
  eFAILED_DOWNLOAD_UPGRADE_PACKAGE,
  eFAILED_APPLY_UPGRADE_PACKAGE,
  eFAILED_INITIALIZE_RSOD,
  eFAILED_PUBLISH_RSOD,
  // Keep this one as the last
  eUNKNOWN
  } UPDATE_ERROR_CODE;
  
  ```

  如果返回错误代码大于  `UPDATE_ERROR_CODE::eUNKNOWN` 为失败的函数调用的 **HRESULT** 。 `UPDATE_ERROR_CODE::eUNKNOWN`从的 "错误" 字段中返回的值中提取 HRESULT 减去 `UPDATE_STATUS_REPORT` 。
    
  可以通过检查嵌入在 OfficeC2RCom.dll 中的 **IUpdateNotify** 类型库来查看状态和错误值的完整列表。 
    
- Contentid 字段用于在开始**下载**后对**状态**的调用，并返回传入到**下载**调用的 contentid。 最佳做法是，在调用**status**方法之前将此字段初始化为**null** ，然后在返回**状态**后检查值。 如果该值仍为 **null**，则表示没有要返回的 contentid。 如果值不为 **null**，则需要通过调用 **SysFreeString ( # B1 **将其释放。 下面是一个代码段，介绍了如何在**下载**后调用**状态**。
    
  ```cpp
  std::wstring contentID;
  UPDATE_STATUS_REPORT statusReport;
  statusReport.status = eUPDATE_UNKNOWN;
  statusReport.error = eOK;
  statusReport.contentid = NULL;
  hr = p->Status(&statusReport);
  if (statusReport.contentid != NULL)
  {
  contentID = statusReport.contentid;
  SysFreeString(statusReport.contentid);
  }
  wprintf(L"ContentID: %s, Status: %d, LastError: %d", contentID.c_str(), statusReport.status, statusReport.error);
  
  ```

### <a name="summary-of-iupdatenotify2-interface"></a>IUpdateNotify2 接口摘要

自版本 [16.0.8208.6352] 我们添加了新的 **IUpdateNotify2** 接口。 
  
- CLSID_UpdateNotifyObject2，{52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}
    
- 此接口也托管原始 IUpdateNotify 接口，以提供向后兼容性。 这意味着，如果您使用此接口，则可以访问 **UpdateNotifyObject** 接口中提供的所有方法。 
    
- 添加到 IUpdateNotify2 的新方法：
    
  - **HRESULT** GetBlockingApps ( [out] BSTR \* AppsList) 。 获取更新阻止应用程序列表。 此调用将返回运行的 Office 应用程序，这将阻止更新过程继续进行。 
    
  - **HRESULT** GetOfficeDeploymentData ( [in] int dataType，[in] **一个 lpcwstr** pcwszName，[OUT] BSTR * OfficeData) 。 获取 Office 部署数据。 
    
- 如果要使用新的方法，您需要确保：
    
  - 您的 C2R 版本比上面的版本 (\> = 六月的分叉构建) 高。
    
  - 使用 UpdateNotifyObject2 而不是 **UpdateNotifyObject** 调用 **CoCreateInstance**。
    
如果不使用任何新方法，则无需更改任何内容。 所有现有方法的工作方式都与之前完全相同。
  
## <a name="implementing-the-bits-interface"></a>实现 BITS 接口

[后台智能传输服务](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) 是 Microsoft 提供的一种服务，用于在客户端和服务器之间传输文件。 BITS 是 Office 即点即用安装程序可用于下载内容的频道之一。 默认情况下，Microsoft 365 应用程序即点即用安装程序使用 Windows 内置的 BITS 实现从 CDN 下载内容。 
  
通过将自定义的 BITS 实现提供给**IUpdateNotify**接口的**下载 ( # B1**方法，您的可管理性软件可以控制客户端的下载内容的位置和方式。 当提供自定义内容分发通道（而不是即点即用的内置通道，如 CDN、IIS 服务器或文件共享）时，自定义的 BITS 接口非常有用。 
  
与 Office C2R service 配合使用的自定义位接口的最低要求是：
  
- 对于 **IBackgroundCopyManager**：
    
  ```cpp
  HRESULT _stdcall CreateJob(
                      [in] LPWSTR DisplayName, 
                      [in] BG_JOB_TYPE Type, 
                      [out] GUID* pJobId, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall GetJob(
                      [in] GUID* jobID, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall EnumJobs(
                      [in] unsigned long dwFlags, 
                      [out] IEnumBackgroundCopyJobs** ppenum)
  
  ```

- 对于 **IBackgroundCopyJob**：
    
  ```cpp
  HRESULT _stdcall AddFile(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName)
  HRESULT _stdcall Resume()
  HRESULT _stdcall Complete()
  HRESULT _stdcall Cancel();
  HRESULT _stdcall GetState([out] BG_JOB_STATE* pVal);
  HRESULT GetProgress( [out] BG_JOB_PROGRESS *pProgress);
  
  ```

- 对于 **IBackgroundCopyJob3**：
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- 对于  `Addfile` 和  `AddFileWithRanges` 函数，远程 URL 采用以下格式： 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - cmbits 是硬编码的，并代表自定义位。
    
  -  _\<contentid\>_ 是** ( # B1**方法的下载的_contentid_参数。 
    
  -  _\<relative path to target file\>_ 提供要下载的文件的位置和文件名。 
    
    例如，如果您已提供_contentid_ `f732af58-5d86-4299-abe9-7595c35136ef` ** ( # B1**方法的下载项的 contentid，而 Office C2R 想要下载版本 cab 文件（如 `v32.cab` File），它将调用**AddFile ( # B3** ，并提供以下 `RemoteUrl` 内容：
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- 对于 **IBackgroundCopyError**：
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- 对于 **IBackgroundCopyFile**：
    
  ```cpp
  HRESULT _stdcall GetLocalName([out] LPWSTR *ppName); 
  HRESULT _stdcall GetRemoteName([out] LPWSTR *ppName);
  
  ```
## <a name="automating-content-staging"></a>自动化内容暂存

IT 管理员可以选择让桌面客户端在可直接从 CDN 获取更新时自动接收更新，也可以选择使用 Office 部署工具或 Microsoft 终结点配置管理器来控制更新通道中可用的更新的部署。
  
服务支持管理工具在更新可用时识别和自动下载内容的功能。
  
**下图概述了下载自定义图像**

![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在 Office 即点即用安装程序上使用 COM 接口的关系图")
  
### <a name="overview-of-downloading-a-custom-image"></a>下载自定义图像概述
  
在上图中，您会看到新的 Microsoft 365 应用程序映像在 CDN 上可用。 除了 Microsoft 365 应用程序映像外，还提供了一个 API，其中包含启用可管理性软件以直接创建自定义图像以替换使用 Office 部署工具的需求所需的信息。

企业将其 WSUS 配置为同步 Microsoft 365 应用更新。 这些更新不包含实际图像负载，但允许可管理性软件识别新内容何时可用。 然后，可管理性软件可阅读 Microsoft 365 应用更新元数据，了解更新适用于什么 Office 版本。

如果更新适用，可管理性软件可以使用 CDN 内容和文件列表来创建自定义图像，并将其存储在配置为使用的文件共享位置上。
  
### <a name="using-the-microsoft-365-apps-file-list-api"></a>使用 Microsoft 365 应用程序文件列表 API

Microsoft 365 应用程序文件列表 API 用于检索特定 Microsoft 365 应用程序更新所需的文件的名称。

HTTP 请求

获取 https://config.office.com/api/filelist

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

可选的查询参数

|**名称**|**说明**|
|:-----|:-----|
| 频道 <br/>| 指定通道名称  <br/> 可选–默认为 "半年" <br/> 支持的值 https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element |
| version <br/>| 指定更新版本 <br/> 可选–默认为可用于指定通道的最新版本 |
| 弧 <br/>| 指定客户端体系结构 <br/> 可选–默认为 "x64" <br/> 支持的值： x64、x86 |
| 盖子 <br/>| 指定要包含的语言文件 <br/> 可选–默认值为无 <br/> 若要指定多种语言，请为每种语言包含一个盖子查询参数 <br/> 使用语言标识符格式（ex）。 ' en-us '，' fr-fr ' |
| alllanguages <br/>| 指定包含所有语言文件 <br/> 可选–默认值为 false |

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。

若要创建图像，请按照以下步骤操作：
1.  调用 API，为您感兴趣的更新的通道、版本和体系结构提供相应的查询参数。
注意：属性为 "lcid" 的 File 对象为 "lcid"： "0" 为中性语言文件，必须包含在映像中。
2.  通过循环访问文件对象和复制 CDN 文件来构造 CDN 的本地映像，同时创建由为每个 file 对象定义的 "relativePath" 属性指定的文件夹结构。

下面的示例检索当前频道的文件列表和64位版本的16.0.4229.1004，并包含法语和英语语言文件：

```http
Get https://config.office.com/api/filelist?Channel=Current&Version=16.0.4229.1004&Arch=x64&Lid=fr-fr&Lid=en-US
```

### <a name="hash-verification-of-dat-files"></a>.Dat 文件的哈希验证

通过将计算的哈希值与与每个 .dat 文件相关联的提供的哈希值相比较，图像创建工具可以验证下载的 .dat 文件的完整性。 以下是一个 file 对象的示例，该对象指定 hashLocation 和 hashAlgorithm 值：
  
```xml
{
  "url": "https://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114/office/data/16.0.1234.1001/stream.x64.x-none.dat",
  "name": "stream.x64.x-none.dat",
  "relativePath": "/office/data/16.0.1234.1001/",
  "hashLocation": "s640.cab/stream.x64.x-none.hash",
  "hashAlgorithm": "Sha256",
  "lcid": "0"
},
```

- **HashLocation**属性指定包含哈希值的 .cab 文件的相对路径位置。 通过串联 URL + relativePath + hashLocation 构造哈希文件位置。 在下面的示例中，stream.x64.bg 的哈希位置将为： 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- **HashAlgorithm**属性指定使用哪种哈希算法。 
    
  若要验证 stream.x64.bg-bg 文件的完整性，请打开 stream.x64.bg-bg. 哈希，并读取哈希值，该值是哈希文件中的第一行文本。 将此值与计算的哈希值进行比较， (使用指定的哈希算法) 验证下载的 .dat 文件的完整性。
    
  下面的示例演示用于读取哈希的 c # 代码。
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="microsoft-365-apps-updates"></a>Microsoft 365 应用更新

所有 Microsoft 365 应用更新都将发布到 [Microsoft Update 目录](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。
  
Microsoft 365 Apps Updates 使可管理性软件能够以与任何其他 WU 更新（只是一个例外）相似的方式来处理 Microsoft 365 应用更新。客户端更新不包含实际有效负载。 Microsoft 365 应用程序更新不应安装在任何客户端上，而是使用可管理性软件将安装命令替换为上面所示的基于 COM 的安装机制，从而触发工作流。

**下图显示了 Office 365 客户端更新工作流的关系图。**

![O365PP 客户端更新的工作流图。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流图表")
  
发布的每个 Microsoft 365 应用更新都包含有关更新的元数据。 此元数据包含一个名为 MoreInfoUrl 的参数，可用于为该特定更新派生对文件列表 API 的 API 调用。

在下面的示例中，文件列表 API 嵌入在 MoreInfoURL 中，并以 "ServicePath =" 开头。

http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath =https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True
  
### <a name="additional-metadata-for-automating-content-staging"></a>用于自动执行内容暂存的其他元数据

**发布历史记录 API**
  
Microsoft 365 应用版本历史记录 API 用于检索与频道名称和其他通道属性一起发布到 CDN 的每个更新的详细信息。

HTTP 请求

```http
GET https://config.office.com/api/filelist/channels 
```

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。

**Sku API**
  
Sku API 返回的信息可用于确定哪些产品可用于从 Office CDN 中进行部署和服务，以及每个产品的各种选项。

HTTP 请求

```http
GET https://config.office.com/api/filelist/skus 
```

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。
