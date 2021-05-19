---
title: '使用 CSISyncClient 控制 ODC Office文档 (缓存) '
manager: soliver
ms.date: 07/13/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 394b8e6f-9132-4c98-8fd6-46ad3c871440
description: 了解如何使用 CSISyncClient 控制 ODC Office缓存 (缓存) 。
ms.openlocfilehash: ce33063f88492bcd6f9682a4a6431fb36f138d55
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346254"
---
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a>使用 CSISyncClient 控制 ODC Office文档 (缓存) 

了解如何使用 CSISyncClient 控制 ODC Office缓存 (缓存) 。
  
CSISyncClient 是一个非 proc COM (CsiSyncClient.exe) ，它允许 Microsoft OneDrive 控制 Office 文档缓存 (ODC) 的行为。 例如，OneDrive通过 CSISyncClient 调用 ODC，将文件上载和下载至启用了 MS-FSSHTTP 的终结点和从这些终结点下载文件。 这样一来，Office支持高级服务的功能，例如共同创作和从脱机到联机的无缝转换。
  
CsiSyncClient 适用于 Office 桌面 (x86 和 x64) 。 注意：虽然更高版本的 Office可能会随 CsiSyncClient 一起提供，但该过程将仅用于向后兼容。 CsiSyncClient 接口和控制 ODC 的方法将在未来版本的 odC 中Office。
  
课程 ID 当前设置为仅响应OneDrive。
  
COM 对象可以用作非 proc COM 服务器，并运行在 CsiSyncClient.exe。 由于 ODC 使用) Office 的 Access (存在限制，因此 x64 Office 表示 x64 COM 对象，x86 Office 表示 x86 COM 对象。 要绕开此限制，将 CLSCTX_LOCAL_SERVER指定为 CoCreateInstance 的一部分将 COM 对象作为非 proc COM 服务器托管，从而允许跨位兼容性。
  
## <a name="interfaces"></a>接口

CSISyncClient 使用下列接口。
  
### <a name="interface-ilsclocalsyncclient"></a>接口 ILSCLocalSyncClient

这是用于同步文件中文件的主要Office。
  
- ProgID：Office。LocalSyncClient
- CLSID：{14286318-B6CF-49a1-81FC-D74AD94902F9}
- TypeLib：{66CDD37F-D313-4e81-8C31-4198F3E42C3C}
   
公开的 COM 对象用作非 proc 服务器。 将 CLSCTX_LOCAL_SERVER CoCreateInstance 允许 64bit 和 32bit 进程之间的可共存性。
  
共同创建 COM 对象后，必须先调用[ILSCLocalSyncClient：：Initialize。](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) [ILSCLocalSyncClient：：Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)成功完成后，你可任意按需要经常调用任何 API。 还可以对已初始化的对象调用 [ILSCLocalSyncClient：：Initialize， ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 但此操作不执行任何操作。 
  
上一段落的例外情况是 [ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 和 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 在 COM 对象上调用 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) 后，必须销毁该对象并创建一个新对象。 [ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 将删除子缓存、删除缓存中所有关联的文件信息，但将文档保留磁盘上。 它还保持与缓存通信的状态不变。 这允许你再次调用 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 以创建新缓存，而无需销毁并重新创建 COM 对象。 
  
**公共成员函数**

#### <a name="ilsclocalsyncclientdeletefile"></a>ILSCLocalSyncClient：:D eleteFile

DeleteFile 用于从缓存中删除文件信息。 但是，此方法将关联的文件保留磁盘上和服务器上。
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识文件的 ResourceID 的字符串。 此值必须非空，最多为 128 个字符。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |给定的 ResourceID 不在缓存中。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |过去未成功调用 Initialize。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |文件当前正在同步或打开，无法删除。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a>ILSCLocalSyncClient：：GetChanges
<a name="ILSCLocalSyncClient_GetChanges"> </a>

GetChanges 返回 ILSCEvent 对象的枚举器，并返回一个令牌，该令牌将给予对 GetChanges 的下一个调用（假设使用者已处理上一组事件）。 指定的  _nPreviousChangesToken_ 之前的事件将被删除且不可用。 如果没有要处理的事件 _，pnCurrentChangesToken_ 的值应该与 _nPreviousChangesToken_ 相同，但仍将设置 _ppiEvents。_ 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a>参数

 _nPreviousChangesToken_
  
标识使用者上次处理的事件。 
  
 _pnCurrentChangesToken_
  
标识要交给消费者的最新事件。 不得为 null。
  
 _ppiEvents_
  
向消费者提供的事件的枚举器。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a>ILSCLocalSyncClient：：GetClientNetworkSyncPermission

GetClientNetworkSyncPermission 用于查询Office网络成本和电源使用情况的同步启发是否被覆盖。 当使用 3G 或其他高成本网络时，或者当使用电池运行与插入时，Office可能会选择阻止网络流量，直到更适当的时间。
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a>参数

 _nspType_
  
定义要查询的成本启发式标记。 请参阅 [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。 
  
 _pfSyncEnabled_
  
指定当前是否覆盖请求的成本启发。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a>ILSCLocalSyncClient：：GetFileStatus

GetFileStatus 用于收集特定文件的信息：它是否位于缓存中、它是否具有与服务器副本的挂起通信，以及 Office 2013 具有本地副本中最新数据。 它需要 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag) 值的位标志来确定 CsiSyncClient COM 对象要查询的信息。 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识客户端上的文件的字符串。 此值必须非空，最多为 128 个字符。 
  
 _sfRequestedStatus_
  
定义要返回的信息的标志。 请参阅 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
 _pbstrFileSystemPath_
  
标识由  _bstrResourceID_ 标识的文件在客户端上的位置的字符串。 不得为 null。 
  
 _pbstrETag_
  
一个字符串，其中包含由  _bstrResourceID_ 标识的文件的 eTag。 不得为 null。 
  
 _psfFileStatus_
  
一个标志，其中包含通过  _sfRequestedStatus_ 为  _bstrResourceID_ 标识的文件请求的状态。 不得为 null。 请参阅 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |_bstrResourceID_ 指定的文件信息在缓存中不存在。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |LSCStatusFlag_LocalFileUnchanged请求，或者  _bstrResourceID_ 指定的文件已锁定或丢失。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a>ILSCLocalSyncClient：：GetSupportedFileExtensions
<a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a>

GetSupportedFileExtensions 返回由管道分隔的文件扩展名的列表，这些扩展名当前受 CsiSyncClient COM 对象支持。 请注意，此列表可能会更改，并且将通过 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 上提供的 IPartnerActivityCallback 对象通知使用者 (EventOccured) 。 
  
返回的字符串示例如下："|docx|docm|pptx|"
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a>参数

 _pbstrSupportedFileExtensions_
  
使用 CsiSyncClient COM 对象支持的一组通过管道分隔的文件扩展名设置的字符串。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a>ILSCLocalSyncClient：：Initialize
<a name="ILSCLocalSyncClient_Initialize"> </a>

Initialize 必须是第一个调用的方法。 否则，所有其他 API 将返回E_LSC_NOTINITIALIZED。 对已初始化的对象调用 Initialize 将返回 S_OK，并且不执行任何操作。 如果E_LSC_CACHEMISMATCH，则调用方可能调用 [ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 以删除与给定 SuppliedID 关联的缓存。 但是，在这种情况下，其他 API 仍将返回E_LSC_NOTINITIALIZED。 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a>参数

 _bstrSuppliedID_
  
标识使用者以及要使用哪个缓存。 必须非空，最多 32 个字符。 
  
 _bstrProgID_
  
标识用于双向通信的使用者的 COM 对象。 必须非空，最多 39 个字符。 有关[ \< ProgID \> 的信息，请参阅 ProgID](https://docs.microsoft.com/windows/desktop/com/-progid--key)密钥。 
  
 _bstrFileSystemDirectoryHint_
  
标识将存储本地文件的目录根目录。 不得为空，最多为 256 个字符。 目录必须已经存在。 
  
 _pEventCallback_
  
CsiSyncClient 将在更改时通知的回调接口。 请参阅 IPartnerActivityCallback：：EventOccurred。 此值不能为 null。 
  
 _pfCreatedNewCache_
  
返回是否已创建一个新缓存。 如果没有与 SuppliedID 关联的缓存，将创建一个缓存。 此值不能为 null。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CACHEMISMATCH  <br/> |SuppliedID 已具有与其关联的缓存，但 ProgId 或 FileSystemDirectoryHint 与提供的缓存不同。  <br/> |
|E_LSC_DIRECTORYHINTCONFLICT  <br/> |FileSystemDirectoryHint (或子文件夹) 缓存中已存在。  <br/> |
|E_LAC_PROGIDCONFLICT  <br/> |ProgID 已存在于其他缓存中。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a>ILSCLocalSyncClient：：LocalFileChange
<a name="ILSCLocalSyncClient_LocalFileChange"> </a>

LocalFileChange 用于告诉 CsiSyncClient COM 对象尝试上载指定文件。 方法将准备文件进行上载，包括读取文件的当前内容。 如果上载已挂起，将放弃之前上载的内容，并准备新内容进行上载。 如果文件在应用程序中打开进行编辑，此方法将返回 S_OK而不准备文件上载 (如果文件发生更改，则应用程序应该已经执行) 。
  
如果之前将此方法标记为已阻止上传， ([ILSCLocalSyncClient：：RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)) 。
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrFileSystemPath_
  
标识客户端上的文件的字符串。 此值必须是最多包含 256 个字符的非空本地路径。 当调用 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 时，此路径必须位于 FileSystemDirectoryHint 指定的目录树中。 
  
 _bstrResourceID_
  
一个标识文件的 ResourceID 的字符串。 此值必须非空，最多为 128 个字符。 
  
 _bstrWebPath_
  
一个标识服务器上文件的字符串。 此值必须为非空的有效 URL，但不得超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrFileSystemPath_ 指定的文件与指定的 ResourceID 不同。 返回此错误LSCEventType_OnFilePathConflict发送类型为 LSCEventType_OnFilePathConflict 的事件。 请参阅 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |文件在操作期间被删除。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |CsiSyncClient COM 对象不支持给定的文件扩展名。 请参阅 [ILSCLocalSyncClient：：GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。  <br/> |
|E_LSC_FILEUPTODATE  <br/> |COM 对象没有计划上载，因为缓存中的文件具有来自磁盘的最新更改。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |_bstrFileSystemPath_ 指定的文件丢失或锁定。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_bstrResourceID_ 指定的文件与指定的 FileSystemPath 不同。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件已在其他缓存中具有挂起的更改，并且无法与使用者的缓存相关联。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供的 WebPath 属于不同的缓存。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a>ILSCLocalSyncClient：：RenameFile
<a name="ILSCLocalSyncClient_RenameFile"> </a>

RenameFile 将关联给定 ResourceID 的新 URL 和本地路径。 如果 ResourceID 指定的文件在缓存中不存在，将尝试创建该文件并标记为下载。
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
一个标识文件的 ResourceID 的字符串。 此值必须非空，最多为 128 个字符。 
  
 _bstrNewFileSystemPath_
  
指定文件的新本地路径的字符串。 此值必须是最多包含 256 个字符的非空本地路径。 当调用 Initialize 时，此路径必须在 FileSystemDirectoryHint 指定的目录树中。 
  
 _bstrNewWebPath_
  
指定文件的新 URL 的字符串。 此值必须为非空的有效 URL，但不超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。 
  
 _fBlockUploads_
  
指定当前是否允许上载到新位置。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrNewFileSystemPath_ 或 _bstrNewWebPath_ 已存在于任何缓存中的另一个文件上。 返回此错误LSCEventType_OnFilePathConflict发送类型为 LSCEventType_OnFilePathConflict 的事件。 请参阅 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |在此方法运行时，文件信息从缓存中删除。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件当前正在Office同步。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a>ILSCLocalSyncClient：：ResetCache
<a name="ILSCLocalSyncClient_ResetCache"> </a>

ResetCache 将删除与 Initialize 上提供的 SuppliedID 关联的缓存。 这包括所有文件信息，但文件将同时保留在服务器上和客户端上。 此方法还会使对象部分未初始化。 在此之后，唯一有效的调用是 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 或 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 如果 Initialize 失败并返回 E_LSC_CACHEMISMATCH，可能会调用此方法，并且将删除与失败调用提供的 SuppliedID 关联的缓存。
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a>参数

无
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a>ILSCLocalSyncClient：：ServerFileChange
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

ServerFileChange 指示 CsiSyncClient COM 对象标记指定的文件进行下载。 如果文件在 Office 应用程序中打开进行编辑，此方法将返回 S_OK而不将文件标记为下载 (如果文件发生更改，则应用程序应该已经执行) 。
  
如果之前将其标记为已阻止下载，此方法将允许下载 (RenameFile) 。
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

|参数|说明|
|:-----|:-----|
|bstrFileSystemPath  <br/> |标识客户端上的文件的字符串。 此值必须是最多包含 256 个字符的非空本地路径。 当调用 Initialize 时，此路径必须在 FileSystemDirectoryHint 指定的目录树中。  <br/> |
|bstrResourceID  <br/> |一个标识文件的 ResourceID 的字符串。 此值必须非空，最多为 128 个字符。  <br/> |
|bstrWebPath  <br/> |一个标识服务器上文件的字符串。 此值必须是非空的有效 URL，但不超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。  <br/> |
   
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |设置缓存连接状态失败。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrFileSystemPath_ 指定的文件与指定的 ResourceID 不同。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |CsiSyncClient COM 对象不支持给定的文件扩展名。 请参阅 GetSupportedFileExtensions。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |文件在操作期间被删除。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_bstrResourceID_ 指定的文件与指定的 FileSystemPath 不同。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件已在其他缓存中具有挂起的更改，并且无法与使用者的缓存相关联。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供的 WebPath 属于不同的缓存。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a>ILSCLocalSyncClient：：SetClientConnectivityState
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

将缓存设置为联机或脱机状态。 如果脱机Office，系统将不会尝试与该缓存中任何文件的服务器通信，而不管每个文件的 _fBlockUploads_ 设置如何。 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a>参数

 _fIsOnline_
  
确定缓存的连接状态 Boolean。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |设置缓存连接状态失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a>ILSCLocalSyncClient：：SetClientNetworkSyncPermission
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

SetClientNetworkSyncPermission 用于覆盖或还原Office 同步网络成本和电源使用情况的启发。 当使用 3G 或其他高成本网络时，或者当使用电池运行与插入时，Office可能会选择阻止网络流量，直到更适当的时间。 此 API 的使用者可以使用它替代Office启发式操作并强制同步发生。
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a>参数

 _nspType_
  
定义要覆盖的成本启发式标记。 请参阅 [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。
  
 _fEnableSync_
  
指定是强制同步，从而替代成本启发式，还是不再覆盖它。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |无法覆盖同步启发。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a>ILSCLocalSyncClient：：Uninitialize
<a name="ILSCLocalSyncClient_Uninitialize"> </a>

从 COM 对象卸载缓存并执行关闭操作。 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) 必须在销毁 COM 对象之前调用 。 调用后，如果想继续操作，则必须销毁 COM 对象并创建一个新 API。 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |无法取消初始化。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
### <a name="interface-ienumlscevent"></a>接口 IEnumLSCEvent

此接口表示 ILSCEvent 事件的列表。
  
**公共成员函数**

#### <a name="ienumlsceventfnext"></a>IEnumLSCEvent：：FNext

从事件列表中检索下一个事件。
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a>参数

 _ppiLSCEvent_
  
指向 ILSCEvent 接口的指针。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |不再有事件。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ienumlsceventreset"></a>IEnumLSCEvent：：Reset

将枚举器重置为第一个事件。
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
### <a name="interface-ilscevent"></a>接口 ILSCEvent

此接口表示同步事件。 可以从接口检索有关事件的所有信息。
  
**公共成员函数**

#### <a name="ilsceventgetconflictstatus"></a>ILSCEvent：：GetConflictStatus

请注意，此值在 [调用 ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) 时填充，而不是创建事件时填充，因此，您将只具有文件的当前状态，而不是冲突状态更改时文件的状态。 
  
此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnLocalConflictStateChanged。 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a>参数

 _pfIsInConflict_
  
与事件关联的文件的当前冲突状态。
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgeterror"></a>ILSCEvent：：GetError

此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a>参数

 _pnError_
  
与此事件关联的错误。
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgetetag"></a>ILSCEvent：：GetETag

此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a>参数

 _pbstrETag_
  
与此事件关联的 ETag
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgeteventtype"></a>ILSCEvent：：GetEventType

获取此事件的类型。
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a>参数

 _pnEventType_
  
此事件的事件类型。 有关[有效值，请参阅 Enum LSCEventType。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a>ILSCEvent：：GetLocalWorkingPath

获取此事件的本地工作路径。
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a>参数

 _pbstrLocalWorkingPath_
  
与此事件相关的文件的本地路径。 
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgetresourceid"></a>ILSCEvent：：GetResourceID

获取事件的资源 ID。
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a>参数

 _pbstrResourceID_
  
与此事件关联的文件的 ResourceID。
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgetresourceidattempted"></a>ILSCEvent：：GetResourceIDAttempted

此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnFilePathConflict。 当调用[ILSCLocalSyncClient：：LocalFileChange、ILSCLocalSyncClient：：ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)或[ILSCLocalSyncClient：：RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)将导致 Web 路径或本地路径与 Office 文件缓存中的另一个文件冲突时，将生成此事件。 [ ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange) 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a>参数

 _pbstrResourceIDAttempted_
  
导致生成此事件的 ResourceID。 不得为 null。 
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
#### <a name="ilsceventgetsyncerrortype"></a>ILSCEvent：：GetSyncErrorType

此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a>参数

 _pnSyncErrorType_
  
与此事件关联的错误类型。 有关[可能的值，请参阅 Enum LSCEventType。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
#### <a name="ilsceventgetwebpath"></a>ILSCEvent：：GetWebPath

此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnFilePathConflict。 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a>参数

 _pbstrWebPath_
  
指定与此事件关联的 Web 路径。 不得为 null。 
  
##### <a name="return-values"></a>返回值

始终返回S_OK。 
  
### <a name="interface-ilscevent2"></a>接口 ILSCEvent2

此接口包含有关同步事件的其他信息。
  
**公共成员函数**

#### <a name="ilscevent2geterrorchain"></a>ILSCEvent2：：GetErrorChain

获取有关同步事件的错误链信息。
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a>参数

 _pbstrErrorChain_
  
用于保存错误链信息的字符串。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_NOTIMPL  <br/> |已安装版本的 Office不支持此接口  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数值无效。  <br/> |
|E_FAIL  <br/> |错误链信息不可用。  <br/> |
|S_OK  <br/> |呼叫成功。  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a>Interface IPartnerActivityCallback

此接口为 CSISyncClient COM 对象提供回调函数。
  
**公共成员函数**

#### <a name="ipartneractivitycallbackeventoccurred"></a>IPartnerActivityCallback：：EventOccurred

这是给定给 CsiSyncClient COM 对象的对象上的回调函数。 预计当事件发生时， ([Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 了解有效的事件类型) ，CsiSyncClient COM 对象将调用此方法，从而影响使用者。 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a>参数

 _eEventTypeOccurred_
  
此事件的事件类型。 有关[有效值，请参阅 Enum LSCEventTypeOccurred。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 
  
##### <a name="return-values"></a>返回值

始终返回S_OK。
  
## <a name="enumerations"></a>枚举

CSISyncClient 使用下列枚举。
  
### <a name="enum-lsceventsyncerrortype"></a>枚举 LSCEventSyncErrorType
<a name="Enum_LSCEventSyncErrorType"> </a>

此枚举指定同步文件时可能会发生的错误类别。
  
|枚举器|说明|
|:-----|:-----|
|LSCEventSyncErrorType_UserInterventionRequiredUnexpected  <br/> |此事件的同步错误是意外的，可能需要特别注意。 默认情况下，用户可能必须介入。  <br/> |
|LSCEventSyncErrorType_NoInterventionRequired  <br/> |此事件的同步错误不需要特别考虑。 Office自动处理它。  <br/> |
|LSCEventSyncErrorType_UserInterventionRequired  <br/> |此事件的同步错误需要用户进行解析。 例如，合并冲突错误要求用户打开文档并合并它。  <br/> |
|LSCEventSyncErrorType_WaitingOnClient  <br/> |此事件的同步错误需要消费者介入，但不需要用户特别考虑。  <br/> |
|LSCEventSyncErrorType_ClientInterventionRequired  <br/> |此事件的同步错误要求消费者以特殊情况介入。  <br/> |
|LSCEventSyncErrorType_Max  <br/> ||
   
### <a name="enum-lsceventtype"></a>枚举 LSCEventType
<a name="Enum_LSCEventType"> </a>

此枚举指定特定文件可发生的事件类型。
  
|枚举器|说明|
|:-----|:-----|
|LSCEventType_None  <br/> ||
|LSCEventType_OnLocalChanges  <br/> |对本地文件进行了更改。  <br/> |
|LSCEventType_OnOpenedByUser  <br/> |用户打开文件。  <br/> |
|LSCEventType_OnServerChangesDownloaded  <br/> |从服务器下载完文件更改。  <br/> |
|LSCEventType_OnLocalChangesUploaded  <br/> |已完成将文件更改上载到服务器。  <br/> |
|LSCEventType_OnLocalConflictStateChanged  <br/> |文件的合并冲突状态已更改。  <br/> |
|LSCEventType_OnFileAdded  <br/> |已添加文件。  <br/> |
|LSCEventType_OnFileDeleted  <br/> |已删除文件。  <br/> |
|LSCEventType_OnSyncEnabled  <br/> |为用户文件启用了同步。  <br/> |
|LSCEventType_OnServerChangesDownloadStarted  <br/> |开始从服务器下载文件更改。  <br/> |
|LSCEventType_OnLocalChangesUploadStarted  <br/> |开始将文件更改上载到服务器。  <br/> |
|LSCEventType_OnFilePathConflict  <br/> |当对[ILSCLocalSyncClient：：LocalFileChange、ILSCLocalSyncClient：：ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)或[ILSCLocalSyncClient：：RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)的调用导致 Web 路径或本地路径与 Office 文件缓存中的另一个文件冲突时，将生成此事件。 [ ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)  <br/> |
|LSCEventType_OnFileForked  <br/> ||
|LSCEventType_Max  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a>枚举 LSCEventTypeOccurred
<a name="Enum_LSCEventTypeOccurred"> </a>

此枚举指定可发生事件的类型。 使用者需要基于事件类型调用特定的 ILSCLocalSyncClient 函数。
  
|枚举器|说明|
|:-----|:-----|
|LSCEventTypeOccurred_GetChanges  <br/> |发生 ILSCEvent。 使用者应调用 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) 以检索数据。  <br/> |
|LSCEventTypeOccurred_GetSupportedFileExtensions  <br/> |受支持的文件扩展名已更改。 使用者应调用 [ILSCLocalSyncClient：：GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions) 来检索受支持的扩展的新列表。  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a>枚举 LSCNetworkSyncPermissionType
<a name="Enum_LSCNetworkSyncPermissionType"> </a>

此枚举指定用于网络成本启发的标志。 

|枚举器|说明|
|:-----|:-----|
|LSCNetworkSyncPermissionType_HighCost  <br/> |如果覆盖高成本网络（如 3G (）的成本启发) True。  <br/> |
|LSCNetworkSyncPermissionType_HighPowerUsage  <br/> |如此 如果电源使用成本启发式 (例如电池) 覆盖。  <br/> |
   
### <a name="enum-lscstatusflag"></a>枚举 LSCStatusFlag
<a name="Enum_LSCStatusFlag"> </a>

此枚举用于表示文件的同步状态。 
  
|枚举器|说明|
|:-----|:-----|
|LCSStatusFlag_None  <br/> ||
|LSCStatusFlag_UploadPending  <br/> |如此 如果有待发送到服务器文件的数据。  <br/> |
|LSCStatusFlag_DownloadPending  <br/> |如果服务器文件中存在要下载的待定数据，则其为 True。  <br/> |
|LSCStatusFlag_LocalFileUnchanged  <br/> |如此 如果Office文件在其缓存中具有的数据是磁盘上的最新数据副本。  <br/> |
   

