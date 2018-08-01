---
title: 使用 Office 365 即点即用安装程序的集成可管理性应用程序
manager: kelbow
ms.date: 10/22/2017
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: 了解如何使用软件管理解决方案集成 Office 365 单击以运行安装程序。
ms.openlocfilehash: abe941e3e3818eed1f18108f1678e46e8156b08c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779566"
---
# <a name="integrating-manageability-applications-with-office-365-click-to-run-installer"></a>使用 Office 365 即点即用安装程序的集成可管理性应用程序

了解如何使用软件管理解决方案集成 Office 365 单击以运行安装程序。
  
Office 365 单击以运行安装程序提供允许 IT 专业人员和软件管理解决方案进行编程控制更新管理的 COM 接口。 此接口提供超出所提供的 Office 部署工具的其他管理功能。
  
> [!NOTE]
> 本文适用于 Office 2016 和更高版本，Office 365。 
  
## <a name="integrating-with-the-click-to-run"></a>单击运行集成

若要使用此接口，可管理性应用程序调用 COM 接口和呼叫公开直接与单击即点即用安装服务进行通信的 Api。 
  
> [!NOTE]
> 单击以运行 Office 安装程序可以从命令行使用的参数运行可以控制的行为，在[单击即点即用 Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)中所述。 
  
**以下是 COM 接口的概念图**

![上，单击以运行 Office 安装程序使用的 COM 接口的图表。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "使用上，单击以运行 Office 安装程序的 COM 接口的图表")
  
Office 365 单击以运行安装程序的基于 COM 的实现接口**IUpdateNotify**注册到 CLSID **CLSID_UpdateNotifyObject**。
  
该接口可以调用，如下所示：
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

呼叫才会成功运行呼叫者所使用提升的权限，因为必须以提升的权限运行单击即点即用安装程序。
  
**IUpdateNotify** COM 接口将公开负责验证命令和参数和计划执行与单击即点即用安装服务三个异步函数。 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

A 规定方法，**状态**，可用于获取的状态信息的上次执行的命令或当前正在执行命令 （即成功故障、 详细的错误代码） 的状态。
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

共有四种状态单击即点即用安装服务可能位于在其生命周期期间可能会调用**IUpdateNotify**方法;重新启动，空闲，下载并应用。 
  
**以下是 COM 接口状态机关系图**

![的 COM 接口的状态图表。](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "COM 接口状态图表")
  
> [!NOTE]
> **Rebooting**： 启动计算机时一段时间单击即点即用安装程序服务不可用。 成功调用后重新启动状态方法将返回 eUPDATE_UNKNOWN。 
  
**空闲时间：** 当单击即点即用安装程序处于空闲状态时，您可以调用： 
  
- **应用**： 安装之前下载的内容。
    
- **取消**： 返回`0x800000e`，"调用的方法是在意外时间。"
    
- **下载**： 下载到客户端的更高版本安装的新内容。
    
- **状态**： 如果操作结束中失败，则返回结果的最后一个已完成的操作或一条错误消息。 如果没有上一操作，将返回**状态** `eUPDATE_UNKNOWN`。
    
**下载：** 下载状态单击即点即用安装程序后，您可以调用： 
  
- **应用**： 返回的值的**HRESULT** `0x800000e`，"调用的方法是在意外时间。"
    
- **取消**： 停止下载并删除部分下载的内容。
    
- **下载**： 返回的值的**HRESULT** `0x800000e`，"调用的方法是在意外时间。" 
    
- **状态**： 返回**DOWNLOAD_WIP**来指示下载工作正在进行。 
    
**应用：** 当单击即点即用安装程序正在安装以前下载内容： 
  
- **应用**： 返回的值的**HRESULT** `0x800000e`，"调用的方法是在意外时间。"
    
- **取消**： 返回`0x800000e`，不能取消应用操作。
    
- **下载**： 返回的值的**HRESULT** `0x800000e`，"调用的方法是在意外时间。" 
    
- **状态**： 返回**APPLY_WIP**以指示的应用工作正在进行。 
    
> [!NOTE]
> 由于 OfficeC2RCOM 是 COM + 服务，并且是动态加载，您需要调用**CoCreateInstance**每次此类，以确保您得到的预期的结果上调用的方法。 COM + 服务将处理根据需要创建的新实例。 当第一次调用的方法之一时，COM + 将加载**IUpdateNotify**对象并运行一个 dllhost.exe 实例中。 大约 3 分钟的空闲，新的对象将保持活动状态。 如果上次呼叫的三个分钟内进行后续呼叫， **IUpdateNotify**对象将保持加载，并且不创建一个新实例。 如果没有呼叫由三个分钟内，将卸载 IUpdateNotify 对象，并进行下一次呼叫时，将创建一个新的**IUpdateNotify**对象。 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a>单击即点即用安装程序 COM API 参考指南

在下面的 API 参考文档：
  
- 参数在由空格分隔的键/值对格式。
    
- 参数不区分大小写。
    
- 没有可用的文档与[参数的列表](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/)。 
    
- 摘要 IUpdateNotify2 接口现包括。
    
### <a name="apply"></a>Apply

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_: **true**以显示安装状态，包括错误，在更新过程;**false**以隐藏错误，包括在更新过程中的安装状态。 默认值为 **false** 。
    
-  _forceappshutdown_: **true**以强制关闭立即**应用**操作被触发; Office 应用程序**false**失败如果任何 Office 应用程序正在运行。 默认值为 **false** 。 有关详细信息，请参阅[备注](#bk_ApplyRemark)。 
    
  如果任何 Office 应用程序正在运行触发**应用**操作时，通常将失败**应用**操作。 传递`forceappshutdown=true`**应用**到方法将导致**OfficeClickToRun**服务若要立即关闭应用程序和应用更新。 在这种情况下，用户可能会遇到数据丢失。 
    
#### <a name="return-results"></a>返回的结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到执行的即点即单击服务。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |无效的参数传递。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许操作。 有关详细信息，请参阅[备注](#bk_ApplyRemark)。  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a>说明

- 如果任何 Office 应用程序正在运行时将触发**应用**操作，则**应用**操作将失败。 传递`forceappshutdown=true`**应用**到方法将导致**OfficeClickToRun**服务若要立即关闭任何 Office 应用程序正在运行并应用更新。 用户可能会遇到数据，它们不提示保存对打开的文档的更改。. 
    
- 此操作只能触发 COM 状态时下列选项之一： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果不以前下载内容的情况下调用**Apply**方法， **Apply**方法将报告**成功**，因为它检测到任何应用并成功地完成**应用**过程。 
    
### <a name="cancel"></a>Cancel

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a>返回的结果

|||
|:-----|:-----|
|S_OK  <br/> |操作已成功提交到执行的即点即单击服务。  <br/> |
|E_ILLEGAL_METHOD_CALL  <br/> |此时不允许操作。 请参阅[备注](#bk_CancelRemarks)部分的详细信息  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a>说明

- 此方法仅可触发何时 COM 状态 id **eDOWNLOAD_WIP**。 它将尝试取消当前下载操作。 COM 状态将更改为**eDOWNLOAD_CANCELLING**和最终更改为**eDOWNLOAD_CANCELED**。 如果在其他任何时间触发，COM 状态将返回**E_ILLEGAL_METHOD_CALL** 。 
    
### <a name="download"></a>下载

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a>参数

-  _displaylevel_: **true**以显示安装状态，包括错误，在更新过程;**false**以隐藏错误，包括在更新过程中的安装状态。 默认值为 **false** 。
    
-  _updatebaseurl_： 备用下载源的 URL。
    
-  _updatetoversion_： 要更新到 Office 的版本。 定义此参数，如果您想要更新为比当前安装的版本较早版本。
    
-  _downloadsource_： 自定义**IBackgroundCopyManager**实现 （位经理） 的 CLSID。 
    
-  _contentid_： 标识要从自定义位经理通过内容服务器下载的内容。 此值被通过 interpretation 的位界面。
    
#### <a name="return-results"></a>返回的结果

|||
|:-----|:-----|
|**S_OK** <br/> |操作已成功提交到执行的即点即单击服务。  <br/> |
|**E_ACCESSDENIED** <br/> |呼叫者未使用提升的权限运行。  <br/> |
|**E_INVALIDARG** <br/> |无效的参数传递。  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |此时不允许操作。 有关详细信息，请参阅[备注](#bk_DownloadRemark)。  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a>说明

- 您必须作为对指定_downloadsource_和_contentid_ 。 如果没有，请**下载**方法将返回**E_INVALIDARG**错误。 
    
- 如果提供了_downloadsource_、 _contentid_和_updatebaseurl_ ， _updatebaseurl_将被忽略。 
    
- 此操作只能触发 COM 状态时下列选项之一： 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- 如果调用不带以前下载内容**Apply**方法时， **Apply**方法将报告**成功**，因为它检测到任何应用并成功地完成**应用**过程。 
    
#### <a name="examples"></a>示例

- 若要从自定义的位经理下载内容： 调用**download()** 函数传递以下参数： 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- 若要下载 Microsoft CDN 中的内容： 在不指定_downloadsource_、 _contentid_或_updatebaseurl_参数的情况下调用**download()** 函数。 
    
- 若要从自定义位置下载内容： 调用**download()** 函数传递以下参数： 
    
  ```cpp
  "updatebaseurl=yourcontentserverurl"
  ```

### <a name="status"></a>Status

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
| _pUpdateStatusReport_ <br/> |指向 UPDATE_STATUS_REPORT 结构。  <br/> |
   
#### <a name="return-results"></a>返回的结果

|||
|:-----|:-----|
|**S_OK** <br/> |**状态**方法始终返回此结果。 检查`UPDATE_STATUS_RESULT`的当前操作状态的结构。  <br/> |
   
#### <a name="remarks"></a>说明

- 状态字段中的`UPDATE_STATUS_REPORT`包含当前操作的状态。 返回下的状态值之一： 
    
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

- 如果的最后一个命令将导致出错错误字段中的`UPDATE_STATUS_REPORT`包含有关错误的详细的信息。 从**状态**方法返回的错误代码的两种类型。 
    
- 如果错误小于`UDPATE_ERROR_CODE::eUNKNOWN`，错误是预定义的错误代码之一：
    
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

  如果返回的错误代码大于`UDPATE_ERROR_CODE::eUNKNOWN`它是**HRESULT**的失败的函数调用。 提取 HRESULT 减去`UDPATE_ERROR_CODE::eUNKNOWN`的错误字段中返回的值从`UPDATE_STATUS_REPORT`。
    
  可以通过检查**IUpdateNotify**类型库中 OfficeC2RCom.dll 嵌入查看的状态和错误信息值的完整列表。 
    
- **下载**已启动并返回传递给**下载**呼叫 contentid 之后，contentid 字段用于呼叫**状态**。 它是一种最佳做法之前调用**状态**方法，然后检查的值之后在返回**状态**初始化此字段为**null** 。 如果值仍为**空**，这意味着不没有返回任何 contentid。 如果值不为**null**，则需要忙与**SysFreeString()** 调用。 下面是如何**下载**后调用**状态**代码段。
    
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

### <a name="summary-of-iupdatenotify2-interface"></a>IUpdateNotify2 接口的摘要。

> [!NOTE]
> 这段摘要是为[Integrating 可管理性与 Office 365 即点即用安装程序的应用程序](https://msdn.microsoft.com/EN-US/library/office/mt608768.aspx)提供补充信息。 一旦公共 doc 进行了更新，此 doc 可以被视为为已过时。 
  
从 C2RTenant [16.0.8208.6352](http://oloop/BuildGroup/Details/tenantc2rclient#3519/1255278) (第一个公开生成应年 6 月分叉生成-8326.*) 我们已添加新的**IUpdateNotify2**接口。 下面是一些有关此接口的基本信息： 
  
- CLSID_UpdateNotifyObject2，{52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}
    
- 此接口还承载着原始 IUpdateNotify 接口提供向后兼容性。 这意味着，如果您使用此接口，您有权访问所有**UpdateNotifyObject**界面中提供的方法。 
    
- 添加到 IUpdateNotify2 的新方法：
    
  - **HRESULT**GetBlockingApps ([输出] BSTR \* AppsList)。 获取更新阻止应用程序列表。 此呼叫将返回运行 Office 应用程序，其中将阻止继续从的更新过程。 
    
  - **HRESULT**GetOfficeDeploymentData ([in] int 数据类型，[in]**一个 lpcwstr，** pcwszName，[out] BSTR * OfficeData)。 获取 Office 部署数据。 
    
- 如果您想要使用的新方法，则需要以确保：
    
  - 是您 C2R 版本比上述生成高 (\>= 年 6 月分叉生成)。
    
  - 使用 UpdateNotifyObject2，而不是**UpdateNotifyObject**调用**CoCreateInstance**。
    
如果您不使用任何新方法，您无需更改任何内容。 所有现有方法将用作确切与之前相同的方式。
  
## <a name="implementing-the-bits-interface"></a>实现位接口

[后台智能传输服务](https://msdn.microsoft.com/en-us/library/bb968799(v=vs.85).aspx)(BITS) 是由 Microsoft 客户端和服务器之间传输文件提供服务。 单击以运行 Office 安装程序可用于下载内容的通道之一位。 默认情况下，单击以运行 Office 安装程序使用 Windows 的生成实现位 CDN 中下载内容中。 
  
通过提供**IUpdateNotify**接口的自定义的位实现**download()** 方法，您可管理性软件可以控制客户端在何处以及如何下载内容。 提供内置的单击即点即用的通道，如 Office CDN，IIS 服务器之外的自定义内容分发通道时有用的自定义的位界面或文件共享。 
  
自定义的位接口来处理 Office C2R 服务的最低要求是：
  
- 为**IBackgroundCopyManager**:
    
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

- 为**IBackgroundCopyJob**:
    
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

- 为**IBackgroundCopyJob3**:
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- 为`Addfile`和`AddFileWithRanges`功能，远程 URL 时采用以下格式： 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - cmbits 硬编码，并表示自定义比特。
    
  -  _ \<contentid\>_ 是_contentid_ **Download()** 方法的参数。 
    
  -  _\<目标文件的相对路径\>_ 提供要下载的文件的位置和文件名称。 
    
    例如，如果您提供的_contentid_ `f732af58-5d86-4299-abe9-7595c35136ef`到**Download()** 方法和 Office C2R 想要下载版本 cab 文件，如`v32.cab`文件，它将与以下调用**AddFile()** `RemoteUrl`:
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- 为**IBackgroundCopyError**:
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- 为**IBackgroundCopyFile**:
    
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

There are two file lists available in a cab file on the CDN. One lists the files for the 32-bit version of Office and one for the 64-bit version of Office. The URL of the location of the Office File List (OFL.CAB) file is [http://officecdn.microsoft.com/pr/wsus/ofl.cab](http://officecdn.microsoft.com/pr/wsus/ofl.cab). The two file lists are called:
  
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
baseURL branch="Monthly" URL="http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" /
```

- The following is a language neutral file needed for all languages. The name of the file is v64_16.0.4229.1004.cab and it should be copied from http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab and renamed to …/office/data/v64.cab.
    
  ```cpp
  baseURL branch="Business" URL="http://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114" /
  File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/
  
  ```

- The following is a file to be included in the en-US image as designated by the language LCID=1033. The name of the file is s641033.cab and it should be copied from http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab and not renamed.
    
  ```cpp
  File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" /
  ```

### Hash verification of data files

Image creation tools may verify the integrity of the downloaded .dat files by comparing a computed HASH value with the supplied HASH value associated with each of the .dat files. Below is an example of a .dat file from the Monthly channel with build version 16.0.4229.1004 and language set to Bulgarian.
  
```cpp
File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"
```

- The  _hashLocation_ attribute specifies the relative path location of the stream.x64.bg-bg.hash for the stream.x64.bg-bg.dat file. Construct the hash file location by concatenating URL + relativePath + hashLocation. In this example the stream.x64.bg-bg.hash location would be http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
    
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
http://officecdn.microsoft.com/pr/wsus/ofl.cab is the location of the XML file lists for this update, specifically the O365Client_32bit.xml from within the OFL.CAB.
http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml 

```
THE ABOVE SECTION APPEARS TO BE A DUPLICATE OF THE FOLLOWING SECTION; TEMPORARILY COMMENTING IT OUT.-->

## <a name="automating-content-staging"></a>自动执行内容暂存

IT 管理员可以选择启用自动接收更新它们可直接从 Microsoft 内容交付网络 (CDN) 或他们可以选择控制从更新可用更新的部署时的桌面客户端使用 Office 部署工具或 System Center Configuration Manager 通道。
  
该服务支持的功能的管理工具，以识别和可用进行更新时自动下载内容。
  
**下图是下载的自定义图像的概述**

![上，单击以运行 Office 安装程序使用的 COM 接口的图表。](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "使用上，单击以运行 Office 安装程序的 COM 接口的图表")
  
### <a name="overview-of-downloading-a-custom-image"></a>下载的自定义图像的概述
  
在上图中，您看到新的 Office 365 ProPlus 图像是 Office 内容分发网络 (CDN) 上可用。 Office 365 ProPlus 的图像，以及一个 XML 格式的文件列表中也有其已启用直接创建自定义的图像替换需要使用 Office 部署工具的可管理性软件所需的信息。
  
企业配置其 WSUS 同步 Office 365 客户端更新。 这些更新不包含实际图像负载，但允许可管理性软件，以识别新的内容时可用。 可管理性软件然后可以读取要了解哪些版本的更新适用于 Office 的客户端更新元数据。
  
可管理性软件适用更新时，可以使用 CDN 内容和文件列表创建自定义图像并将其存储到的文件共享位置配置为使用。
  
### <a name="format-of-the-xml-file-list"></a>XML 文件列表的格式

CDN 的 cab 文件中提供了两个文件列表。 一个列出 32 位版本的 Office 文件和一个用于 64 位版本的 Office。 Office 文件列表 (OFL 的位置 URL。CAB) 文件是[http://officecdn.microsoft.com/pr/wsus/ofl.cab](http://officecdn.microsoft.com/pr/wsus/ofl.cab)。 两个文件列表称为：
  
- O365Client_32bit.xml
    
- O365Client_64bit.xml
    
在每个文件的 XML 列表中，<UpdateFiles>节点包含 version 属性。  `<UpdateFiles version="1.4">`. 如果的文件列表进行了更改，就会增加此版本。
  
有两个参数所需的 xml，以使自定义图像组合： 
  
- Office 的内部版本替换 *%版本 %* 。 这可以派生客户端更新元数据 （下一节中所述）。 
    
- 使用图像正在创建的分支相关联的 URL 值定义*baseURL* 。 这被从客户端更新元数据下, 一节中所述。 
    
创建图像的步骤如下：
  
1. 打开 XML 文件列表。
    
2. 替换适用的 Office 内部版本 *%版本 %* 的匹配项。 可以从 releasehistory.xml 中获取的内部版本号，本文后面所述。 
    
3. 阅读目标分支的 URL 属性。
    
4. 删除自定义图像中不需要任何语言的语言节点。
    
   > [!NOTE]
   > 与语言的节点 ="0"的非特定语言和必须包含图像。 
  
5. 通过循环访问 XML 文件列表并根据需要创建的文件夹结构时复制 CDN 文件，构建 CDN 本地图像。 
    
   - 如果提供*重命名*属性，然后*重命名*文件复制到值中提供的重命名属性。 这用于创建 v64.cab 和 v32.cab 文件的顶级默认值。 这些是重命名顶级生成 cab 文件的版本，并将用作默认安装版本，如果未指定版本。 
    
   - 使用 URL + relativePath + 文件名来构造的 CDN 的位置。
    
以下是使用每月的通道示例 (由定义`<baseURL>`节点) 和内部版本 16.0.4229.1004 从 releasehistory.xml。 
  
```xml
<baseURL branch="Monthly" URL="http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" />
```

- 下面是所需的所有语言的语言中性文件。 文件的名称是 v64_16.0.4229.1004.cab，它应从复制`http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab`和重命名为`…/office/data/v64.cab`。 
    
  ```xml
  <File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/>
  
  ```

- 下面是指定的语言的 LCID 要包含在 EN-US 图像文件 = 1033年。 文件的名称是 s641033.cab，它应从复制`http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab`，并且不重命名。
    
  ```xml
  <File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" />
  ```

### <a name="hash-verification-of-dat-files"></a>.Dat 文件的哈希验证

图像创建工具可能与提供的每个.dat 文件相关联的哈希值计算哈希值进行比较，来确认下载的.dat 文件的完整性。 以下是从内部版本 16.0.4229.1004 和语言设置为保加利亚语的每月通道.dat 文件的示例：
  
```xml
<File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"/>
```

- **HashLocation**属性指定 stream.x64.bg bg.dat 文件 stream.x64.bg bg.hash 相对路径的位置。 通过将 URL + relativePath + hashLocation 构造的哈希文件位置。 在以下示例中，将为 stream.x64.bg bg.hash 位置： 
    
  ```http
  http://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- **HashAlgo**属性指定使用哪种哈希算法。 在这种情况下使用 Sha256。 
    
  若要验证 stream.x64.bg bg.dat 文件的完整性，请打开 stream.x64.bg bg.hash 并读取即哈希文件中的文本的第一行的哈希值。 这与计算哈希值 （使用指定的哈希算法） 验证下载的.dat 文件的完整性。
    
  下面的示例演示的 C# 代码读取哈希值。
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="office-365-client-updates"></a>Office 365 客户端更新

所有 Office 365 客户端更新都发布到[Microsoft Update 目录](http://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)。
  
Office 365 客户端更新启用可管理性软件非常类似于有一个例外; 任何其他 WU 更新方式处理 Office 365 客户端更新客户端更新不包含实际负载。 Office 365 客户端更新不应在任何客户端上安装但而不显示用于的触发的工作流与可管理性软件的安装命令替换 COM 基于安装机制如上所示。 
  
**下图显示了 Office 365 客户端更新工作流的图表。**

![O365PP 客户端更新的工作流示意图。](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "O365PP 客户端更新的工作流示意图")
  
每个 Office 365 客户端更新发布包括有关更新的元数据。 此元数据包括参数调用*MoreInfoUrl*可用于派生的以下信息： 
  
-  *版本*： 标识与此更新关联的 Office 版本。 
    
-  *分支*： 标识更新通道的此更新。 值 Broad 包括 InsiderFast、 内部人员、 每月、 目标。 可能将来添加其他值。 
    
-  *弧*： 标识与此更新关联的处理器体系结构。 
    
-  *xmlVer*: XML 文件列表中，应使用构造基图像此更新的版本。 
    
-  *xmlPath*: OFL 路径。列出其包含的 XML 文件的 CAB 文件。 
    
-  *mlFile*： 应将用于此更新文件列表的名称。 此值将是 O365Client_32bit 或 O365Client_64bit，并且将匹配弧。 
    
下面的 URL 是 office 的指 32 位版本上当前信道 16.0.2342.2343 生成版本与 Office 365 客户端更新版本*MoreInfoURL*参数的示例。 
  
http://officecdn.microsoft.com/pr/wsus/ofl.cab此更新，专门 O365Client_32bit.xml 从 OFL 中的 XML 文件列表的位置。CAB。
  
[Office 365 客户端更新通道版本](http://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=http://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml)
  
### <a name="additional-metadata-for-automating-content-staging"></a>用于自动执行内容暂存的其他元数据

除了发布的元数据的那里定义还其他 XML 文件发布到 CDN 的可帮助提供有关 Office CDN 中可用的 Office 365 客户端的其他信息。
  
**SKU。XML**
  
签名 CAB 中包含此 XML 文件并将其发布到 Office CDN 的以下 url: [http://officecdn.microsoft.com/pr/wsus/skus.cab](http://officecdn.microsoft.com/pr/wsus/skus.cab)。
  
发布此 XML 文件中的元数据可用于确定可供部署哪些产品和服务从 Office CDN 以及每个的各种选项。 
  
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

** \<ReleaseInfo\>** 根节点包含 PublishedDate 属性，它标识发布此文件的日期。 
  
** \<SKU\>** 节点标识单个 SKU。 
  
- *ProductID*属性标识如果使用 ODT 作为 configuration.xml 中的 ID 属性传递的 ID。 例如，`<Product ID="O365ProPlusRetail">`。 
    
- 如果*默认*属性设置为 true 时，标识建议的 SKU。 
    
**\<应用程序\>** 节点用于定义的每个 SKU 支持单个 Office 应用程序。 
  
- *Name*属性是显示应用程序名称。 
    
- *AppID*属性为 ID 属性中的 configuration.xml 传递**\<ExcludeApp\>** 如果使用 ODT 节点。 例如，`<ExcludeApp ID="Publisher" />`。 
    
**RELEASEHISTORY。XML**
  
签名 CAB 中包含此 XML 文件并将其发布到 Office CDN 的以下位置： [http://officecdn.microsoft.com/pr/wsus/releasehistory.cab](http://officecdn.microsoft.com/pr/wsus/releasehistory.cab)。 
  
发布此 XML 文件中的元数据可用于确定支持哪些通道服务以及生成历史记录信息的受支持的通道的每个 Office CDN 中的更新。
  
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

** \<ReleaseHistory\>** 根节点包含 PublishedDate 属性，它标识发布此文件的日期。 
  
** \<UpdateChannel\>** 节点定义的受支持的通道。 
  
- *Name*属性定义了用来传递给中作为通道属性 configuration.xml ODT 通道 ID。 
    
  示例：`<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Current">` 
    
  > [!NOTE] 
  > 此属性已被弃用并且用于向后兼容性。 使用来代替名称属性的 ID 属性。 
    
- *ID*属性定义了用来传递给中作为通道属性 configuration.xml ODT 通道 ID。 
    
  示例：`<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Deferred">` 
    
- **DisplayName**属性用作显示名称。 
    
**\<更新\>** 节点用于定义已发布的特定频道的每个更新。 
  
- **最新**属性，如果设置为 True，定义为该频道的最新版本的发行版。 
    
- **Version**属性定义此特定的更新的版本号。 
    
- **LegacyVersion**属性定义此特定更新完整的版本号。 
    
- **构建**属性定义此特定更新内部版本号。 
    
- **PubTime**属性定义的日期和时间 Office CDN 中发布此更新的频率。 
    

