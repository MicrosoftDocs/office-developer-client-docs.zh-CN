---
title: 使用 CSISyncClient 控制 Office 文档缓存 (ODC)
manager: soliver
ms.date: 07/13/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 394b8e6f-9132-4c98-8fd6-46ad3c871440
description: 了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。
ms.openlocfilehash: ce33063f88492bcd6f9682a4a6431fb36f138d55
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346254"
---
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a>使用 CSISyncClient 控制 Office 文档缓存 (ODC)

了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。
  
CSISyncClient 是一个进程外 COM 服务器 (CSISyncClient), 它允许 Microsoft OneDrive 控制 Office 文档缓存 (ODC) 的行为。 例如, OneDrive 可能会通过 CSISyncClient 在 ODC 上进行调用, 以在 MS ms-fsshttp 启用的终结点上传和下载文件。 这将启用 Office 中的高级服务支持功能, 如共同创作和从脱机到联机的无缝转换。
  
CsiSyncClient 在 Office Desktop (x86 和 x64) 中可用。 注意: 虽然较新版本的 Office 可能附带 CsiSyncClient, 但此过程仅用于向后兼容性。 用于控制 ODC 的 CsiSyncClient 接口和方法在将来的 Office 版本中会发生变化。
  
类 ID 当前设置为仅响应 OneDrive。
  
com 对象可用作进程外 com 服务器, 并在 CsiSyncClient 中运行。 由于 Access (ODC 使用) 的限制, 它附带了 Office 所带的位类型, 因此 x64 office 表示 x64 com 对象, 或 x86 office 表示 x86 com 对象。 若要避免此限制, 将 CLSCTX_LOCAL_SERVER 指定为 CoCreateInstance 的一部分会将 com 对象作为进程外 com 服务器托管, 从而允许跨位数兼容性。
  
## <a name="interfaces"></a>接口

CSISyncClient 使用下列接口。
  
### <a name="interface-ilsclocalsyncclient"></a>接口 ILSCLocalSyncClient

这是用于同步 Office 中的文件的主要界面。
  
- ProgID: LocalSyncClient
- CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}
- TypeLib: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}
   
公开的 COM 对象用作进程外服务器。 将 CLSCTX_LOCAL_SERVER 指定为 CoCreateInstance 的一部分可以实现64位和32位进程之间的兼容性。
  
共同创建 COM 对象后, 必须先调用[ILSCLocalSyncClient:: first 初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)。 一旦[ILSCLocalSyncClient:: 初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)成功完成, 您可以根据需要按任意顺序调用任何 API。 您还可以对已经初始化的对象调用[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) , 但这不起任何作用。 
  
前一段的例外情况是[ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)和[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 在对 COM 对象调用[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)后, 必须销毁该对象并创建一个新对象。 [ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)将删除您的 subcache, 删除缓存中的所有关联文件信息, 但将这些文档保留在磁盘上。 它还保持与缓存进行通信的状态不变。 这使您可以调用[ILSCLocalSyncClient:: 重新初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)以创建新的缓存, 而无需销毁并重新创建 COM 对象。 
  
**公共成员函数**

#### <a name="ilsclocalsyncclientdeletefile"></a>ILSCLocalSyncClient::D eletefile

DeleteFile 用于从缓存中删除文件信息。 但是, 此方法将把关联的文件保留在磁盘上和服务器上。
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识文件的 ResourceID 的字符串。 此值必须为非空, 最多为128个字符。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |给定的 ResourceID 不在缓存中。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |过去未成功调用初始化。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |文件当前正在同步或已打开, 无法删除。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a>ILSCLocalSyncClient:: GetChanges
<a name="ILSCLocalSyncClient_GetChanges"> </a>

GetChanges 返回 ILSCEvent 对象的枚举器, 并且还返回一个令牌, 该令牌将提供给下一个对 GetChanges 的调用, 假定使用者已处理了以前的一组事件。 在指定的_nPreviousChangesToken_之前的事件将被删除且不可用。 如果没有要处理的事件, 则_pnCurrentChangesToken_应与_nPreviousChangesToken_的值相同, 但仍将设置_ppiEvents_ 。 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a>参数

 _nPreviousChangesToken_
  
标识使用者上次处理的事件。 
  
 _pnCurrentChangesToken_
  
标识正在传递给使用者的最新事件。 不得为 null。
  
 _ppiEvents_
  
传递给使用者的事件的枚举器。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a>ILSCLocalSyncClient:: GetClientNetworkSyncPermission

GetClientNetworkSyncPermission 用于查询 Office 对网络成本和电源使用的同步试探法是否已被覆盖。 在3g 或其他高成本网络上, 或在使用电池运行而不是插入时, Office 可能会选择阻止网络流量, 直到 opportune 时间。
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a>参数

 _nspType_
  
定义要查询的成本启发的标志。 请参阅[Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。 
  
 _pfSyncEnabled_
  
指定请求的成本试探法当前是否已覆盖。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a>ILSCLocalSyncClient:: GetFileStatus

GetFileStatus 用于收集特定文件的信息: 无论它是否存在于缓存中, 如果有挂起的与服务器副本的通信, 以及 Office 2013 是否具有来自本地副本的最新数据。 它需要[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)值的按位标志, 以确定 CsiSyncClient COM 对象要查询的信息。 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
标识客户端上的文件的字符串。 此值必须为非空, 最多为128个字符。 
  
 _sfRequestedStatus_
  
定义要返回的信息的标志。 请参阅[Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
 _pbstrFileSystemPath_
  
标识由客户端上的_bstrResourceID_标识的文件的位置的字符串。 不得为 null。 
  
 _pbstrETag_
  
一个字符串, 它将包含由_bstrResourceID_标识的文件的 eTag。 不得为 null。 
  
 _psfFileStatus_
  
一个标志, 该标志将包含通过_sfRequestedStatus_为_bstrResourceID_标识的文件请求的状态。 不得为 null。 请参阅[Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |_bstrResourceID_指定的文件信息在缓存中不存在。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |已请求 LSCStatusFlag_LocalFileUnchanged 或_bstrResourceID_指定的文件已锁定或丢失。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a>ILSCLocalSyncClient:: GetSupportedFileExtensions
<a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a>

GetSupportedFileExtensions 返回 CsiSyncClient COM 对象当前支持的、由管道分隔的文件扩展名列表。 请注意, 此列表可能会发生更改, 并且将通过 ILSCLocalSyncClient 中提供的 IPartnerActivityCallback 对象通知使用者[:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (请参阅 EventOccured)。 
  
返回的字符串示例如下: "| .docx | .docm | .pptx |"
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a>参数

 _pbstrSupportedFileExtensions_
  
要使用 CsiSyncClient COM 对象支持的一组由管道分隔的文件扩展名进行设置的字符串。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a>ILSCLocalSyncClient:: Initialize
<a name="ILSCLocalSyncClient_Initialize"> </a>

初始化必须是调用的第一个方法。 否则, 所有其他 api 将返回 E_LSC_NOTINITIALIZED。 对已初始化的对象调用 Initialize 将返回 S_OK, 并且不执行任何操作。 如果返回 E_LSC_CACHEMISMATCH, 则调用方可能会调用[ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)以删除与给定 SuppliedID 关联的缓存。 但是, 在这种情况下, 其他 api 仍将返回 E_LSC_NOTINITIALIZED。 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a>参数

 _bstrSuppliedID_
  
标识使用者以及要使用的缓存。 必须为非空, 最多为32个字符。 
  
 _bstrProgID_
  
标识用于双向通信的使用者的 COM 对象。 必须为非空, 最多为39个字符。 有关 ProgIDs 的详细信息, 请参阅[ \<ProgID\> Key](https://docs.microsoft.com/windows/desktop/com/-progid--key) 。 
  
 _bstrFileSystemDirectoryHint_
  
标识将在其中存储本地文件的目录根。 必须为非空, 最多为256个字符。 该目录必须已经存在。 
  
 _pEventCallback_
  
CsiSyncClient 将在发生更改时通知的回调接口。 请参阅 IPartnerActivityCallback:: EventOccurred。 此值不得为 null。 
  
 _pfCreatedNewCache_
  
返回一个指示是否已创建新的缓存。 如果没有与 SuppliedID 关联的缓存, 则将创建一个缓存。 此值不得为 null。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CACHEMISMATCH  <br/> |SuppliedID 已有与之关联的缓存, 但其 ProgId 或 FileSystemDirectoryHint 与提供的是不同的 ProgId 或文件。  <br/> |
|E_LSC_DIRECTORYHINTCONFLICT  <br/> |FileSystemDirectoryHint (或子文件夹) 已存在于不同的缓存中。  <br/> |
|E_LAC_PROGIDCONFLICT  <br/> |ProgID 已经存在于不同的缓存中。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a>ILSCLocalSyncClient:: LocalFileChange
<a name="ILSCLocalSyncClient_LocalFileChange"> </a>

LocalFileChange 用于通知 CsiSyncClient COM 对象尝试上传指定的文件。 此方法将为上载准备文件, 包括读取文件的当前内容。 如果上载已挂起, 将放弃上一个上载, 并为上载准备好的新内容。 如果在应用程序中打开文件进行编辑, 则此方法将返回 S_OK, 而不准备上载文件 (如果存在更改, 应用程序应已执行此步骤)。
  
此方法将允许上载 (如果之前已将其标记为 "已阻止上载") (请参阅[ILSCLocalSyncClient:: RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile))。
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

 _bstrFileSystemPath_
  
一个标识客户端上的文件的字符串。 此值必须为非空的本地路径, 最多为256个字符。 调用[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)时, 此路径必须位于由 FileSystemDirectoryHint 指定的目录树中。 
  
 _bstrResourceID_
  
一个标识文件的 ResourceID 的字符串。 此值必须为非空, 最多为128个字符。 
  
 _bstrWebPath_
  
一个标识服务器上的文件的字符串。 此值必须为非空、有效的 URL, 但不能长于 INTERNET_MAX_URL_LENGTH 定义的https://support.microsoft.com/kb/208427。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrFileSystemPath_指定的文件的 ResourceID 与指定的 ResourceID 不同。 当返回此错误时, 将发送 LSCEventType_OnFilePathConflict 类型的事件。 请参阅[ILSCLocalSyncClient:: GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |文件是在操作中删除的。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |CsiSyncClient COM 对象不支持给定的文件扩展名。 请参阅[ILSCLocalSyncClient:: GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。  <br/> |
|E_LSC_FILEUPTODATE  <br/> |由于缓存中的文件包含磁盘的最新更改, 因此 COM 对象未计划上载。  <br/> |
|E_LSC_LOCALFILEUNAVAILABLE  <br/> |_bstrFileSystemPath_指定的文件已丢失或被锁定。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_bstrResourceID_指定的文件具有与指定的 FileSystemPath 不同的。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件在其他缓存中已有挂起的更改, 并且尚未与使用者的缓存关联。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供的 WebPath 位于不同的缓存中。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a>ILSCLocalSyncClient:: RenameFile
<a name="ILSCLocalSyncClient_RenameFile"> </a>

RenameFile 将为给定的 ResourceID 关联新的 URL 和本地路径。 如果由 ResourceID 指定的文件在缓存中不存在, 则将尝试创建该文件并将其标记为下载。
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a>参数

 _bstrResourceID_
  
一个标识文件的 ResourceID 的字符串。 此值必须为非空, 最多为128个字符。 
  
 _bstrNewFileSystemPath_
  
一个字符串, 它指定文件的新本地路径。 此值必须为非空的本地路径, 最多为256个字符。 此路径必须位于由 FileSystemDirectoryHint 指定的目录树中进行初始化调用时。 
  
 _bstrNewWebPath_
  
一个字符串, 指定文件的新 URL。 此值必须为非空的有效 URL, 但不能超过 INTERNET_MAX_URL_LENGTH (由https://support.microsoft.com/kb/208427定义)。 
  
 _fBlockUploads_
  
指定当前是否允许上载到新位置。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrNewFileSystemPath_或_bstrNewWebPath_已存在于任何缓存中的另一个文件上。 当返回此错误时, 将发送 LSCEventType_OnFilePathConflict 类型的事件。 请参阅[ILSCLocalSyncClient:: GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |在此方法运行过程中, 文件信息已从缓存中删除。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件当前在 Office 应用程序中进行同步。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a>ILSCLocalSyncClient:: ResetCache
<a name="ILSCLocalSyncClient_ResetCache"> </a>

ResetCache 将删除与初始化时提供的 SuppliedID 关联的缓存。 这包括所有文件信息, 但会将这些文件同时保留在客户端和服务器上。 此方法还会使对象处于部分未初始化状态。 在此之后, 唯一有效的调用是[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)或[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。 如果初始化失败并返回 E_LSC_CACHEMISMATCH, 则可能会调用此方法, 并将删除与失败调用一起提供的 SuppliedID 关联的缓存。
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a>参数

无
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |调用失败。  <br/> |
|E_LSC_NOTINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用 Initialize。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a>ILSCLocalSyncClient:: ServerFileChange
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

ServerFileChange 通知 CsiSyncClient COM 对象将指定的文件标记为下载。 如果文件已在 Office 应用程序中打开, 则此方法将返回 S_OK, 而不标记要下载的文件 (如果存在更改, 应用程序应已执行此步骤)。
  
如果之前已将下载标记为 "已阻止下载", 此方法将允许下载 (请参阅 RenameFile)。
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a>参数

|参数|描述|
|:-----|:-----|
|bstrFileSystemPath  <br/> |一个标识客户端上的文件的字符串。 此值必须为非空的本地路径, 最多为256个字符。 此路径必须位于由 FileSystemDirectoryHint 指定的目录树中进行初始化调用时。  <br/> |
|bstrResourceID  <br/> |一个标识文件的 ResourceID 的字符串。 此值必须为非空, 最多为128个字符。  <br/> |
|bstrWebPath  <br/> |一个标识服务器上的文件的字符串。 此值必须为非空的有效 URL, 但不能长于 INTERNET_MAX_URL_LENGTH 定义的https://support.microsoft.com/kb/208427。  <br/> |
   
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |未能设置缓存连接状态。  <br/> |
|E_LSC_CONFLICTINGFILE  <br/> |_bstrFileSystemPath_指定的文件的 ResourceID 与指定的 ResourceID 不同。  <br/> |
|E_LSC_FILENOTSUPPORTED  <br/> |CsiSyncClient COM 对象不支持给定的文件扩展名。 请参阅 GetSupportedFileExtensions。  <br/> |
|E_LSC_FILENOTFOUND  <br/> |在 mid 操作中删除了文件。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_LOCALPATHNOTMAPPED  <br/> |在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|E_LSC_PATHMISMATCH  <br/> |_bstrResourceID_指定的文件具有与指定的 FileSystemPath 不同的。  <br/> |
|E_LSC_PENDINGCHANGESINCACHE  <br/> |指定的文件在其他缓存中已有挂起的更改, 并且尚未与使用者的缓存关联。  <br/> |
|E_LSC_SERVERPATHINDIFFERENTCACHE  <br/> |提供的 WebPath 位于不同的缓存中。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a>ILSCLocalSyncClient:: SetClientConnectivityState
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

将缓存设置为联机或脱机状态。 如果脱机, 则无论每个文件的_fBlockUploads_设置如何, Office 都不会尝试与服务器进行缓存中任何文件的通信。 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a>参数

 _fIsOnline_
  
用于确定缓存的连接状态的布尔值。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |未能设置缓存连接状态。  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a>ILSCLocalSyncClient:: SetClientNetworkSyncPermission
<a name="ILSCLocalSyncClient_ServerFileChange"> </a>

SetClientNetworkSyncPermission 用于替代或 restoreOffice 同步试探法以实现网络成本和电源使用。 在3g 或其他高成本网络上, 或在使用电池运行而不是插入时, Office 可能会选择阻止网络流量, 直到 opportune 时间。 此 API 的使用者可以使用它来覆盖 Office 的试探方法并强制进行同步。
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a>参数

 _nspType_
  
一个标志, 该标志定义要覆盖的成本试探法。 请参阅[Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。
  
 _fEnableSync_
  
指定是否强制在上进行同步, 从而替代该成本试探法, 或不再覆盖它。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |重写同步试探法失败。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a>ILSCLocalSyncClient:: 取消初始化
<a name="ILSCLocalSyncClient_Uninitialize"> </a>

从 COM 对象中卸载缓存并执行关闭操作。 [ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)在销毁 COM 对象之前, 必须调用。 调用后, 不能调用任何其他 api, 必须销毁 COM 对象并创建新的, 如果您想要继续操作。 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |取消初始化失败。  <br/> |
|E_LSC_NOINITIALIZED  <br/> |[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
### <a name="interface-ienumlscevent"></a>接口 IEnumLSCEvent

此接口表示 ILSCEvent 事件的列表。
  
**公共成员函数**

#### <a name="ienumlsceventfnext"></a>IEnumLSCEvent:: FNext

从事件列表中检索下一个事件。
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a>参数

 _ppiLSCEvent_
  
指向 ILSCEvent 接口的指针。
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_FAIL  <br/> |没有其他事件。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ienumlsceventreset"></a>IEnumLSCEvent:: Reset

将枚举器重置为第一个事件。
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a>参数

无。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
### <a name="interface-ilscevent"></a>接口 ILSCEvent

此接口表示同步事件。 可以从接口检索有关事件的所有信息。
  
**公共成员函数**

#### <a name="ilsceventgetconflictstatus"></a>ILSCEvent:: GetConflictStatus

请注意, 在调用[ILSCLocalSyncClient:: GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)时, 将填充此值, 而不是在创建事件时填充, 因此您仅具有文件的当前状态, 而不是在冲突状态更改时文件的状态。 
  
仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnLocalConflictStateChanged 时, 才会填充此值。 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a>参数

 _pfIsInConflict_
  
与事件关联的文件的当前冲突状态。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgeterror"></a>ILSCEvent:: GetError

仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a>参数

 _pnError_
  
与此事件关联的错误。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetetag"></a>ILSCEvent:: GetETag

仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a>参数

 _pbstrETag_
  
与此事件关联的 ETag
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgeteventtype"></a>ILSCEvent:: GetEventType

获取此事件的类型。
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a>参数

 _pnEventType_
  
此事件的事件类型。 有关有效值, 请参阅[Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a>ILSCEvent:: GetLocalWorkingPath

获取此事件的本地工作路径。
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a>参数

 _pbstrLocalWorkingPath_
  
此事件所属于的文件的本地路径。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetresourceid"></a>ILSCEvent:: GetResourceID

获取事件的资源 ID。
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a>参数

 _pbstrResourceID_
  
与此事件关联的文件的资源 id。
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetresourceidattempted"></a>ILSCEvent:: GetResourceIDAttempted

仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnFilePathConflict 时, 才会填充此值。 当调用[ILSCLocalSyncClient:: LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient:: ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient:: RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)导致 Web 路径或本地路径与 Office 文件缓存中的其他文件发生冲突时, 这生成事件。 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a>参数

 _pbstrResourceIDAttempted_
  
导致此事件生成的 ResourceID。 不得为 null。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
#### <a name="ilsceventgetsyncerrortype"></a>ILSCEvent:: GetSyncErrorType

仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a>参数

 _pnSyncErrorType_
  
与此事件关联的错误类型。 有关潜在值, 请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_INVALIDARG  <br/> |一个或多个参数无效。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
#### <a name="ilsceventgetwebpath"></a>ILSCEvent:: GetWebPath

仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnFilePathConflict 时, 才会填充此值。 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a>参数

 _pbstrWebPath_
  
指定与此事件关联的 Web 路径。 不得为 null。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。 
  
### <a name="interface-ilscevent2"></a>接口 ILSCEvent2

此接口保存有关同步事件的其他信息。
  
**公共成员函数**

#### <a name="ilscevent2geterrorchain"></a>ILSCEvent2:: GetErrorChain

获取有关同步事件的错误链信息。
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a>参数

 _pbstrErrorChain_
  
一个用于保存错误链信息的字符串。 不得为 null。 
  
##### <a name="return-values"></a>返回值

|值|说明|
|:-----|:-----|
|E_NOTIMPL  <br/> |安装的 Office 版本不支持此接口  <br/> |
|E_INVALIDARG  <br/> |一个或多个参数值无效。  <br/> |
|E_FAIL  <br/> |错误链信息不可用。  <br/> |
|S_OK  <br/> |调用成功。  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a>接口 IPartnerActivityCallback

此接口提供对 CSISyncClient COM 对象的回调函数。
  
**公共成员函数**

#### <a name="ipartneractivitycallbackeventoccurred"></a>IPartnerActivityCallback:: EventOccurred

这是给定给 CsiSyncClient COM 对象的对象上的回调函数。 当事件发生时 (请参阅[Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid 事件类型), CsiSyncClient COM 对象将调用此方法, 以信令使用者。 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a>参数

 _eEventTypeOccurred_
  
此事件的事件类型。 有关有效值, 请参阅[Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 。 
  
##### <a name="return-values"></a>返回值

始终返回 S_OK。
  
## <a name="enumerations"></a>枚举

CSISyncClient 使用以下枚举。
  
### <a name="enum-lsceventsyncerrortype"></a>枚举 LSCEventSyncErrorType
<a name="Enum_LSCEventSyncErrorType"> </a>

此枚举指定同步文件时可能发生的错误类别。
  
|枚举器重|说明|
|:-----|:-----|
|LSCEventSyncErrorType_UserInterventionRequiredUnexpected  <br/> |此事件的同步错误是意外的, 可能需要特别注意。 默认情况下, 用户可能需要干预。  <br/> |
|LSCEventSyncErrorType_NoInterventionRequired  <br/> |此事件的同步错误不需要特别考虑。 Office 将自动处理它。  <br/> |
|LSCEventSyncErrorType_UserInterventionRequired  <br/> |此事件的同步错误要求用户对其进行解析。 例如, 合并冲突错误要求用户打开并合并文档。  <br/> |
|LSCEventSyncErrorType_WaitingOnClient  <br/> |此事件的同步错误需要使用者干预, 但用户不需要特别注意。  <br/> |
|LSCEventSyncErrorType_ClientInterventionRequired  <br/> |此事件的同步错误要求使用者干预为特殊情况。  <br/> |
|LSCEventSyncErrorType_Max  <br/> ||
   
### <a name="enum-lsceventtype"></a>枚举 LSCEventType
<a name="Enum_LSCEventType"> </a>

此枚举指定可对特定文件发生的事件的类型。
  
|枚举器重|说明|
|:-----|:-----|
|LSCEventType_None  <br/> ||
|LSCEventType_OnLocalChanges  <br/> |对本地文件进行了更改。  <br/> |
|LSCEventType_OnOpenedByUser  <br/> |用户打开了文件。  <br/> |
|LSCEventType_OnServerChangesDownloaded  <br/> |从服务器下载文件更改已完成。  <br/> |
|LSCEventType_OnLocalChangesUploaded  <br/> |完成将文件更改上载到服务器。  <br/> |
|LSCEventType_OnLocalConflictStateChanged  <br/> |文件的合并冲突状态已更改。  <br/> |
|LSCEventType_OnFileAdded  <br/> |添加了一个文件。  <br/> |
|LSCEventType_OnFileDeleted  <br/> |删除了一个文件。  <br/> |
|LSCEventType_OnSyncEnabled  <br/> |对用户文件启用了同步。  <br/> |
|LSCEventType_OnServerChangesDownloadStarted  <br/> |已开始从服务器下载文件更改。  <br/> |
|LSCEventType_OnLocalChangesUploadStarted  <br/> |已开始将文件更改上载到服务器。  <br/> |
|LSCEventType_OnFilePathConflict  <br/> |当调用[ILSCLocalSyncClient:: LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient:: ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient:: RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)导致 Web 路径或本地路径与另一个文件中的其他文件发生冲突时, 会生成此事件。Office 文件缓存。  <br/> |
|LSCEventType_OnFileForked  <br/> ||
|LSCEventType_Max  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a>枚举 LSCEventTypeOccurred
<a name="Enum_LSCEventTypeOccurred"> </a>

此枚举指定可能发生的事件的类型。 使用者需要根据事件类型调用特定的 ILSCLocalSyncClient 函数。
  
|枚举器重|说明|
|:-----|:-----|
|LSCEventTypeOccurred_GetChanges  <br/> |发生了 ILSCEvent。 使用者应调用[ILSCLocalSyncClient:: GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)以检索数据。  <br/> |
|LSCEventTypeOccurred_GetSupportedFileExtensions  <br/> |支持的文件扩展名已更改。 使用者应调用[ILSCLocalSyncClient:: GetSupportedFileExtensions](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)以检索支持的扩展的新列表。  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a>枚举 LSCNetworkSyncPermissionType
<a name="Enum_LSCNetworkSyncPermissionType"> </a>

此枚举指定用于网络成本启发式的标志。 

|枚举器重|说明|
|:-----|:-----|
|LSCNetworkSyncPermissionType_HighCost  <br/> |如此如果重写昂贵网络 (如 3g) 的成本试探法。  <br/> |
|LSCNetworkSyncPermissionType_HighPowerUsage  <br/> |如此如果重写了电源使用的成本试探法 (如电池)。  <br/> |
   
### <a name="enum-lscstatusflag"></a>枚举 LSCStatusFlag
<a name="Enum_LSCStatusFlag"> </a>

此枚举用于表示文件的同步状态。 
  
|枚举器重|说明|
|:-----|:-----|
|LCSStatusFlag_None  <br/> ||
|LSCStatusFlag_UploadPending  <br/> |如果有要发送到服务器文件的挂起数据, 则为 True。  <br/> |
|LSCStatusFlag_DownloadPending  <br/> |如果有要从服务器文件中下载的挂起数据, 则为 True。  <br/> |
|LSCStatusFlag_LocalFileUnchanged  <br/> |如此如果数据办公室的缓存中的文件是磁盘上的最新数据副本。  <br/> |
   

