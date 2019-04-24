---
title: 将可管理性应用程序与 Office 365 即点即用安装程序集成
manager: kelbow
ms.date: 10/22/2017
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何将 Office 365 即点即用安装程序与软件管理解决方案集成。
ms.openlocfilehash: cdcdde0618e2b96ce997ba5e263f75d85c21fd11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318337"
---
# <a name="integrating-manageability-applications-with-office-365-click-to-run-installer"></a>将可管理性应用程序与 Office 365 即点即用安装程序集成

了解如何将 Office 365 即点即用安装程序与软件管理解决方案集成。
  
Office 365 即点即用安装程序提供一个 COM 接口, 允许 IT 专业人员和软件管理解决方案以编程方式控制更新管理。 此接口提供了 Office 部署工具所提供功能之外的其他管理功能。
  
> [!NOTE]
> 本文适用于 office 2016 及更高版本 (office 365)。 
  
## <a name="integrating-with-the-click-to-run"></a>与即点即用集成

若要使用此接口, 可管理性应用程序将调用 COM 接口, 并调用与即点即用安装服务直接通信的公开 api。 
  
> [!NOTE]
> 可以通过命令行运行 office 即点即用安装程序, 这些参数可以控制针对即点即用的[Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)中所述的行为。 
  
**以下是 COM 接口的概念图**

在![Office 即点即用安装程序中使用 COM 接口的关系图。]在(media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "Office 即点即用安装程序上使用 COM 接口的关系图")
  
Office 365 即点即用安装程序实现基于 COM 的接口, **IUpdateNotify**注册到 CLSID **CLSID_UpdateNotifyObject**。
  
可以按如下方式调用此接口:
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

仅当呼叫者在提升的权限下运行时, 调用才会成功, 因为必须使用提升的权限运行即点即用安装程序。
  
**IUpdateNotify** COM 接口公开三个异步功能, 负责验证命令和参数, 并使用即点即用安装服务执行计划的运行。 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

"**状态**" 方法可用于获取有关上次执行的命令状态的信息, 或当前正在执行的命令的状态 (即成功、失败、详细错误代码)。
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

在其生命周期中, 即点即用安装服务可能处于运行状态的四种状态, 在此期间可以调用**IUpdateNotify**方法;重新启动、空闲、下载和应用。 
  
**以下是 COM 接口状态机关系图**

![COM 接口的状态图。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口的状态图")
  
> [!NOTE]
> **重新启动**: 当计算机启动时, 即点即用安装程序服务不可用时的一段时间。 重新启动后, 对 Status 方法的成功调用将返回 eUPDATE_UNKNOWN。 
  
**空闲:** 当即点即用安装程序处于空闲状态时, 您可以调用: 
  
- **应用**: 安装以前下载的内容。
    
- **取消**: 返回`0x800000e`"在意外的时间调用方法"。
    
- **下载**: 将新内容下载到客户端, 以供以后安装。
    
- **Status**: 返回上次完成的操作的结果, 如果操作在失败时结束, 则返回错误消息。 如果没有上一个操作,**状态**将返回`eUPDATE_UNKNOWN`。
    
**下载:** 当即点即用安装程序处于下载状态时, 您可以调用: 
  
- **应用**: 返回值**** `0x800000e`为 "在意外的时间调用了某个方法的 HRESULT"。
    
- **取消**: 停止下载并删除部分下载的内容。
    
- **下载**: 返回值**** `0x800000e`为 "在意外时间调用方法" 的 HRESULT。 
    
- **Status**: 返回**DOWNLOAD_WIP**以指示正在进行下载工作。 
    
**应用:** 当即点即用安装程序安装之前的下载内容的过程中: 
  
- **应用**: 返回值**** `0x800000e`为 "在意外的时间调用了某个方法的 HRESULT"。
    
- **取消**: 返回`0x800000e`, 无法取消应用操作。
    
- **下载**: 返回值**** `0x800000e`为 "在意外时间调用方法" 的 HRESULT。 
    
- **Status**: 返回**APPLY_WIP**以指示应用工作正在进行中。 
    
> [!NOTE]
> 由于 OfficeC2RCOM 是 com + 服务并且已动态加载, 因此您需要在每次调用此类上的方法时调用**CoCreateInstance** , 以确保获得预期的结果。 如果需要, com + 服务将处理创建新实例的情况。 当首次调用其中一种方法时, com + 将加载**IUpdateNotify**对象并在其中一个 dllhost 实例中运行它。 新对象将保持活动状态大约3分钟, 并处于空闲状态。 如果在最后一次呼叫的三分钟内进行后续调用, 则**IUpdateNotify**对象将保持加载, 并且不会创建新的实例。 如果在三分钟内未进行任何调用, 则将卸载 IUpdateNotify 对象, 并在下一次调用时创建一个新的**IUpdateNotify**对象。 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a>即点即用安装程序 COM API 参考指南

在下面的 API 参考文档中:
  
- 参数的键/值对格式由空格分隔。
    
- 参数不区分大小写。
    
- 有可用的带有文档[的参数的列表](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/)。 
    
- IUpdateNotify2 接口摘要现已包括在内。
    
### <a name="apply"></a>应用

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_: **true**以在更新过程中显示安装状态 (包括错误);**如果为 false** , 则在更新过程中隐藏安装状态, 包括错误。 默认值为 **false** 。
    
-  _forceappshutdown_: **true**以强制 Office 应用程序在触发**应用**程序操作时立即关闭;**假**如果有任何 Office 应用程序在运行时失败。 默认值为 **false** 。 有关详细信息, 请参阅 "[备注](#bk_ApplyRemark)"。 
    
  如果在触发**应用**操作时任何 Office 应用程序正在运行, 则**apply**操作通常会失败。 传递`forceappshutdown=true`给**Apply**方法将导致**OfficeClickToRun**服务立即关闭应用程序并应用更新。 在这种情况下, 用户可能会遇到数据丢失。 
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许执行操作。 有关详细信息, 请参阅 "[备注](#bk_ApplyRemark)"。  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a>注解

- 如果在触发**应用**操作时任何 Office 应用程序正在运行, 则**应用**操作将失败。 传递`forceappshutdown=true`给**Apply**方法将导致**OfficeClickToRun**服务立即关闭任何正在运行的 Office 应用程序并应用更新。 用户可能会遇到数据, 因为不提示他们保存对打开文档所做的更改。。 
    
- 仅当 COM 状态为以下情况之一时, 才能触发此操作: 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果在不下载内容的情况下调用**Apply**方法, 则**Apply**方法将报告**成功**, 因为它检测到什么内容未成功应用并已完成**应用**过程。 
    
### <a name="cancel"></a>取消

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|S_OK  <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|E_ILLEGAL_METHOD_CALL  <br/> |此时不允许执行操作。 有关详细信息, 请参阅 "[备注](#bk_CancelRemarks)" 部分  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a>注解

- 仅当 COM 状态 id 为**eDOWNLOAD_WIP**时, 才能触发此方法。 它将尝试取消当前的下载操作。 COM 状态将更改为**eDOWNLOAD_CANCELLING** , 最终更改为**eDOWNLOAD_CANCELED**。 如果在任何其他时间触发, COM 状态将返回**E_ILLEGAL_METHOD_CALL** 。 
    
### <a name="download"></a>下载

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_: **true**以在更新过程中显示安装状态 (包括错误);**如果为 false** , 则在更新过程中隐藏安装状态, 包括错误。 默认值为 **false** 。
    
-  _updatebaseurl_: 指向备用下载源的 URL。
    
-  _updatetoversion_: 将 Office 更新到的版本。 如果要更新到比当前安装的版本更旧的版本, 请定义此参数。
    
-  _downloadsource_: 自定义**IBackgroundCopyManager**实现的 CLSID (BITS 管理器)。 
    
-  _contentid_: 标识要通过自定义的 BITS 管理器从内容服务器下载的内容。 此值通过 BITS 接口传递以用于解释。
    
#### <a name="return-results"></a>返回结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到即点即用服务以执行。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |传递的参数无效。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许执行操作。 有关详细信息, 请参阅 "[备注](#bk_DownloadRemark)"。  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a>注解

- 必须将_downloadsource_和_contentid_指定为一对。 如果不是, 则**下载**方法将返回一个**E_INVALIDARG**错误。 
    
- 如果提供了_downloadsource_、 _contentid_和_updatebaseurl_ , 则将忽略_updatebaseurl_ 。 
    
- 仅当 COM 状态为以下情况之一时, 才能触发此操作: 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果在未下载内容的情况下调用**apply**方法, 则**Apply**方法将报告**成功**, 因为它检测到什么内容未成功应用并已完成**应用**过程。 
    
#### <a name="examples"></a>示例

- 若要从自定义的 BITS 管理器下载内容: 调用**下载 ()** 函数传递以下参数: 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- 若要从 Microsoft CDN 下载内容: 在未指定_downloadsource_、 _contentid_或_updatebaseurl_参数的情况下调用**下载 ()** 函数。 
    
- 若要从自定义位置下载内容: 调用**下载 ()** 函数传递以下参数: 
    
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
|**S_OK** <br/> |**Status**方法始终返回此结果。 检查当前`UPDATE_STATUS_RESULT`操作的状态的结构。  <br/> |
   
#### <a name="remarks"></a>注解

- 的 "状态" 字段`UPDATE_STATUS_REPORT`包含当前操作的状态。 将返回以下状态值之一: 
    
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

- 如果最后一个命令导致错误, 则`UPDATE_STATUS_REPORT`中的 "错误" 字段包含有关错误的详细信息。 **状态**方法返回两种类型的错误代码。 
    
- 如果错误小于`UPDATE_ERROR_CODE::eUNKNOWN`, 则此错误为下列预定义的错误代码之一:
    
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

  如果返回错误代码大于`UPDATE_ERROR_CODE::eUNKNOWN`为失败的函数调用的**HRESULT** 。 从的 " `UPDATE_STATUS_REPORT`错误" `UPDATE_ERROR_CODE::eUNKNOWN`字段中返回的值中提取 HRESULT 减去。
    
  可以通过检查嵌入在 OfficeC2RCom 中的**IUpdateNotify**类型库来查看状态和错误值的完整列表。 
    
- contentid 字段用于在开始**下载**后对**状态**的调用, 并返回传入到**下载**调用的 contentid。 最佳做法是, 在调用**status**方法之前将此字段初始化为**null** , 然后在返回**状态**后检查值。 如果该值仍为**null**, 则表示没有要返回的 contentid。 如果值不为**null**, 则需要调用**SysFreeString ()** 来释放它。 下面是一个代码段, 介绍了如何在**下载**后调用**状态**。
    
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

> [!NOTE]
> 此摘要作为将[可管理性应用程序与 Office 365 即点即用安装程序集成](https://msdn.microsoft.com/EN-US/library/office/mt608768.aspx)的补充信息提供。 更新公用文档后, 可以将此文档视为已过时。 
  
从 C2RTenant [16.0.8208.6352](https://oloop/BuildGroup/Details/tenantc2rclient#3519/1255278) (第一个公开发布的内部版本应为六月的分叉生成--8326. *) 我们添加了新的**IUpdateNotify2**接口。 下面是有关此接口的一些基本信息: 
  
- CLSID_UpdateNotifyObject2, {52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}
    
- 此接口也托管原始 IUpdateNotify 接口, 以提供向后兼容性。 这意味着, 如果您使用此接口, 则可以访问**UpdateNotifyObject**接口中提供的所有方法。 
    
- 添加到 IUpdateNotify2 的新方法:
    
  - **HRESULT**GetBlockingApps ([out] BSTR \* AppsList)。 获取更新阻止应用程序列表。 此调用将返回运行的 Office 应用程序, 这将阻止更新过程继续进行。 
    
  - **HRESULT**GetOfficeDeploymentData ([in] int dataType, [in]**一个 lpcwstr** pcwszName, [out] BSTR * OfficeData)。 获取 Office 部署数据。 
    
- 如果要使用新的方法, 您需要确保:
    
  - 您的 C2R 版本比上面的版本 (\>= 六月的分叉构建) 新。
    
  - 使用 UpdateNotifyObject2 而不是**UpdateNotifyObject**调用**CoCreateInstance**。
    
如果不使用任何新方法, 则无需更改任何内容。 所有现有方法的工作方式都与之前完全相同。
  
## <a name="implementing-the-bits-interface"></a>实现 BITS 接口

[后台智能传输服务](https://msdn.microsoft.com/library/bb968799(v=vs.85).aspx)(BITS) 是 Microsoft 提供的一种服务, 用于在客户端和服务器之间传输文件。 BITS 是 Office 即点即用安装程序可用于下载内容的频道之一。 默认情况下, Office 即点即用安装程序使用在 BITS 的内置实现从 CDN 下载内容。 
  
通过向**IUpdateNotify**接口的**下载 ()** 方法提供自定义的 BITS 实现, 您的可管理性软件可以控制客户端的下载内容的位置和方式。 当提供自定义内容分发通道 (而非即点即用的内置通道, 如 Office CDN、IIS 服务器或文件共享) 时, 自定义的 BITS 接口非常有用。 
  
与 Office C2R service 配合使用的自定义位接口的最低要求是:
  
- 对于**IBackgroundCopyManager**:
    
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

- 对于**IBackgroundCopyJob**:
    
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

- 对于**IBackgroundCopyJob3**:
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- 对于`Addfile`和`AddFileWithRanges`函数, 远程 URL 采用以下格式: 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - cmbits 是硬编码的, 并代表自定义位。
    
  -  __ **** _\> contentid 是用于下载 () 方法\<_ 的 contentid 参数。 
    
  -  _目标文件\>的相对路径提供要下载的文件的位置和\<_ 文件名。 
    
    例如, 如果您已提供**下载 ()** `v32.cab`方法`f732af58-5d86-4299-abe9-7595c35136ef`的_contentid_ , 而 Office C2R 想要下载版本 cab 文件 (如 file), 它将使用以下`RemoteUrl`命令调用**AddFile ()** :
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- 对于**IBackgroundCopyError**:
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- 对于**IBackgroundCopyFile**:
    
  ```cpp
  HRESULT _stdcall GetLocalName([out] LPWSTR *ppName); 
  HRESULT _stdcall GetRemoteName([out] LPWSTR *ppName);
  
  ```

<!--## Automating content staging

IT administrators can choose to have desktop clients enabled to automatically receive updates when they are available directly from the Microsoft Content Delivery Network (CDN) or they can choose to control the deployment of updates available from the [update channels](https://support.office.com/en-us/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&rs=en-US&ad=US) using the [Office 2016 Deployment Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49117) or [System Center Configuration Manager](https://support.office.com/en-us/article/Manage-updates-to-Office-365-ProPlus-with-System-Center-Configuration-Manager-b4a17328-fcfe-40bf-9202-58d7cbf1cede).
  
The service supports the ability for management tools to recognize and automate the download of the content when updates are made available.
  
**Following is a diagram showing the overview of downloading a custom image**

![An overview of downloading Office updates from the CDN.](media/9afac230-6b22-4526-a800-0562708cc436.png "An overview of downloading Office updates from the CDN")
  
In the above diagram you see that a new Office 365 ProPlus image is available on the Office Content Distribution Network (CDN). Along with the Office 365 ProPlus image, an XML-formatted file list is also available which has the information needed to enable manageability software to directly create customized images replacing the need for using the Office Deployment Tool.
  
An enterprise configures their WSUS to sync the Office 365 Client Updates. These updates do not contain the actual image payload but does allow the manageability software to recognize when new content is available. The manageability software can then read the Client Update metadata to understand what version of Office the update applies to.
  
If the update is applicable, the manageability software can use the CDN content and the file list to create the custom image and store it onto the file share location that it is configured to use.
  
### Format of the XML file list

There are two file lists available in a cab file on the CDN. One lists the files for the 32-bit version of Office and one for the 64-bit version of Office. The URL of the location of the Office File List (OFL.CAB) file is [https://officecdn.microsoft.com/pr/wsus/ofl.cab](https://officecdn.microsoft.com/pr/wsus/ofl.cab). The two file lists are called:
  
- O365Client_32bit.xml
    
- O365Client_64bit.xml
    
Within the XML for each of the file lists is an  `UpdateFiles` node which contains a version attribute.  `UpdateFiles version="1.4"`.
  
This version is incremented if changes are made to the file lists.
  
There are two parameters that need to be combined with the XML to make a custom image: 
  
- Replace  _%version%_ with the build version of Office. This can be derived from the Client Update metadata  `MoreInfoURL` field, see below. 
    
- Define  _baseURL_ by using the URL value associated with the branch the image is being created for. This can be derived from the Client Update metadata, see below. 
    
The steps for creating an image are:
  
1. Open the XML file list.
    
2. Replace occurrences of  _%version%_ with the applicable Office build version. The build version can be acquired from releasehistory.xml as described later in this article. 
    
3. Read the URL attribute for the target branch.
    
4. Remove language nodes for any languages not required in the custom image.
    
   > [!NOTE]
   > Nodes with language='0' are language neutral and must be included in the image. 
  
5. Construct a local image of the CDN by iterating through the XML file list and copying the CDN files, while creating the folder structure as needed. 
    
   - If the  _rename_ attribute is provided, then rename the copied file to the value provided in the  _rename_ attribute. This used to create the top-level default v64.cab and v32.cab files. These are the renamed versions of the top-level build cab file and are used as the default installation version if the version is not specified. 
    
   - Use URL + relativePath + filename to construct the CDN location.
    
The following examples use the Monthly channel (as defined by the  `baseURL` node) and build version 16.0.4229.1004 from releasehistory.xml. 
  
```cpp
baseURL branch="Monthly" URL="https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" /
```

- The following is a language neutral file needed for all languages. The name of the file is v64_16.0.4229.1004.cab and it should be copied from https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab and renamed to …/office/data/v64.cab.
    
  ```cpp
  baseURL branch="Business" URL="https://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114" /
  File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/
  
  ```

- The following is a file to be included in the en-US image as designated by the language LCID=1033. The name of the file is s641033.cab and it should be copied from https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab and not renamed.
    
  ```cpp
  File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" /
  ```

### Hash verification of data files

Image creation tools may verify the integrity of the downloaded .dat files by comparing a computed HASH value with the supplied HASH value associated with each of the .dat files. Below is an example of a .dat file from the Monthly channel with build version 16.0.4229.1004 and language set to Bulgarian.
  
```cpp
File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"
```

- The  _hashLocation_ attribute specifies the relative path location of the stream.x64.bg-bg.hash for the stream.x64.bg-bg.dat file. Construct the hash file location by concatenating URL + relativePath + hashLocation. In this example the stream.x64.bg-bg.hash location would be https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
    
- The  _hashAlgo_ attribute specifies what hashing algorithm was used. In this case the Sha256 algorithm was used. 
    
To validate the integrity of the stream.x64.bg-bg.dat file, open the stream.x64.bg-bg.hash and read the hash value from the first line of text in the hash file. Compare this to the has value that you computed using the specified hashing algorithm to verify that the values match. Use the following C# code to read the hash.
  
```cs
string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
string readHash = readHashes.First();

```

### Office 365 Client Updates

Office 365 Client Updates enable manageability software to treat the Office 365 Client Updates in a manner very similar to any other WU update with one exception; the client updates do not contain an actual payload. The Office 365 Client Updates should not be installed on any clients but rather used to trigger the workflows with the manageability software replacing the installation command with the COM based installation mechanism shown above.
  
**Office 365 Client Update workflow**

![Workflow diagram for O365PP client updates.](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "Workflow diagram for O365PP client updates")
  
Each Office 365 Client Update that is published includes metadata about the update. This metadata includes a parameter called  _MoreInfoUrl_ which can be used to derive the following information: 
  
-  _Ver_: Identifies the Office version associated with this update. For example 16.0.4229.1004.
    
-  _Branch_: Identifies the Update Channel for this update. Values include InsiderFast, Insiders, Monthly, Targeted, Broad. Additional values may be added in the future.
    
-  _Arch_: Identifies the processor architecture associated with this update.
    
-  _xmlVer_: Identifies the version of the XML file lists to use to construct the base image for this update.
    
-  _xmlPath_: Path to the OFL.CAB file that contains the XML file lists.
    
-  _xmlFile_: The name of the file list that should be used for this update. The value will be  `O365Client_32bit` or  `O365Client_64bit` and will match the value in  _Arch_.
    
The following is an example of the  _MoreInfoURL_ parameter which refers to the Office 365 Client Update for the 32-bit version of Office with build version of 16.0.2342.2343 on the Current channel. 
  
```http
https://officecdn.microsoft.com/pr/wsus/ofl.cab is the location of the XML file lists for this update, specifically the O365Client_32bit.xml from within the OFL.CAB.
https://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=https://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml 

```
THE ABOVE SECTION APPEARS TO BE A DUPLICATE OF THE FOLLOWING SECTION; TEMPORARILY COMMENTING IT OUT.-->

## <a name="automating-content-staging"></a>自动化内容暂存

IT 管理员可以选择启用桌面客户端, 以便在 Microsoft 内容交付网络 (CDN) 中直接获取更新, 也可以选择控制更新时可用的更新部署使用 Office 部署工具或 System Center Configuration Manager 的通道。
  
服务支持管理工具在更新可用时识别和自动下载内容的功能。
  
**下图概述了下载自定义图像**

在![Office 即点即用安装程序中使用 COM 接口的关系图。]在(media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "Office 即点即用安装程序上使用 COM 接口的关系图")
  
### <a name="overview-of-downloading-a-custom-image"></a>下载自定义图像概述
  
在上图中, 您会看到 office 内容分发网络 (CDN) 上有一个新的 office 365 专业增强版图像。 除了 Office 365 专业增强版图像, 还提供了一个 XML 格式的文件列表, 其中包含启用可管理性软件以直接创建自定义图像以替换使用 Office 部署工具的需求所需的信息。
  
企业将其 WSUS 配置为同步 Office 365 客户端更新。 这些更新不包含实际图像负载, 但允许可管理性软件识别新内容何时可用。 然后, 可管理性软件可以读取客户端更新元数据, 以了解应用更新的 Office 版本。
  
如果更新适用, 可管理性软件可以使用 CDN 内容和文件列表来创建自定义图像, 并将其存储在配置为使用的文件共享位置上。
  
### <a name="format-of-the-xml-file-list"></a>XML 文件列表的格式

CDN 文件中有两个文件列表可在 cab 文件中使用。 一个列出了32位版本的 office 的文件, 另一个为64位版本的 office。 Office 文件列表 (OFL) 位置的 URL。CAB) 文件[https://officecdn.microsoft.com/pr/wsus/ofl.cab](https://officecdn.microsoft.com/pr/wsus/ofl.cab)。 这两个文件列表称为:
  
- O365Client_32bit
    
- O365Client_64bit
    
在每个文件列表的 XML 中, 都是<UpdateFiles>一个包含 version 属性的节点。  `<UpdateFiles version="1.4">`. 如果对文件列表进行了更改, 则此版本递增。
  
有两个参数需要与 XML 组合使用, 以生成自定义图像: 
  
- 将 *% version* % 替换为 Office 的内部版本。 这可以从客户端更新元数据 (下一节所述) 派生。 
    
- 使用与要为其创建图像的分支相关联的 URL 值定义*baseURL* 。 这是从客户端更新元数据派生的, 下一节对此进行了说明。 
    
创建图像的步骤如下:
  
1. 打开 XML 文件列表。
    
2. 将 *% version* % 的匹配项替换为适用的 Office 内部版本。 可以从 releasehistory 获取内部版本, 如本文后面所述。 
    
3. 读取目标分支的 URL 属性。
    
4. 删除自定义图像中不需要的任何语言的语言节点。
    
   > [!NOTE]
   > 语言为 "0" 的节点是非特定语言的, 并且必须包含在图像中。 
  
5. 通过循环访问 XML 文件列表并复制 cdn 文件来构造 cdn 的本地映像, 同时根据需要创建文件夹结构。 
    
   - 如果提供了*rename*属性, 请将复制的文件*重命名*为 rename 属性中提供的值。 此项用于创建顶级默认 v64 和 v32 文件。 这些是顶级生成 cab 文件的重命名版本, 并在未指定版本时用作默认安装版本。 
    
   - 使用 URL + relativePath + filename 构造 CDN 位置。
    
以下是使用每月频道 (由`<baseURL>`节点定义) 和从 releasehistory 生成版本16.0.4229.1004 的示例。 
  
```xml
<baseURL branch="Monthly" URL="https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" />
```

- 以下是所有语言所需的语言中立文件。 文件的名称为 v64_ 16.0.4229.1004, 应从`https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab`复制到并重命名为。 `…/office/data/v64.cab` 
    
  ```xml
  <File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/>
  
  ```

- 以下是由语言 LCID = 1033 指定的包含在 en-us 图像中的文件。 文件的名称为 s641033, 应从`https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab`复制而不是对其进行重命名。
    
  ```xml
  <File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" />
  ```

### <a name="hash-verification-of-dat-files"></a>.dat 文件的哈希验证

通过将计算的哈希值与与每个 .dat 文件相关联的提供的哈希值相比较, 图像创建工具可以验证下载的 .dat 文件的完整性。 以下是每月频道中的 .dat 文件的示例, 其中生成版本16.0.4229.1004 和语言设置为保加利亚语:
  
```xml
<File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"/>
```

- **hashLocation**属性指定 stream.x64.bg-bg 文件的 stream.x64.bg-bg 的相对路径位置。 通过串联 URL + relativePath + hashLocation 构造哈希文件位置。 在下面的示例中, stream.x64.bg 的哈希位置将为: 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- **hashAlgo**属性指定使用哪种哈希算法。 在这种情况下, 使用了 Sha256。 
    
  若要验证 stream.x64.bg-bg 文件的完整性, 请打开 stream.x64.bg-bg. 哈希, 并读取哈希值, 该值是哈希文件中的第一行文本。 将此值与计算的哈希值 (使用指定的哈希算法) 进行比较, 以验证下载的 .dat 文件的完整性。
    
  下面的示例演示用于读取哈希的 c # 代码。
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="office-365-client-updates"></a>Office 365 客户端更新

所有 Office 365 客户端更新都将发布到[Microsoft Update 目录](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。
  
office 365 客户端更新使易管理性软件能够以与任何其他 WU 更新 (只是一个例外) 相似的方式来处理 Office 365 客户端更新。客户端更新不包含实际有效负载。 不应将 Office 365 客户端更新安装在任何客户端上, 而是使用可管理性软件将安装命令替换为上面所示的基于 COM 的安装机制来触发工作流。 
  
**下图显示了 Office 365 客户端更新工作流的关系图。**

![O365PP 客户端更新的工作流图表。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流图表")
  
发布的每个 Office 365 客户端更新都包含有关更新的元数据。 此元数据包含一个名为*MoreInfoUrl*的参数, 可用于派生以下信息: 
  
-  *Ver*: 标识与此更新关联的 Office 版本。 
    
-  *Branch*: 标识此更新的更新频道。 值包括 InsiderFast、内部人员、每月、目标、广泛。 将来可能会添加其他值。 
    
-  *拱*: 标识与此更新关联的处理器体系结构。 
    
-  *xmlVer*: 应用于构造此更新的基本图像的 XML 文件列表的版本。 
    
-  *xmlPath*: OFL 的路径。包含 XML 文件列表的 CAB 文件。 
    
-  *mlFile*: 此更新应使用的文件列表的名称。 值将为 O365Client_32bit 或 O365Client_64bit, 并且将匹配该弧。 
    
下面的 URL 是*MoreInfoURL*参数的一个示例, 它是指在当前通道上使用16.0.2342.2343 的内部版本的 office 的32位版本的 office 的 office 365 客户端更新版本。 
  
https://officecdn.microsoft.com/pr/wsus/ofl.cab是此更新的 XML 文件列表的位置, 特别是 OFL 中的 O365Client_32bit。间.
  
[Office 365 客户端更新频道版本](https://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=https://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml)
  
### <a name="additional-metadata-for-automating-content-staging"></a>用于自动执行内容暂存的其他元数据

除了已发布的元数据定义的元数据之外, 还会向 CDN 发布其他 XML 文件, 这些文件可帮助提供有关 office 365 客户端在 office CDN 中可用的其他信息。
  
**sku.XML**
  
此 XML 文件包含在已签名的 CAB 中, 并发布到以下 URL 中的 Office CDN [https://officecdn.microsoft.com/pr/wsus/skus.cab](https://officecdn.microsoft.com/pr/wsus/skus.cab):。
  
在此 XML 文件中发布的元数据可用于确定哪些产品可用于从 Office CDN 进行部署和服务, 以及每个产品的各种选项。 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<ReleaseInfo PublishedDate="08/07/2017 16:34">
  <!-- Suite / App catalog -->
  <Suite>
    <SKU Name="Office 365 ProPlus" ProductID="O365ProPlusRetail" Default="True">
      <Apps>
        <App Name="Access" AppID="Access" />
        <App Name="Excel" AppID="Excel" />
        <App Name="OneDrive for Business (Groove)" AppID="Groove" />
        <App Name="OneDrive for Business (Next Gen Sync Client)" AppID="OneDrive" />
        <App Name="OneNote" AppID="OneNote" />
        <App Name="Outlook" AppID="Outlook" />
        <App Name="PowerPoint" AppID="PowerPoint" />
        <App Name="Publisher" AppID="Publisher" />
        <App Name="Skype for Business" AppID="Lync" />
        <App Name="Word" AppID="Word" />
      </Apps>
      <Channels>
        <Channel ID="Monthly"/>
        <Channel ID="Insiders"/>
        <Channel ID="Targeted"/>
        <Channel ID="Broad"/>
      </Channels>
    </SKU>
```

ReleaseInfo 根节点包含用于标识此文件的发布日期的 PublishedDate 属性。 ** \<\> ** 
  
sku 节点标识单个 SKU。 ** \<\> ** 
  
- *ProductID*属性标识作为配置 .xml 中的 id 属性传递的 id (如果使用 ODT)。 例如，`<Product ID="O365ProPlusRetail">`。 
    
- 如果设置为 True, 则*默认*属性标识建议的 SKU。 
    
应用节点用于定义每个 SKU 支持的各个 Office 应用。 ** \<\> ** 
  
- *Name*属性是显示的应用程序名称。 
    
- *AppID*属性是在配置 .xml 中传递的 ID 属性 (如果使用 ODT, 则为** \<ExcludeApp\> **节点)。 例如，`<ExcludeApp ID="Publisher" />`。 
    
**RELEASEHISTORY。XML**
  
此 XML 文件包含在已签名的 CAB 中, 并已发布到以下位置的 Office CDN [https://officecdn.microsoft.com/pr/wsus/releasehistory.cab](https://officecdn.microsoft.com/pr/wsus/releasehistory.cab)中:。 
  
在此 XML 文件中发布的元数据对于确定支持来自 Office CDN 的更新的通道以及有关每个受支持通道的生成历史记录的信息很有用。
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<ReleaseHistory PublishedDate="10/22/2017 00:48">
  <UpdateChannel Name="Current" ID="Monthly" DisplayName="Monthly Channel">
    <Update Latest="True" Version="1709" LegacyVersion="16.0.8528.2139" Build="8528.2139" PubTime="2017-10-16T19:45:50.743Z" />
    <Update Latest="False" Version="1708" LegacyVersion="16.0.8431.2107" Build="8431.2107" PubTime="2017-10-11T01:52:33.793Z" />
    <Update Latest="False" Version="1708" LegacyVersion="16.0.8431.2079" Build="8431.2079" PubTime="2017-09-18T22:26:13.673Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2107" Build="8326.2107" PubTime="2017-09-12T18:56:53.657Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2096" Build="8326.2096" PubTime="2017-08-30T00:10:25.253Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2076" Build="8326.2076" PubTime="2017-08-19T00:13:01.787Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2073" Build="8326.2073" PubTime="2017-08-11T19:35:42.173Z" />
  </UpdateChannel>
```

ReleaseHistory 根节点包含用于标识此文件的发布日期的 PublishedDate 属性。 ** \<\> ** 
  
UpdateChannel 节点定义受支持的通道。 ** \<\> ** 
  
- *Name*属性定义通道 ID, 用于将 config.xml 中的 ODT 作为信道属性进行传递。 
    
  示例： `<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Current">` 
    
  > [!NOTE] 
  > 此属性已被弃用, 仅用于向后兼容性。 使用 ID 属性代替 Name 属性。 
    
- *ID*属性定义通道 ID, 用于将 config.xml 中的 ODT 作为信道属性进行传递。 
    
  示例： `<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Deferred">` 
    
- **DisplayName**属性将用作显示名称。 
    
Update 节点用于定义为该特定通道发布的每个更新。 ** \<\> ** 
  
- 如果设置为 True, 则**最新**属性将定义版本为该频道的最新版本。 
    
- **version**属性定义此特定更新的版本号。 
    
- **LegacyVersion**属性定义此特定更新的完整版本号。 
    
- **Build**属性定义此特定更新的内部版本号。 
    
- **PubTime**属性定义将此更新发布到 Office CDN 的日期和时间。 
    

