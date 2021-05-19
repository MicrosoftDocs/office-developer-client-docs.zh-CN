---
title: 将可管理性Microsoft 365 应用版与一键式安装程序集成
manager: lindalu
ms.date: 09/28/2020
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何将Microsoft 365 应用版即点即用安装程序与软件管理解决方案集成。
ms.openlocfilehash: eccd634f7906acf25b521ed2deb456ca914f37da
ms.sourcegitcommit: c8c51bd3f51c0a59fe44c014c8e56f1ba7c7aa03
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48297312"
---
# <a name="integrating-manageability-applications-with-microsoft-365-apps-click-to-run-installer"></a>将可管理性Microsoft 365 应用版与一键式安装程序集成

了解如何将Microsoft 365 应用版即点即用安装程序与软件管理解决方案集成。
  
该Microsoft 365 应用版即点即用安装程序提供了 COM 接口，使 IT 专业人员和软件管理解决方案可以编程方式控制更新管理。 此接口提供除 Office 工具提供的其他管理功能。
  
> [!NOTE]
> 本文适用于Office即点即用安装程序的应用。 
  
## <a name="integrating-with-the-click-to-run"></a>与"单击运行"集成

为了使用此接口，可管理性应用程序调用 COM 接口并调用直接与即点即用安装服务通信的公开的 API。 
  
> [!NOTE]
> The Office Click-to-Run installer can be run from the command-line with parameters that can control the behavior， as documented in [Office Deployment Tool for Click-to-Run](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool). 
  
**下面是 COM 接口的概念图**

![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在&quot;单击到运行&quot;安装程序Office COM 接口的关系图")
  
即Microsoft 365 应用版即点即用安装程序实现基于 COM 的接口，**即** 注册到 CLSID CLSID_UpdateNotifyObject。
  
可以按如下方式调用此接口：
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

只有在呼叫者以提升的权限运行时，调用才能成功，因为即点即用安装程序必须使用提升的权限运行。
  
**IUpdateNotify** COM 接口公开了三个异步函数，这些函数负责验证命令和参数以及使用即点即用安装服务计划执行。 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

前一个方法 **Status** 可用于获取有关上次执行的命令的状态或当前执行的命令的状态的信息 (例如成功、失败、详细的错误代码) 。
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

即点即用安装服务在其生命周期内可能存在四种状态，在此期间可能会调用 **IUpdateNotify** 方法;正在重启、空闲、正在下载和应用。 
  
**下面是 COM 接口状态机图**

![COM 接口的状态图。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口的状态图")
  
> [!NOTE]
> **正在** 重新启动：当计算机启动时，有一段时间即点即用安装程序服务不可用。 重新启动后成功调用 Status 方法将返回eUPDATE_UNKNOWN。 
  
**空闲：** 当 Click-to-Run 安装程序处于空闲状态时，你可以调用： 
  
- **应用**：安装之前下载的内容。
    
- **Cancel**： Returns  `0x800000e` ， "A method was called at an unexpected time."
    
- **下载**：将新内容下载到客户端以稍后安装。
    
- **状态**：返回上一个已完成操作的结果，或返回一条错误消息（如果操作以失败结束）。 如果之前没有操作 **，Status** 将返回  `eUPDATE_UNKNOWN` 。
    
**正在下载：** 当 Click-to-Run 安装程序位于下载状态时，你可以调用： 
  
- **Apply**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."
    
- **取消**：停止下载并删除部分下载的内容。
    
- **下载**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time." 
    
- **状态****：DOWNLOAD_WIP，** 以指示下载工作正在进行。 
    
**应用：** 当"单击运行"安装程序正在安装之前下载的内容时： 
  
- **Apply**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time."
    
- **Cancel**：返回  `0x800000e` ，无法取消 Apply 操作。
    
- **下载**：返回一 **个 HRESULT，** 值为  `0x800000e` "A method was called at an unexpected time." 
    
- **Status**： returns **APPLY_WIP** to indicate that apply work is in progress. 
    
> [!NOTE]
> 由于 OfficeC2RCOM 是一个 COM+ 服务且是动态加载的，因此每次在此类上调用方法时都需要调用 **CoCreateInstance，** 以确保获得预期的结果。 COM+ 服务将在必要时处理创建新实例。 当首次调用其中一个方法时，COM+ 将加载 **IUpdateNotify** 对象，并在其实例之一dllhost.exe它。 新对象在空闲时将保持活动状态大约 3 分钟。 如果最后一次调用的三分钟内进行了后续调用， **则 IUpdateNotify** 对象将保持加载状态，并且不会创建一个新实例。 如果在三分钟内未进行调用，将卸载 IUpdateNotify 对象，并且将在下一次调用时创建一个新的 **IUpdateNotify** 对象。 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a>Click-to-Run installer COM API 参考指南

在下面的 API 参考文档中：
  
- 参数采用键/值对格式，用空格分隔。
    
- 参数不区分大小写。
    
- 有一 [个包含可用文档](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) 的参数列表。 
    
- 现在包含 IUpdateNotify2 接口的摘要。
    
### <a name="apply"></a>应用

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_ **：true** 表示更新过程中安装状态（包括错误）; **false** 以在更新过程中隐藏安装状态（包括错误）。 默认值为 **false**。
    
-  _forceappshutdown_：如果为 **true，Office** 应用在触发 **Apply** 操作时立即关闭;**如果** 任何应用程序正在运行，Office false。 默认值为 **false**。 有关详细信息 [，](#bk_ApplyRemark) 请参阅"说明"。 
    
  如果在Office **应用** 操作时应用程序正在运行，**则 Apply** 操作通常会失败。 传递到  `forceappshutdown=true` **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭应用程序并应用更新。 在这种情况下，用户可能会遇到数据丢失问题。 
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |调用方没有使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |目前不允许操作。 有关详细信息 [，](#bk_ApplyRemark) 请参阅"说明"。  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a>备注

- 如果在Office **应用** 操作时应用程序正在运行，**则 Apply** 操作将失败。 传递到 `forceappshutdown=true` **Apply** 方法将导致 **OfficeClickToRun** 服务立即关闭Office应用程序并应用更新的任何应用程序。 用户可能会遇到数据，因为系统不会提示他们保存对打开的文档所做的更改。 
    
- 只有当 COM 状态为以下状态之一时，才能触发此操作： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果在之前未下载内容的情况下调用 **Apply** 方法， **则 Apply** 方法将报告 **Succeeded，** 因为它未检测到任何要应用并且成功完成 **了应用** 过程。 
    
### <a name="cancel"></a>取消

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|S_OK  <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|E_ILLEGAL_METHOD_CALL  <br/> |目前不允许操作。 有关详细信息 [，请参阅](#bk_CancelRemarks) "备注"部分  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a>备注

- 此方法只能在 COM 状态 ID 为 eDOWNLOAD_WIP 时 **触发**。 它将尝试取消当前下载操作。 COM 状态将更改为 eDOWNLOAD_CANCELLING **并最终更改为****eDOWNLOAD_CANCELED**。 COM 状态将在任何其他 **E_ILLEGAL_METHOD_CALL** 触发时返回该状态。 
    
### <a name="download"></a>下载

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_ **：true** 表示更新过程中安装状态（包括错误）; **false** 以在更新过程中隐藏安装状态（包括错误）。 默认值为 **false**。
    
-  _updatebaseurl_：备用下载源的 URL。
    
-  _updatetoversion_：要更新Office的版本。 如果要更新到比当前安装的版本更旧的版本，请定义此参数。
    
-  _downloadsource_：BITS 管理器中自定义 **的 IBackgroundCopyManager** (CLSID) 。 
    
-  _contentid：_ 标识要通过自定义 BITS 管理器从内容服务器下载的内容。 此值通过 BITS 接口传递进行解释。
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |调用方没有使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |目前不允许操作。 有关详细信息 [，](#bk_DownloadRemark) 请参阅"说明"。  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a>备注

- 必须将  _downloadsource 和_  _contentid 指定为_ 对。 如果没有，则 **Download** 方法 **将返回E_INVALIDARG** 错误。 
    
- 如果 _提供了 downloadsource、contentid_ 和 _updatebaseurl，__则 updatebaseurl_ 将被忽略。  
    
- 只有当 COM 状态为以下状态之一时，才能触发此操作： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果调用 **Apply** 方法时未下载之前的内容， **则 Apply** 方法将报告 **Succeeded，** 因为它未检测到应用任何内容，并且成功完成 **了应用** 过程。 
    
#### <a name="examples"></a>示例

- 若要从自定义 BITS 管理器下载内容：调用 **download ()** 函数，以传递以下参数： 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- 若要从网站下载Office 内容分发网络 (CDN) ：调用 **download ()** 函数，而不指定 _downloadsource、contentid_ 或 _updatebaseurl_ 参数。 
    
- 若要从自定义位置下载内容：调用 **传递 ()** 参数的 download () 函数： 
    
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
| _pUpdateStatusReport_ <br/> |指向结构UPDATE_STATUS_REPORT指针。  <br/> |
   
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |**Status** 方法始终返回此结果。 检查  `UPDATE_STATUS_RESULT` 结构以检查当前操作的状态。  <br/> |
   
#### <a name="remarks"></a>备注

- 的状态字段  `UPDATE_STATUS_REPORT` 包含当前操作的状态。 返回以下状态值之一： 
    
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

- 如果最后一个命令导致错误，则 的错误字段  `UPDATE_STATUS_REPORT` 包含有关错误的详细信息。 Status 方法返回两种类型的 **错误** 代码。 
    
- 如果错误小于  `UPDATE_ERROR_CODE::eUNKNOWN` ，则错误是以下预定义的错误代码之一：
    
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

  如果返回错误代码大于失败函数调用的 `UPDATE_ERROR_CODE::eUNKNOWN` **HRESULT。** 从 的错误字段中返回的值中提取 HRESULT  `UPDATE_ERROR_CODE::eUNKNOWN`  `UPDATE_STATUS_REPORT` 减去 。
    
  通过检查 **IUpdateNotify 类型库中嵌入的 IUpdateNotify** 类型库，可以查看状态和错误值的完整OfficeC2RCom.dll。 
    
- contentid 字段用于在 **启动 Download** 后调用 **Status，** 并返回传递到 Download 调用的 **contentid。** 最佳做法是在调用 **Status** 方法之前将此字段初始化为 **null，** 然后在 **返回 Status** 后检查该值。 如果值仍为 **null，** 则意味着没有要返回的 contentid。 如果值不为 **null，** 则需要通过调用 **SysFreeString** () 释放它。 下面是在下载后如何调用 **Status** 的代码 **段**。
    
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

从版本 [16.0.8208.6352] 我们添加了一个新的 **IUpdateNotify2** 接口。 
  
- CLSID_UpdateNotifyObject2，{52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}
    
- 此接口还托管了原始 IUpdateNotify 接口以提供向后兼容性。 这意味着如果使用此接口，则有权访问 **UpdateNotifyObject** 接口中提供的所有方法。 
    
- 添加到 IUpdateNotify2 的新方法：
    
  - **HRESULT** GetBlockingApps ([out] BSTR \* AppsList) 。 获取阻止应用的更新列表。 此调用将返回正在运行的Office应用，这些应用将阻止更新过程继续。 
    
  - **HRESULT** GetOfficeDeploymentData ([in] int dataType， [in] **LPCWSTR** pcwszName， [out] BSTR * OfficeData) 。 获取Office数据。 
    
- 如果要使用新方法，需要确保：
    
  - 你的 C2R 版本比上述内部版本更新 (六月 \> 分叉版本) 。
    
  - 使用 UpdateNotifyObject2，而不是 **UpdateNotifyObject** 调用 **CoCreateInstance**。
    
如果不使用任何新方法，则无需更改任何内容。 所有现有方法将采用与以前完全相同的方式工作。
  
## <a name="implementing-the-bits-interface"></a>实现 BITS 接口

BACKGROUND [Intelligent Transfer Service](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) (BITS) 是 Microsoft 提供的一项在客户端和服务器之间传输文件的服务。 BITS 是即点即Office安装程序可用于下载内容的通道之一。 默认情况下，Microsoft 365 应用版即点即用安装程序使用 BITS Windows的内置实现来下载来自 CDN 的内容。 
  
通过向 **IUpdateNotify** 接口的 **()** 方法提供自定义 BITS 实现，您的可管理性软件可以控制客户端下载内容的地方和方式。 自定义 BITS 接口在提供自定义内容分发通道（而非即点即用内置通道，如 CDN、IIS 服务器或文件共享）时很有用。 
  
自定义 BITS 接口与 C2R 服务Office的最低要求是：
  
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

- 对于  `Addfile` 和  `AddFileWithRanges` 函数，远程 URL 的格式如下： 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - cmbits 是硬编码的，代表自定义 BITS。
    
  -  _\<contentid\>_ 是 Download () **的**_contentid_ 参数。 
    
  -  _\<relative path to target file\>_ 提供要下载的文件的位置和文件名。 
    
    例如，如果你向 Download () 方法提供了 的 _contentid，_ 并且 Office C2R 想要下载版本的 cab 文件（如文件），它将使用以下内容调用 `f732af58-5d86-4299-abe9-7595c35136ef`  `v32.cab` **AddFile** `RemoteUrl` () ：
    
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
## <a name="automating-content-staging"></a>自动执行内容暂存

IT 管理员可以选择启用桌面客户端，以在直接从 CDN时自动接收更新，也可以选择使用 Office 部署工具或 Microsoft Endpoint Configuration Manager 控制更新频道提供的更新的部署。
  
该服务支持管理工具在更新可用时识别并自动下载内容。
  
**下图概述了如何下载自定义映像**

![在 Office 单击即运行安装程序上使用 COM 接口的图。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "在&quot;单击到运行&quot;安装程序Office COM 接口的关系图")
  
### <a name="overview-of-downloading-a-custom-image"></a>下载自定义映像概述
  
在上图中，可以看到新Microsoft 365 应用版图像可用于CDN。 除了Microsoft 365 应用版映像外，API 也可用，该 API 具有启用可管理性软件以直接创建自定义映像所需的信息，无需使用 Office 部署工具。

企业将其 WSUS 配置为同步Microsoft 365 应用版更新。 这些更新不包含实际的图像有效负载，但允许可管理性软件识别新内容何时可用。 然后，可管理性软件可以读取 Microsoft 365 应用版 Update 元数据，以了解此更新Office版本。

如果更新适用，可管理性软件可以使用 CDN 内容和文件列表创建自定义映像，并存储到配置为使用的文件共享位置。
  
### <a name="using-the-microsoft-365-apps-file-list-api"></a>使用Microsoft 365 应用版列表 API

文件Microsoft 365 应用版 API 用于检索特定文件更新所需的Microsoft 365 应用版名称。

HTTP 请求

获取 https://config.office.com/api/filelist

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

可选的查询参数

|**名称**|**说明**|
|:-----|:-----|
| channel <br/>| 指定频道名称  <br/> 可选 – 默认为"SemiAnnual" <br/> 支持的值 https://docs.microsoft.com/DeployOffice/office-deployment-tool-configuration-options#channel-attribute-part-of-add-element |
| version <br/>| 指定更新版本 <br/> 可选 – 默认为可用于指定频道的最新版本 |
| arch <br/>| 指定客户端体系结构 <br/> 可选 – 默认为"x64" <br/> 支持的值：x64、x86 |
| 一个 <br/>| 指定要包含的语言文件 <br/> 可选 – 默认为无 <br/> 若要指定多种语言，请包含每种语言的一个盖查询参数 <br/> 使用语言标识符格式，例如 "en-us"、"fr-fr" |
| alllanguages <br/>| 指定包括所有语言文件 <br/> 可选 – 默认为 false |

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。

若要创建映像，请按照以下步骤操作：
1.  调用 API，为感兴趣的更新的通道、版本和体系结构提供适当的查询参数。
注意：属性为"lcid"："0"的 File 对象是中性语言文件，必须包含在映像中。
2.  通过访问文件对象并复制 CDN 文件来构造 CDN 的本地映像，同时创建由为每个文件对象定义的"relativePath"属性指定的文件夹结构。

以下示例检索 64bit 的当前频道和版本 16.0.4229.1004 的文件列表，并包括法语和英语语言文件：

```http
Get https://config.office.com/api/filelist?Channel=Current&Version=16.0.4229.1004&Arch=x64&Lid=fr-fr&Lid=en-US
```

### <a name="hash-verification-of-dat-files"></a>.dat 文件的哈希验证

映像创建工具可能会通过将计算哈希值与提供的与每个 .dat 文件关联的哈希值进行比较来验证下载的 .dat 文件的完整性。 下面是指定 hashLocation 和 hashAlgorithm 值的文件对象的示例：
  
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

- **hashLocation** 属性指定包含哈希值的.cab文件的相对路径位置。 通过连接 URL + relativePath + hashLocation 构造哈希文件位置。 在下面的示例中，stream.x64.bg-bg.hash 位置为： 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- **hashAlgorithm** 属性指定使用的哈希算法。 
    
  若要验证 stream.x64.bg-bg.dat 文件的完整性，请打开 stream.x64.bg-bg.hash 并读取 HASH 值，它是哈希文件的第一行文本。 将此与使用指定的哈希算法 (哈希值值进行比较) 验证下载的 .dat 文件的完整性。
    
  以下示例显示用于C#哈希的代码。
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="microsoft-365-apps-updates"></a>Microsoft 365 应用版更新

所有Microsoft 365 应用版更新都发布到[Microsoft 更新目录](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。
  
Microsoft 365 应用版更新使可管理性软件Microsoft 365 应用版处理更新的方式与任何其他 WU 更新非常类似，只有一个例外;客户端更新不包含实际有效负载。 该Microsoft 365 应用版更新不应安装在任何客户端上，而应该用于使用可管理性软件触发工作流，将安装命令替换为上述基于 COM 的安装机制。

**下图显示了客户端更新Office 365的图表。**

![O365PP 客户端更新的工作流图。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流关系图")
  
发布的Microsoft 365 应用版更新包括有关更新的元数据。 此元数据包括一个称为 MoreInfoUrl 的参数，该参数可用于将 API 调用派生到特定更新的文件列表 API。

在下面的示例中，文件列表 API 嵌入到 MoreInfoURL 中，以"ServicePath="开头。

http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.12527.21104&Branch=Insiders&Arch=64&XMLVer=1.6&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml& ServicePath=https://config.office.com/api/filelist?Channel=Insiders&Version=16.0.12527.21104&Arch=64&AllLanguages=True
  
### <a name="additional-metadata-for-automating-content-staging"></a>用于自动执行内容暂存的其他元数据

**版本历史记录 API**
  
发布Microsoft 365 应用版 API 用于检索发布到该版本的每个更新的详细信息CDN通道名称和其他通道属性。

HTTP 请求

```http
GET https://config.office.com/api/filelist/channels 
```

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。

**SKUs API**
  
SKUs API 返回的信息可用于确定哪些产品可用于从 Office CDN部署和维护，以及每种产品的各种选项。

HTTP 请求

```http
GET https://config.office.com/api/filelist/skus 
```

请勿提供此方法的请求正文。

调用此 API 不需要任何权限。

HTTP 响应

如果成功，此方法在响应正文中返回 200 OK 响应代码和 file 对象集合。
