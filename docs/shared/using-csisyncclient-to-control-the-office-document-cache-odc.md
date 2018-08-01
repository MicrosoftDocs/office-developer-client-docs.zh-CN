---
title: 使用 CSISyncClient 控制 Office 文档缓存 (ODC)
manager: soliver
ms.date: 07/13/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 394b8e6f-9132-4c98-8fd6-46ad3c871440
description: 了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。
ms.openlocfilehash: adaa56bf040889bd8220506bcfab8fdb0b7ab6c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779601"
---
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a>使用 CSISyncClient 控制 Office 文档缓存 (ODC)

了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。
  
CSISyncClient 是允许 Microsoft OneDrive 以控制行为的 Office 文档缓存 (ODC) 进程出 COM 服务器 (CsiSyncClient.exe)。 例如，OneDrive 可以调用 CSISyncClient 上载和下载文件，与 MS-FSSHTTP 启用终结点通过 ODC。 这样，高级的服务备份 Office 中的功能，如共同创作和无缝切换从脱机到 online。
  
CsiSyncClient 位于 Office 桌面 （x86 和 x64）。 注意： 时较新版本的 Office 可能附带 CsiSyncClient，过程将用于向后兼容性。 CsiSyncClient 接口和控制 ODC 方法将在将来更改版本的 Office。
  
当前设置的类 ID，只响应 OneDrive。
  
COM 对象是为进程出 COM 服务器可用，并在 CsiSyncClient.exe 运行。 由于限制访问 （它使用 ODC），它附带的 Office 中，因此 x64 Office 意味着 x64 位键入 COM 对象或 x86 Office 意味着 x86 COM 对象。 若要解决此限制，如一部分 CoCreateInstance 会为允许占用兼容性出进程 COM 服务器托管的 COM 对象指定 CLSCTX_LOCAL_SERVER。
  
## <a name="interfaces"></a>接口

CSISyncClient 使用以下接口。
  
### <a name="interface-ilsclocalsyncclient"></a>接口 ILSCLocalSyncClient

这是用于同步文件在 Office 中的主要接口。
  
- ProgID: Office.LocalSyncClient
- CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}
- 类型库: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}
   
已公开的 COM 对象用作出进程服务器。 指定作为一部分 CoCreateInstance CLSCTX_LOCAL_SERVER 允许 64 位和 32 位进程之间的兼容性。
  
一旦共同创建 COM 对象，您必须首先调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 。 一旦[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)已成功完成，您可能会调用任何 API，通常可以您希望和按任意顺序。 您可能已初始化的对象上调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) ，但这不执行任何操作。 
  
上一段的例外是[ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)和[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 COM 对象上调用[ILSCLocalSyncClient::Uninitialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)之后，您必须销毁对象，并创建一个新。 [ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)将删除您 subcache，删除该缓存中的所有关联的文件信息，但在磁盘上保留文档。 它还退出状态用于与缓存通信保持不变。 这样，您可以调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)再次以创建新的缓存，而无需销毁并重新创建该 COM 对象。 
  
**公共成员函数**

#### <a name="ilsclocalsyncclientdeletefile"></a>ILSCLocalSyncClient::DeleteFile

DeleteFile 用于从缓存中删除的文件信息。 但是，此方法将保留关联的文件在磁盘上和在服务器上。
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识文件的资源 Id 字符串。 此值必须为非空最多为 128 个字符。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |给定的 ResourceID 不在缓存中。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |初始化尚未成功调用过去。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |文件当前正在同步或打开，无法删除。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a>ILSCLocalSyncClient::GetChanges
<a name="ILSCLocalSyncClient_GetChanges"> </a>

GetChanges 返回 ILSCEvent 对象的枚举，并返回其授予对下次调用 GetChanges，假定使用者已经处理前一组事件的令牌。 指定_nPreviousChangesToken_之前的事件都将被删除，而且不可用。 如果没有处理的事件， _pnCurrentChangesToken_应_nPreviousChangesToken_，相同的值，但_ppiEvents_仍将被设置。 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a>参数

 _nPreviousChangesToken_
  
标识的使用者上次处理的事件。 
  
 _pnCurrentChangesToken_
  
标识要传递给使用者的最新事件。 不得为空。
  
 _ppiEvents_
  
传递给使用者的事件枚举。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a>ILSCLocalSyncClient::GetClientNetworkSyncPermission

GetClientNetworkSyncPermission 用于查询是否 for Office 的同步启发网络成本和电源使用被重写。 当在 3g 或其他跟踪成本很高网络，或在与要插入的电池上运行时，可以选择 Office 之前多此时阻止网络通信。
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a>参数

 _nspType_
  
一个查询中定义的成本推断方法的标志。 请参阅[枚举 LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。 
  
 _pfSyncEnabled_
  
指定是否请求的成本推断方法当前重写或不。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a>ILSCLocalSyncClient::GetFileStatus

GetFileStatus 用于收集特定文件的信息： 它具有挂起的通信与服务器副本中，如果存在在缓存中，还是 Office 2013 具有充分最多的本地副本的日期数据。 需要[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)值来确定 CsiSyncClient COM 对象为哪些信息的按位标志查询。 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
一个字符串，用于标识客户端上的文件。 此值必须为非空，最多为 128 个字符。 
  
 _sfRequestedStatus_
  
一个标志它定义要返回的信息。 请参阅[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
 _pbstrFileSystemPath_
  
该字符串标识标识_bstrResourceID_客户端上的文件的位置。 不得为空。 
  
 _pbstrETag_
  
一个字符串，其中将包含由_bstrResourceID_标识的文件的 eTag。 不得为空。 
  
 _psfFileStatus_
  
将包含通过由_bstrResourceID_标识文件_sfRequestedStatus_请求的状态标志。 不得为空。 请参阅[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |在缓存中不存在_bstrResourceID_由指定的文件信息。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |请求 LSCStatusFlag_LocalFileUnchanged 或_bstrResourceID_指定的文件已锁定或丢失。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a>ILSCLocalSyncClient::GetSupportedFileExtensions
<a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a>

GetSupportedFileExtensions 返回当前受支持的 CsiSyncClient COM 对象的管道分隔的文件扩展名的列表。 请注意，此列表可能会更改，并使用者将通过[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (请参阅 EventOccured) 中提供的 IPartnerActivityCallback 对象更改的通知。 
  
字符串的示例返回如下所示:"| docx | docm | pptx |"
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a>参数

 _pbstrSupportedFileExtensions_
  
要设置与一组管道分隔 CsiSyncClient COM 对象支持的文件扩展名的字符串。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a>ILSCLocalSyncClient::Initialize
<a name="ILSCLocalSyncClient_Initialize"> </a>

初始化必须是第一种方法调用。 否则，所有其他 Api 将返回 E_LSC_NOTINITIALIZED。 已初始化对象上调用 Initialize，则返回 S_OK 和不执行任何操作。 如果返回 E_LSC_CACHEMISMATCH，呼叫者可能会调用[ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)删除与给定 SuppliedID 关联的缓存。 但是，在这种情况下其他 Api 仍将返回 E_LSC_NOTINITIALIZED。 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a>参数

 _bstrSuppliedID_
  
标识使用者和其缓存使用。 非空值必须为最多 32 个字符。 
  
 _bstrProgID_
  
标识双向通信使用者的 COM 的对象。 非空值必须为最多为 39 个字符。 请参阅[\<ProgID\>键](http://msdn.microsoft.com/en-us/library/ms690196.aspx.aspx)的 Progid 的详细信息。 
  
 _bstrFileSystemDirectoryHint_
  
标识将在其中存储的本地文件的根目录。 非空值必须为最多包含 256 个字符。 目录必须已经存在。 
  
 _pEventCallback_
  
更改将通知 CsiSyncClient 回调接口。 请参阅 IPartnerActivityCallback::EventOccurred。 此值不为 null。 
  
 _pfCreatedNewCache_
  
返回一个新的缓存是否已创建。 如果没有缓存与 SuppliedID 关联，将创建一个。 此值不为 null。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_CACHEMISMATCH  <br/> |SuppliedID 已具有与其关联的缓存，但具有不同的 ProgId 或 FileSystemDirectoryHint 比提供。  <br/> |
|E_LSC_DIRECTORYHINTCONFLICT  <br/> |FileSystemDirectoryHint （或子文件夹） 不同缓存上已存在。  <br/> |
|E_LAC_PROGIDCONFLICT  <br/> |不同缓存上已存在 ProgID。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a>ILSCLocalSyncClient::LocalFileChange
<a name="ILSCLocalSyncClient_LocalFileChange"> </a>

LocalFileChange 用于告知 CsiSyncClient COM 对象，以尝试上载指定的文件。 该方法将准备上载，包括读取文件的当前内容的文件。 如果上载已挂起，将放弃上次上载并准备好的新内容上载。 如果文件已打开，在应用程序中进行编辑，此方法将返回 S_OK 而不准备的上载 （应用程序应该已执行此步骤时更改） 的文件。
  
此方法将允许上载如果它被标记为上载被阻止之前 （请参阅[ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)）。
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrFileSystemPath_
  
一个字符串，用于标识客户端上的文件。 此值必须是最多包含 256 个字符的非空本地路径。 此路径必须是由 FileSystemDirectoryHint 时进行[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)调用指定目录树中。 
  
 _bstrResourceID_
  
标识文件的资源 Id 字符串。 此值必须为非空最多为 128 个字符。 
  
 _bstrWebPath_
  
一个字符串，用于标识的服务器上的文件。 此值必须为非空、 有效的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_BstrFileSystemPath_指定的文件具有不同的资源 Id 与指定。 类型的事件，则返回此错误时，会发送 LSCEventType_OnFilePathConflict。 请参阅[ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |文件已删除的中端操作。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |由 CsiSyncClient COM 对象不支持的给定的文件扩展名。 请参阅[ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。  <br/> |
|E_LSC_FILEUPTODATE  <br/> |COM 对象未安排上载，因为在缓存中的文件从磁盘的最新更改。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |缺失或被锁定， _bstrFileSystemPath_指定的文件。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_BstrResourceID_指定的文件具有不同 FileSystemPath 比指定。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件已具有挂起的不同缓存中的更改，并且尚未不能与使用者的缓存。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供 WebPath 低于其他的缓存。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a>ILSCLocalSyncClient::RenameFile
<a name="ILSCLocalSyncClient_RenameFile"> </a>

RenameFile 将为给定的资源 Id 关联的新 URL 和本地路径。 如果资源 Id 指定的文件不存在在缓存中，将进行尝试创建并将其标记为下载。
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识文件的资源 Id 字符串。 此值必须为非空最多为 128 个字符。 
  
 _bstrNewFileSystemPath_
  
一个字符串，用于指定文件的新本地路径。 此值必须是最多包含 256 个字符的非空本地路径。 此路径必须是由 FileSystemDirectoryHint 进行初始化通话时指定目录树中。 
  
 _bstrNewWebPath_
  
一个指定文件的新 URL 的字符串。 此值必须为非空有效的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。 
  
 _fBlockUploads_
  
指定是否当前允许文件将上载到新位置。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_BstrNewFileSystemPath_或_bstrNewWebPath_已经存在任何缓存中的另一个文件。 类型的事件，则返回此错误时，会发送 LSCEventType_OnFilePathConflict。 请参阅[ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |运行此方法时，从缓存中已删除的文件信息。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件当前 Office 应用程序中进行同步。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a>ILSCLocalSyncClient::ResetCache
<a name="ILSCLocalSyncClient_ResetCache"> </a>

ResetCache 将删除与已提供在初始化 SuppliedID 关联的缓存。 这包括的所有文件信息，但将保留在客户端和服务器上的文件。 此方法还使处于部分未初始化的状态的对象。 唯一有效呼叫后这是[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)或[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 如果初始化失败并返回 E_LSC_CACHEMISMATCH，可能会调用此方法将删除与已附带的失败呼叫 SuppliedID 关联的缓存。
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a>参数

无
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |在过去未成功调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a>ILSCLocalSyncClient::ServerFileChange
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

ServerFileChange 告知 CsiSyncClient COM 对象标记指定的文件进行下载。 编辑 Office 应用程序中打开该文件时，此方法将返回 S_OK 而不将标记 （应用程序应该已执行此步骤时更改） 下载的文件。
  
此方法将允许下载如果它被标记为下载阻止以前 （请参阅 RenameFile）。
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

|参数|说明|
|:-----|:-----|
|bstrFileSystemPath  <br/> |一个字符串，用于标识客户端上的文件。 此值必须是最多包含 256 个字符的非空本地路径。 此路径必须是由 FileSystemDirectoryHint 进行初始化通话时指定目录树中。  <br/> |
|bstrResourceID  <br/> |标识文件的资源 Id 字符串。 此值必须为非空最多为 128 个字符。  <br/> |
|bstrWebPath  <br/> |一个字符串，用于标识的服务器上的文件。 此值必须是有效的非空的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。  <br/> |
   
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |未能设置缓存连接状态。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_BstrFileSystemPath_指定的文件具有不同的资源 Id 与指定。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |由 CsiSyncClient COM 对象不支持的给定的文件扩展名。 请参阅 GetSupportedFileExtensions。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |中间操作中已删除文件。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_BstrResourceID_指定的文件具有不同 FileSystemPath 比指定。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件已具有挂起的不同缓存中的更改，并且尚未不能与使用者的缓存。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供 WebPath 低于其他的缓存。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a>ILSCLocalSyncClient::SetClientConnectivityState
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

将缓存设置为联机或脱机状态。 如果脱机，Office 将尝试与该缓存，而不考虑每个单独的文件_fBlockUploads_设置中的任何文件的服务器进行通信。 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a>参数

 _fIsOnline_
  
确定连接状态的缓存的布尔值。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |未能设置缓存连接状态。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a>ILSCLocalSyncClient::SetClientNetworkSyncPermission
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

是重写用于 SetClientNetworkSyncPermission 或 restoreOffice 的同步启发的网络成本和电源使用率。 当在 3g 或其他跟踪成本很高网络，或在与要插入的电池上运行时，可以选择 Office 之前多此时阻止网络通信。 此 API 的使用者可以使用它覆盖 Office 的启发并强制同步发生。
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a>参数

 _nspType_
  
它定义重写的成本推断方法的标志。 请参阅[枚举 LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。
  
 _fEnableSync_
  
指定是否强制执行同步上，因此重写该成本推断方法，或不再重写。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |重写同步试探方法失败。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a>ILSCLocalSyncClient::Uninitialize
<a name="ILSCLocalSyncClient_Uninitialize"> </a>

卸载从的 COM 对象缓存，并执行结束操作。 [ILSCLocalSyncClient::Uninitialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)必须在销毁 COM 对象之前调用。 调用后，可调用任何其他 Api、 COM 对象必须销毁和创建一个新的如果想要继续操作。 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |取消初始化失败。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
### <a name="interface-ienumlscevent"></a>接口 IEnumLSCEvent

此接口表示 ILSCEvent 事件的列表。
  
**公共成员函数**

#### <a name="ienumlsceventfnext"></a>IEnumLSCEvent::FNext

从的事件列表中检索下一个事件。
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a>参数

 _ppiLSCEvent_
  
指向 ILSCEvent 接口的指针。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |没有详细事件。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ienumlsceventreset"></a>IEnumLSCEvent::Reset

将枚举器重重置为第一个事件。
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
### <a name="interface-ilscevent"></a>接口 ILSCEvent

此接口表示同步事件。 可以从界面检索有关事件的所有信息。
  
**公共成员函数**

#### <a name="ilsceventgetconflictstatus"></a>ILSCEvent::GetConflictStatus

注意，此值填充[ILSCLocalSyncClient::GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)调用时，不时事件的创建，以便您只具有该文件，不文件冲突状态更改时的状态的当前状态。 
  
事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnLocalConflictStateChanged 时，仅将填充此值。 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a>参数

 _pfIsInConflict_
  
与事件关联的文件的冲突当前状态。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgeterror"></a>ILSCEvent::GetError

此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a>参数

 _pnError_
  
与该事件关联的错误。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetetag"></a>ILSCEvent::GetETag

此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a>参数

 _pbstrETag_
  
与此事件关联的 ETag
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgeteventtype"></a>ILSCEvent::GetEventType

获取该事件的类型。
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a>参数

 _pnEventType_
  
此事件的事件类型。 有效的值，请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a>ILSCEvent::GetLocalWorkingPath

获取此事件的本地工作路径。
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a>参数

 _pbstrLocalWorkingPath_
  
此事件与相关文件的本地路径。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetresourceid"></a>ILSCEvent::GetResourceID

获取事件的资源 ID。
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a>参数

 _pbstrResourceID_
  
与此事件关联的文件的资源 Id。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetresourceidattempted"></a>ILSCEvent::GetResourceIDAttempted

事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnFilePathConflict 时，仅将填充此值。 调用[ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient::ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient::RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)与另一个文件置于 Office 文件缓存中，会导致 Web 路径或本地路径冲突时这生成事件。 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a>参数

 _pbstrResourceIDAttempted_
  
ResourceID 导致获取生成该事件。 不得为空。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetsyncerrortype"></a>ILSCEvent::GetSyncErrorType

此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a>参数

 _pnSyncErrorType_
  
与该事件关联的错误类型。 潜在的值，请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数均无效。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ilsceventgetwebpath"></a>ILSCEvent::GetWebPath

事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnFilePathConflict 时，仅将填充此值。 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a>参数

 _pbstrWebPath_
  
指定与此事件关联的 Web 路径。 不得为空。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
### <a name="interface-ilscevent2"></a>接口 ILSCEvent2

此接口包含有关同步事件的其他信息。
  
**公共成员函数**

#### <a name="ilscevent2geterrorchain"></a>ILSCEvent2::GetErrorChain

获取有关同步事件链错误信息。
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a>参数

 _pbstrErrorChain_
  
要保留错误链信息的字符串。 不得为空。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_NOTIMPL  <br/> |安装的 Office 版本不支持此接口  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数值是无效。  <br/> |
|E_FAIL  <br/> |错误链信息不可用。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a>接口 IPartnerActivityCallback

此接口提供对 CSISyncClient COM 对象的回调函数。
  
**公共成员函数**

#### <a name="ipartneractivitycallbackeventoccurred"></a>IPartnerActivityCallback::EventOccurred

这是分配给 CsiSyncClient COM 对象的对象上的回调函数。 预计事件发生时 （请参阅为有效的事件类型的[枚举 LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) ），CsiSyncClient COM 对象将调用此方法时，信号使用者。 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a>参数

 _eEventTypeOccurred_
  
此事件的事件类型。 有效的值，请参阅[枚举 LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。
  
## <a name="enumerations"></a>枚举

CSISyncClient 使用将下列枚举。
  
### <a name="enum-lsceventsyncerrortype"></a>枚举 LSCEventSyncErrorType
<a name="Enum_LSCEventSyncErrorType"> </a>

此枚举指定类别的文件同步时可能出现的错误。
  
|枚举|说明|
|:-----|:-----|
|LSCEventSyncErrorType_UserInterventionRequiredUnexpected  <br/> |此事件的同步错误是意外，并且可能需要特殊的注意事项。 默认情况下，用户可能需要介入。  <br/> |
|LSCEventSyncErrorType_NoInterventionRequired  <br/> |此事件的同步错误不需要特殊的注意事项。 Office 将自动处理。  <br/> |
|LSCEventSyncErrorType_UserInterventionRequired  <br/> |此事件的同步错误要求用户解决。 例如，合并冲突错误要求用户在打开文档并将其合并。  <br/> |
|LSCEventSyncErrorType_WaitingOnClient  <br/> |此事件的同步错误需要使用者进行干预，但应不需要用户的特殊注意事项。  <br/> |
|LSCEventSyncErrorType_ClientInterventionRequired  <br/> |此事件的同步错误需要使用者的特殊情况介入。  <br/> |
|LSCEventSyncErrorType_Max  <br/> ||
   
### <a name="enum-lsceventtype"></a>枚举 LSCEventType
<a name="Enum_LSCEventType"> </a>

此枚举指定特定文件可能会发生的事件的类型。
  
|枚举|说明|
|:-----|:-----|
|LSCEventType_None  <br/> ||
|LSCEventType_OnLocalChanges  <br/> |对本地文件进行更改。  <br/> |
|LSCEventType_OnOpenedByUser  <br/> |用户打开文件。  <br/> |
|LSCEventType_OnServerChangesDownloaded  <br/> |完成从服务器下载文件的更改。  <br/> |
|LSCEventType_OnLocalChangesUploaded  <br/> |完成上载到服务器的文件的更改。  <br/> |
|LSCEventType_OnLocalConflictStateChanged  <br/> |合并冲突状态的文件已更改。  <br/> |
|LSCEventType_OnFileAdded  <br/> |添加了一个文件。  <br/> |
|LSCEventType_OnFileDeleted  <br/> |已删除文件。  <br/> |
|LSCEventType_OnSyncEnabled  <br/> |同步已启用的用户的文件。  <br/> |
|LSCEventType_OnServerChangesDownloadStarted  <br/> |启动从服务器下载文件的更改。  <br/> |
|LSCEventType_OnLocalChangesUploadStarted  <br/> |启动文件更改上载到服务器。  <br/> |
|LSCEventType_OnFilePathConflict  <br/> |此事件时调用[ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)， [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)，生成或[ILSCLocalSyncClient::RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)与另一个文件导致 Web 路径或本地路径冲突Office 文件缓存。  <br/> |
|LSCEventType_OnFileForked  <br/> ||
|LSCEventType_Max  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a>枚举 LSCEventTypeOccurred
<a name="Enum_LSCEventTypeOccurred"> </a>

此枚举指定可能发生的事件的类型。 使用者需要调用基于事件类型的特定 ILSCLocalSyncClient 函数。
  
|枚举|说明|
|:-----|:-----|
|LSCEventTypeOccurred_GetChanges  <br/> |发生 ILSCEvent。 使用者应调用[ILSCLocalSyncClient::GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)检索数据。  <br/> |
|LSCEventTypeOccurred_GetSupportedFileExtensions  <br/> |已更改的受支持的文件扩展名。 使用者应调用[ILSCLocalSyncClient::GetSupportedFileExtensions](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)检索新的受支持的扩展名列表。  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a>枚举 LSCNetworkSyncPermissionType
<a name="Enum_LSCNetworkSyncPermissionType"> </a>

此枚举指定用于网络成本推断方法的标志。 

|枚举|说明|
|:-----|:-----|
|LSCNetworkSyncPermissionType_HighCost  <br/> |如果昂贵网络 （如 3g) 的成本推断方法将被覆盖，则为 true。  <br/> |
|LSCNetworkSyncPermissionType_HighPowerUsage  <br/> |如果 （如电池） 的电源使用成本推断方法将被覆盖，则为 true。  <br/> |
   
### <a name="enum-lscstatusflag"></a>枚举 LSCStatusFlag
<a name="Enum_LSCStatusFlag"> </a>

此枚举用于表示文件的同步状态。 
  
|枚举|说明|
|:-----|:-----|
|LCSStatusFlag_None  <br/> ||
|LSCStatusFlag_UploadPending  <br/> |如果没有挂起的数据发送到服务器文件，则为 true。  <br/> |
|LSCStatusFlag_DownloadPending  <br/> |如果没有待处理的要从服务器文件下载的数据，则为 true。  <br/> |
|LSCStatusFlag_LocalFileUnchanged  <br/> |如果数据 Office 具有其缓存中的文件，则磁盘上的数据的最新副本。  <br/> |
   

