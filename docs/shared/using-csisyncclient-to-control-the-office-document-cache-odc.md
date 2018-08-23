---
title: 使用 CSISyncClient 控制 Office 文档缓存 (ODC)
manager: soliver
ms.date: 07/13/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 394b8e6f-9132-4c98-8fd6-46ad3c871440
description: 了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。
ms.openlocfilehash: 908442bdc4e02f8268b9af877921da45a64ab197
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565282"
---
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a><span data-ttu-id="b0e44-103">使用 CSISyncClient 控制 Office 文档缓存 (ODC)</span><span class="sxs-lookup"><span data-stu-id="b0e44-103">Using CSISyncClient to control the Office Document Cache (ODC)</span></span>

<span data-ttu-id="b0e44-104">了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-104">Learn how to use CSISyncClient to control the Office Document Cache (ODC).</span></span>
  
<span data-ttu-id="b0e44-105">CSISyncClient 是允许 Microsoft OneDrive 以控制行为的 Office 文档缓存 (ODC) 进程出 COM 服务器 (CsiSyncClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-105">CSISyncClient is an out-of-proc COM server (CsiSyncClient.exe) that allows Microsoft OneDrive to control the behavior of the Office Document Cache (ODC).</span></span> <span data-ttu-id="b0e44-106">例如，OneDrive 可以调用 CSISyncClient 上载和下载文件，与 MS-FSSHTTP 启用终结点通过 ODC。</span><span class="sxs-lookup"><span data-stu-id="b0e44-106">For example, OneDrive may call upon the ODC via CSISyncClient to upload and download files to and from MS-FSSHTTP enabled endpoints.</span></span> <span data-ttu-id="b0e44-107">这样，高级的服务备份 Office 中的功能，如共同创作和无缝切换从脱机到 online。</span><span class="sxs-lookup"><span data-stu-id="b0e44-107">This enables advanced service-backed features in Office, such as co-authoring and seamless transitions from offline to online.</span></span>
  
<span data-ttu-id="b0e44-108">CsiSyncClient 位于 Office 桌面 （x86 和 x64）。</span><span class="sxs-lookup"><span data-stu-id="b0e44-108">CsiSyncClient is available in Office Desktop (both x86 and x64).</span></span> <span data-ttu-id="b0e44-109">注意： 时较新版本的 Office 可能附带 CsiSyncClient，过程将用于向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0e44-109">Note: While newer versions of Office may ship with CsiSyncClient, the process will be used for backward compatibility only.</span></span> <span data-ttu-id="b0e44-110">CsiSyncClient 接口和控制 ODC 方法将在将来更改版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="b0e44-110">The CsiSyncClient interface and the methodology of controlling the ODC will change in future versions of Office.</span></span>
  
<span data-ttu-id="b0e44-111">当前设置的类 ID，只响应 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="b0e44-111">The class ID is currently set to respond only to OneDrive.</span></span>
  
<span data-ttu-id="b0e44-112">COM 对象是为进程出 COM 服务器可用，并在 CsiSyncClient.exe 运行。</span><span class="sxs-lookup"><span data-stu-id="b0e44-112">The COM object is usable as an out-of-proc COM server and runs in CsiSyncClient.exe.</span></span> <span data-ttu-id="b0e44-113">由于限制访问 （它使用 ODC），它附带的 Office 中，因此 x64 Office 意味着 x64 位键入 COM 对象或 x86 Office 意味着 x86 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b0e44-113">Due to limitations with Access (which the ODC uses), it ships with the bit type that Office comes in, so x64 Office means an x64 COM object, or x86 Office means an x86 COM object.</span></span> <span data-ttu-id="b0e44-114">若要解决此限制，如一部分 CoCreateInstance 会为允许占用兼容性出进程 COM 服务器托管的 COM 对象指定 CLSCTX_LOCAL_SERVER。</span><span class="sxs-lookup"><span data-stu-id="b0e44-114">To get around this limitation, specifying CLSCTX_LOCAL_SERVER as part of the CoCreateInstance will have the COM object be hosted as an out-of-proc COM server, allowing cross-bitness compatibility.</span></span>
  
## <a name="interfaces"></a><span data-ttu-id="b0e44-115">接口</span><span class="sxs-lookup"><span data-stu-id="b0e44-115">Interfaces</span></span>

<span data-ttu-id="b0e44-116">CSISyncClient 使用以下接口。</span><span class="sxs-lookup"><span data-stu-id="b0e44-116">CSISyncClient uses the following interfaces.</span></span>
  
### <a name="interface-ilsclocalsyncclient"></a><span data-ttu-id="b0e44-117">接口 ILSCLocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="b0e44-117">Interface ILSCLocalSyncClient</span></span>

<span data-ttu-id="b0e44-118">这是用于同步文件在 Office 中的主要接口。</span><span class="sxs-lookup"><span data-stu-id="b0e44-118">This is the primary interface used to synchronize files in Office.</span></span>
  
- <span data-ttu-id="b0e44-119">ProgID: Office.LocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="b0e44-119">ProgID: Office.LocalSyncClient</span></span>
- <span data-ttu-id="b0e44-120">CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}</span><span class="sxs-lookup"><span data-stu-id="b0e44-120">CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}</span></span>
- <span data-ttu-id="b0e44-121">类型库: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span><span class="sxs-lookup"><span data-stu-id="b0e44-121">TypeLib: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span></span>
   
<span data-ttu-id="b0e44-122">已公开的 COM 对象用作出进程服务器。</span><span class="sxs-lookup"><span data-stu-id="b0e44-122">The COM object that is exposed is used as an out-of-proc server.</span></span> <span data-ttu-id="b0e44-123">指定作为一部分 CoCreateInstance CLSCTX_LOCAL_SERVER 允许 64 位和 32 位进程之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0e44-123">Specifying CLSCTX_LOCAL_SERVER as part of CoCreateInstance allows compatability between 64bit and 32bit processes.</span></span>
  
<span data-ttu-id="b0e44-124">一旦共同创建 COM 对象，您必须首先调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 。</span><span class="sxs-lookup"><span data-stu-id="b0e44-124">Once you've co-created the COM object, you MUST call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) first.</span></span> <span data-ttu-id="b0e44-125">一旦[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)已成功完成，您可能会调用任何 API，通常可以您希望和按任意顺序。</span><span class="sxs-lookup"><span data-stu-id="b0e44-125">Once [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has completed successfully, you may call any API as often as you wish and in any order.</span></span> <span data-ttu-id="b0e44-126">您可能已初始化的对象上调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) ，但这不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b0e44-126">You may also call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) on an already initialized object, but this does nothing.</span></span> 
  
<span data-ttu-id="b0e44-127">上一段的例外是[ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)和[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-127">The exceptions to the previous paragraph are [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) and [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="b0e44-128">COM 对象上调用[ILSCLocalSyncClient::Uninitialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)之后，您必须销毁对象，并创建一个新。</span><span class="sxs-lookup"><span data-stu-id="b0e44-128">After you call [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) on the COM object, you MUST destroy that object and create a new one.</span></span> <span data-ttu-id="b0e44-129">[ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)将删除您 subcache，删除该缓存中的所有关联的文件信息，但在磁盘上保留文档。</span><span class="sxs-lookup"><span data-stu-id="b0e44-129">[ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) will delete your subcache, delete all associated file information in the cache, but leave the documents on disk.</span></span> <span data-ttu-id="b0e44-130">它还退出状态用于与缓存通信保持不变。</span><span class="sxs-lookup"><span data-stu-id="b0e44-130">It also leaves the state intact for communicating with the cache.</span></span> <span data-ttu-id="b0e44-131">这样，您可以调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)再次以创建新的缓存，而无需销毁并重新创建该 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b0e44-131">This allows you to call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) again to create a new cache without having to destroy and recreate the COM object.</span></span> 
  
<span data-ttu-id="b0e44-132">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0e44-132">**Public member functions**</span></span>

#### <a name="ilsclocalsyncclientdeletefile"></a><span data-ttu-id="b0e44-133">ILSCLocalSyncClient::DeleteFile</span><span class="sxs-lookup"><span data-stu-id="b0e44-133">ILSCLocalSyncClient::DeleteFile</span></span>

<span data-ttu-id="b0e44-134">DeleteFile 用于从缓存中删除的文件信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-134">DeleteFile is used to remove the file information from the cache.</span></span> <span data-ttu-id="b0e44-135">但是，此方法将保留关联的文件在磁盘上和在服务器上。</span><span class="sxs-lookup"><span data-stu-id="b0e44-135">However, this method will leave the associated file on disk and on the server.</span></span>
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-136">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-136">Parameters</span></span>

 <span data-ttu-id="b0e44-137">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-137">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0e44-138">标识文件的资源 Id 字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-138">The string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0e44-139">此值必须为非空最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-139">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-140">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-140">Return values</span></span>

|<span data-ttu-id="b0e44-141">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-141">Value</span></span>|<span data-ttu-id="b0e44-142">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-142">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-143">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-143">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-144">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-144">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-145">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-145">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-146">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-146">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-147">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-147">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-148">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-148">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-149">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0e44-149">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0e44-150">给定的 ResourceID 不在缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0e44-150">The given ResourceID is not in the cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-151">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-151">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-152">初始化尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-152">Initialize has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-153">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-153">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-154">文件当前正在同步或打开，无法删除。</span><span class="sxs-lookup"><span data-stu-id="b0e44-154">The file is currently synchronizing or open and cannot be deleted.</span></span>  <br/> |
|<span data-ttu-id="b0e44-155">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-155">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-156">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-156">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a><span data-ttu-id="b0e44-157">ILSCLocalSyncClient::GetChanges</span><span class="sxs-lookup"><span data-stu-id="b0e44-157">ILSCLocalSyncClient::GetChanges</span></span>
<span data-ttu-id="b0e44-158"><a name="ILSCLocalSyncClient_GetChanges"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-158"></span></span>

<span data-ttu-id="b0e44-159">GetChanges 返回 ILSCEvent 对象的枚举，并返回其授予对下次调用 GetChanges，假定使用者已经处理前一组事件的令牌。</span><span class="sxs-lookup"><span data-stu-id="b0e44-159">GetChanges returns an enumerator of ILSCEvent objects, and also returns a token that is given to the next call to GetChanges, assuming the consumer has processed the previous set of events.</span></span> <span data-ttu-id="b0e44-160">指定_nPreviousChangesToken_之前的事件都将被删除，而且不可用。</span><span class="sxs-lookup"><span data-stu-id="b0e44-160">Events before the  _nPreviousChangesToken_ specified will be deleted and unavailable.</span></span> <span data-ttu-id="b0e44-161">如果没有处理的事件， _pnCurrentChangesToken_应_nPreviousChangesToken_，相同的值，但_ppiEvents_仍将被设置。</span><span class="sxs-lookup"><span data-stu-id="b0e44-161">If there are no events to be processed,  _pnCurrentChangesToken_ should be the same value as  _nPreviousChangesToken_, but  _ppiEvents_ will still be set.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-162">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-162">Parameters</span></span>

 <span data-ttu-id="b0e44-163">_nPreviousChangesToken_</span><span class="sxs-lookup"><span data-stu-id="b0e44-163">_nPreviousChangesToken_</span></span>
  
<span data-ttu-id="b0e44-164">标识的使用者上次处理的事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-164">Identifies which event was last processed by the consumer.</span></span> 
  
 <span data-ttu-id="b0e44-165">_pnCurrentChangesToken_</span><span class="sxs-lookup"><span data-stu-id="b0e44-165">_pnCurrentChangesToken_</span></span>
  
<span data-ttu-id="b0e44-166">标识要传递给使用者的最新事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-166">Identifies the most recent event being handed to the consumer.</span></span> <span data-ttu-id="b0e44-167">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-167">Must not be null.</span></span>
  
 <span data-ttu-id="b0e44-168">_ppiEvents_</span><span class="sxs-lookup"><span data-stu-id="b0e44-168">_ppiEvents_</span></span>
  
<span data-ttu-id="b0e44-169">传递给使用者的事件枚举。</span><span class="sxs-lookup"><span data-stu-id="b0e44-169">An enumerator for the events handed to the consumer.</span></span> <span data-ttu-id="b0e44-170">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-170">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-171">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-171">Return values</span></span>

|<span data-ttu-id="b0e44-172">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-172">Value</span></span>|<span data-ttu-id="b0e44-173">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-173">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-174">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-174">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-175">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-175">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-176">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-176">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-177">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-177">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-178">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-178">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-179">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-179">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-180">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-180">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-181">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-181">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a><span data-ttu-id="b0e44-182">ILSCLocalSyncClient::GetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="b0e44-182">ILSCLocalSyncClient::GetClientNetworkSyncPermission</span></span>

<span data-ttu-id="b0e44-183">GetClientNetworkSyncPermission 用于查询是否 for Office 的同步启发网络成本和电源使用被重写。</span><span class="sxs-lookup"><span data-stu-id="b0e44-183">GetClientNetworkSyncPermission is used to query whether Office's synchronizing heuristics for network cost and power usage are overridden.</span></span> <span data-ttu-id="b0e44-184">当在 3g 或其他跟踪成本很高网络，或在与要插入的电池上运行时，可以选择 Office 之前多此时阻止网络通信。</span><span class="sxs-lookup"><span data-stu-id="b0e44-184">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span>
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-185">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-185">Parameters</span></span>

 <span data-ttu-id="b0e44-186">_nspType_</span><span class="sxs-lookup"><span data-stu-id="b0e44-186">_nspType_</span></span>
  
<span data-ttu-id="b0e44-187">一个查询中定义的成本推断方法的标志。</span><span class="sxs-lookup"><span data-stu-id="b0e44-187">A flag which defines which cost heuristic to query.</span></span> <span data-ttu-id="b0e44-188">请参阅[枚举 LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-188">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span> 
  
 <span data-ttu-id="b0e44-189">_pfSyncEnabled_</span><span class="sxs-lookup"><span data-stu-id="b0e44-189">_pfSyncEnabled_</span></span>
  
<span data-ttu-id="b0e44-190">指定是否请求的成本推断方法当前重写或不。</span><span class="sxs-lookup"><span data-stu-id="b0e44-190">Specifies whether the requested cost heuristic is currently overridden or not.</span></span> <span data-ttu-id="b0e44-191">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-191">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-192">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-192">Return values</span></span>

|<span data-ttu-id="b0e44-193">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-193">Value</span></span>|<span data-ttu-id="b0e44-194">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-194">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-195">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-195">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-196">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-196">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-197">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-197">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-198">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-198">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-199">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-199">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-200">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-200">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-201">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-201">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-202">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-202">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a><span data-ttu-id="b0e44-203">ILSCLocalSyncClient::GetFileStatus</span><span class="sxs-lookup"><span data-stu-id="b0e44-203">ILSCLocalSyncClient::GetFileStatus</span></span>

<span data-ttu-id="b0e44-204">GetFileStatus 用于收集特定文件的信息： 它具有挂起的通信与服务器副本中，如果存在在缓存中，还是 Office 2013 具有充分最多的本地副本的日期数据。</span><span class="sxs-lookup"><span data-stu-id="b0e44-204">GetFileStatus is used to gather information for a specific file: whether it exists in the cache, if it has pending communication with the server copy, and if Office 2013 has the most up to date data from the local copy.</span></span> <span data-ttu-id="b0e44-205">需要[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)值来确定 CsiSyncClient COM 对象为哪些信息的按位标志查询。</span><span class="sxs-lookup"><span data-stu-id="b0e44-205">It requires a bitwise flag of [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag) values to determine what information the CsiSyncClient COM object is to query for.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-206">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-206">Parameters</span></span>

 <span data-ttu-id="b0e44-207">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-207">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0e44-208">一个字符串，用于标识客户端上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-208">The string which identifies the file on the client.</span></span> <span data-ttu-id="b0e44-209">此值必须为非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-209">This value must be non-empty, with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0e44-210">_sfRequestedStatus_</span><span class="sxs-lookup"><span data-stu-id="b0e44-210">_sfRequestedStatus_</span></span>
  
<span data-ttu-id="b0e44-211">一个标志它定义要返回的信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-211">A flag which defines what information to return.</span></span> <span data-ttu-id="b0e44-212">请参阅[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-212">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
 <span data-ttu-id="b0e44-213">_pbstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-213">_pbstrFileSystemPath_</span></span>
  
<span data-ttu-id="b0e44-214">该字符串标识标识_bstrResourceID_客户端上的文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b0e44-214">The string which identifies the location of the file identified by  _bstrResourceID_ on the client.</span></span> <span data-ttu-id="b0e44-215">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-215">Must not be null.</span></span> 
  
 <span data-ttu-id="b0e44-216">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="b0e44-216">_pbstrETag_</span></span>
  
<span data-ttu-id="b0e44-217">一个字符串，其中将包含由_bstrResourceID_标识的文件的 eTag。</span><span class="sxs-lookup"><span data-stu-id="b0e44-217">A string which will contain the eTag for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="b0e44-218">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-218">Must not be null.</span></span> 
  
 <span data-ttu-id="b0e44-219">_psfFileStatus_</span><span class="sxs-lookup"><span data-stu-id="b0e44-219">_psfFileStatus_</span></span>
  
<span data-ttu-id="b0e44-220">将包含通过由_bstrResourceID_标识文件_sfRequestedStatus_请求的状态标志。</span><span class="sxs-lookup"><span data-stu-id="b0e44-220">A flag which will contain the status requested via  _sfRequestedStatus_ for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="b0e44-221">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-221">Must not be null.</span></span> <span data-ttu-id="b0e44-222">请参阅[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-222">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-223">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-223">Return values</span></span>

|<span data-ttu-id="b0e44-224">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-224">Value</span></span>|<span data-ttu-id="b0e44-225">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-225">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-226">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-226">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-227">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-227">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-228">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-228">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-229">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-229">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-230">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0e44-230">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0e44-231">在缓存中不存在_bstrResourceID_由指定的文件信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-231">The file information specified by  _bstrResourceID_ does not exist in the cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-232">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0e44-232">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="b0e44-233">请求 LSCStatusFlag_LocalFileUnchanged 或_bstrResourceID_指定的文件已锁定或丢失。</span><span class="sxs-lookup"><span data-stu-id="b0e44-233">LSCStatusFlag_LocalFileUnchanged was requested or the file specified by  _bstrResourceID_ is locked or missing.</span></span>  <br/> |
|<span data-ttu-id="b0e44-234">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-234">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-235">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-235">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-236">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-236">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-237">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-237">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a><span data-ttu-id="b0e44-238">ILSCLocalSyncClient::GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="b0e44-238">ILSCLocalSyncClient::GetSupportedFileExtensions</span></span>
<span data-ttu-id="b0e44-239"><a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-239"></span></span>

<span data-ttu-id="b0e44-240">GetSupportedFileExtensions 返回当前受支持的 CsiSyncClient COM 对象的管道分隔的文件扩展名的列表。</span><span class="sxs-lookup"><span data-stu-id="b0e44-240">GetSupportedFileExtensions returns a list of pipe-delimited file extensions which are currently supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0e44-241">请注意，此列表可能会更改，并使用者将通过[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (请参阅 EventOccured) 中提供的 IPartnerActivityCallback 对象更改的通知。</span><span class="sxs-lookup"><span data-stu-id="b0e44-241">Note that this list may change, and the consumer will be notified of a change via the IPartnerActivityCallback object provided on [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (See EventOccured).</span></span> 
  
<span data-ttu-id="b0e44-242">字符串的示例返回如下所示:"| docx | docm | pptx |"</span><span class="sxs-lookup"><span data-stu-id="b0e44-242">An example of the string returned is as follows: "|docx|docm|pptx|"</span></span>
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-243">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-243">Parameters</span></span>

 <span data-ttu-id="b0e44-244">_pbstrSupportedFileExtensions_</span><span class="sxs-lookup"><span data-stu-id="b0e44-244">_pbstrSupportedFileExtensions_</span></span>
  
<span data-ttu-id="b0e44-245">要设置与一组管道分隔 CsiSyncClient COM 对象支持的文件扩展名的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-245">A string to be set with a pipe-delimited set of file extensions supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0e44-246">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-246">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-247">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-247">Return values</span></span>

|<span data-ttu-id="b0e44-248">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-248">Value</span></span>|<span data-ttu-id="b0e44-249">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-249">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-250">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-250">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-251">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-251">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-252">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-252">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-253">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-253">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-254">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-254">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-255">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-255">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-256">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-256">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-257">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-257">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a><span data-ttu-id="b0e44-258">ILSCLocalSyncClient::Initialize</span><span class="sxs-lookup"><span data-stu-id="b0e44-258">ILSCLocalSyncClient::Initialize</span></span>
<span data-ttu-id="b0e44-259"><a name="ILSCLocalSyncClient_Initialize"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-259"></span></span>

<span data-ttu-id="b0e44-260">初始化必须是第一种方法调用。</span><span class="sxs-lookup"><span data-stu-id="b0e44-260">Initialize must be the first method called.</span></span> <span data-ttu-id="b0e44-261">否则，所有其他 Api 将返回 E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="b0e44-261">Otherwise, all other APIs will return E_LSC_NOTINITIALIZED.</span></span> <span data-ttu-id="b0e44-262">已初始化对象上调用 Initialize，则返回 S_OK 和不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b0e44-262">Calling Initialize on an already initialized object returns S_OK and does nothing.</span></span> <span data-ttu-id="b0e44-263">如果返回 E_LSC_CACHEMISMATCH，呼叫者可能会调用[ILSCLocalSyncClient::ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)删除与给定 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-263">If E_LSC_CACHEMISMATCH is returned, the caller may call [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) to delete the cache associated with the given SuppliedID.</span></span> <span data-ttu-id="b0e44-264">但是，在这种情况下其他 Api 仍将返回 E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="b0e44-264">However, in this case other APIs will still return E_LSC_NOTINITIALIZED.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-265">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-265">Parameters</span></span>

 <span data-ttu-id="b0e44-266">_bstrSuppliedID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-266">_bstrSuppliedID_</span></span>
  
<span data-ttu-id="b0e44-267">标识使用者和其缓存使用。</span><span class="sxs-lookup"><span data-stu-id="b0e44-267">Identifies the consumer and which cache to use.</span></span> <span data-ttu-id="b0e44-268">非空值必须为最多 32 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-268">Must be non-empty with a maximum of 32 characters.</span></span> 
  
 <span data-ttu-id="b0e44-269">_bstrProgID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-269">_bstrProgID_</span></span>
  
<span data-ttu-id="b0e44-270">标识双向通信使用者的 COM 的对象。</span><span class="sxs-lookup"><span data-stu-id="b0e44-270">Identifies the consumer's COM object for two-way communication.</span></span> <span data-ttu-id="b0e44-271">非空值必须为最多为 39 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-271">Must be non-empty with a maximum of 39 characters.</span></span> <span data-ttu-id="b0e44-272">请参阅[\<ProgID\>键](https://docs.microsoft.com/en-us/windows/desktop/com/-progid--key)有关 Progid 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-272">See [\<ProgID\> Key](https://docs.microsoft.com/en-us/windows/desktop/com/-progid--key) for more information about ProgIDs.</span></span> 
  
 <span data-ttu-id="b0e44-273">_bstrFileSystemDirectoryHint_</span><span class="sxs-lookup"><span data-stu-id="b0e44-273">_bstrFileSystemDirectoryHint_</span></span>
  
<span data-ttu-id="b0e44-274">标识将在其中存储的本地文件的根目录。</span><span class="sxs-lookup"><span data-stu-id="b0e44-274">Identifies the directory root in which local files will be stored.</span></span> <span data-ttu-id="b0e44-275">非空值必须为最多包含 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-275">Must be non-empty with a maximum of 256 characters.</span></span> <span data-ttu-id="b0e44-276">目录必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="b0e44-276">The directory must already exist.</span></span> 
  
 <span data-ttu-id="b0e44-277">_pEventCallback_</span><span class="sxs-lookup"><span data-stu-id="b0e44-277">_pEventCallback_</span></span>
  
<span data-ttu-id="b0e44-278">更改将通知 CsiSyncClient 回调接口。</span><span class="sxs-lookup"><span data-stu-id="b0e44-278">The callback interface which CsiSyncClient will notify on changes.</span></span> <span data-ttu-id="b0e44-279">请参阅 IPartnerActivityCallback::EventOccurred。</span><span class="sxs-lookup"><span data-stu-id="b0e44-279">See IPartnerActivityCallback::EventOccurred.</span></span> <span data-ttu-id="b0e44-280">此值不为 null。</span><span class="sxs-lookup"><span data-stu-id="b0e44-280">This value must not be null.</span></span> 
  
 <span data-ttu-id="b0e44-281">_pfCreatedNewCache_</span><span class="sxs-lookup"><span data-stu-id="b0e44-281">_pfCreatedNewCache_</span></span>
  
<span data-ttu-id="b0e44-282">返回一个新的缓存是否已创建。</span><span class="sxs-lookup"><span data-stu-id="b0e44-282">Returns whether a new cache was created.</span></span> <span data-ttu-id="b0e44-283">如果没有缓存与 SuppliedID 关联，将创建一个。</span><span class="sxs-lookup"><span data-stu-id="b0e44-283">If no cache is associated with the SuppliedID, one will be created.</span></span> <span data-ttu-id="b0e44-284">此值不为 null。</span><span class="sxs-lookup"><span data-stu-id="b0e44-284">This value must not be null.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-285">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-285">Return values</span></span>

|<span data-ttu-id="b0e44-286">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-286">Value</span></span>|<span data-ttu-id="b0e44-287">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-287">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-288">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-288">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-289">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-289">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-290">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-290">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-291">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-291">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-292">E_LSC_CACHEMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0e44-292">E_LSC_CACHEMISMATCH</span></span>  <br/> |<span data-ttu-id="b0e44-293">SuppliedID 已具有与其关联的缓存，但具有不同的 ProgId 或 FileSystemDirectoryHint 比提供。</span><span class="sxs-lookup"><span data-stu-id="b0e44-293">A SuppliedID already has a cache associated with it, but has a different ProgId or FileSystemDirectoryHint than the ones provided.</span></span>  <br/> |
|<span data-ttu-id="b0e44-294">E_LSC_DIRECTORYHINTCONFLICT</span><span class="sxs-lookup"><span data-stu-id="b0e44-294">E_LSC_DIRECTORYHINTCONFLICT</span></span>  <br/> |<span data-ttu-id="b0e44-295">FileSystemDirectoryHint （或子文件夹） 不同缓存上已存在。</span><span class="sxs-lookup"><span data-stu-id="b0e44-295">The FileSystemDirectoryHint (or a subfolder) already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-296">E_LAC_PROGIDCONFLICT</span><span class="sxs-lookup"><span data-stu-id="b0e44-296">E_LAC_PROGIDCONFLICT</span></span>  <br/> |<span data-ttu-id="b0e44-297">不同缓存上已存在 ProgID。</span><span class="sxs-lookup"><span data-stu-id="b0e44-297">The ProgID already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-298">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-298">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-299">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-299">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a><span data-ttu-id="b0e44-300">ILSCLocalSyncClient::LocalFileChange</span><span class="sxs-lookup"><span data-stu-id="b0e44-300">ILSCLocalSyncClient::LocalFileChange</span></span>
<span data-ttu-id="b0e44-301"><a name="ILSCLocalSyncClient_LocalFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-301"></span></span>

<span data-ttu-id="b0e44-302">LocalFileChange 用于告知 CsiSyncClient COM 对象，以尝试上载指定的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-302">LocalFileChange is used to tell the CsiSyncClient COM object to attempt to upload the specified file.</span></span> <span data-ttu-id="b0e44-303">该方法将准备上载，包括读取文件的当前内容的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-303">The method will prepare the file for upload, including reading the file's current contents.</span></span> <span data-ttu-id="b0e44-304">如果上载已挂起，将放弃上次上载并准备好的新内容上载。</span><span class="sxs-lookup"><span data-stu-id="b0e44-304">If an upload is already pending, the previous upload will be discarded and the new contents prepared for upload.</span></span> <span data-ttu-id="b0e44-305">如果文件已打开，在应用程序中进行编辑，此方法将返回 S_OK 而不准备的上载 （应用程序应该已执行此步骤时更改） 的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-305">If the file is open for editing in an application, this method will return S_OK without preparing the file for upload (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="b0e44-306">此方法将允许上载如果它被标记为上载被阻止之前 （请参阅[ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)）。</span><span class="sxs-lookup"><span data-stu-id="b0e44-306">This method will allow uploads if it was marked as uploads blocked previously (see [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)).</span></span>
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-307">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-307">Parameters</span></span>

 <span data-ttu-id="b0e44-308">_bstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-308">_bstrFileSystemPath_</span></span>
  
<span data-ttu-id="b0e44-309">一个字符串，用于标识客户端上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-309">A string which identifies the file on the client.</span></span> <span data-ttu-id="b0e44-310">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-310">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0e44-311">此路径必须是由 FileSystemDirectoryHint 时进行[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)调用指定目录树中。</span><span class="sxs-lookup"><span data-stu-id="b0e44-311">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was made.</span></span> 
  
 <span data-ttu-id="b0e44-312">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-312">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0e44-313">标识文件的资源 Id 字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-313">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0e44-314">此值必须为非空最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-314">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0e44-315">_bstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-315">_bstrWebPath_</span></span>
  
<span data-ttu-id="b0e44-316">一个字符串，用于标识的服务器上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-316">A string which identifies the file on the server.</span></span> <span data-ttu-id="b0e44-317">此值必须为非空、 有效的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。</span><span class="sxs-lookup"><span data-stu-id="b0e44-317">This value must be non-empty, valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by http://support.microsoft.com/kb/208427.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-318">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-318">Return values</span></span>

|<span data-ttu-id="b0e44-319">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-319">Value</span></span>|<span data-ttu-id="b0e44-320">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-320">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-321">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-321">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-322">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-322">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-323">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-323">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-324">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-324">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-325">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0e44-325">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0e44-326">_BstrFileSystemPath_指定的文件具有不同的资源 Id 与指定。</span><span class="sxs-lookup"><span data-stu-id="b0e44-326">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span> <span data-ttu-id="b0e44-327">类型的事件，则返回此错误时，会发送 LSCEventType_OnFilePathConflict。</span><span class="sxs-lookup"><span data-stu-id="b0e44-327">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="b0e44-328">请参阅[ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-328">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="b0e44-329">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0e44-329">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0e44-330">文件已删除的中端操作。</span><span class="sxs-lookup"><span data-stu-id="b0e44-330">The file was deleted mid-operation.</span></span>  <br/> |
|<span data-ttu-id="b0e44-331">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b0e44-331">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="b0e44-332">由 CsiSyncClient COM 对象不支持的给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0e44-332">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0e44-333">请参阅[ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-333">See [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions).</span></span>  <br/> |
|<span data-ttu-id="b0e44-334">E_LSC_FILEUPTODATE</span><span class="sxs-lookup"><span data-stu-id="b0e44-334">E_LSC_FILEUPTODATE</span></span>  <br/> |<span data-ttu-id="b0e44-335">COM 对象未安排上载，因为在缓存中的文件从磁盘的最新更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-335">The COM object did not schedule an upload because the file in the cache had the most recent changes from the disk.</span></span>  <br/> |
|<span data-ttu-id="b0e44-336">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0e44-336">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="b0e44-337">缺失或被锁定， _bstrFileSystemPath_指定的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-337">The file specified by  _bstrFileSystemPath_ is missing or locked.</span></span>  <br/> |
|<span data-ttu-id="b0e44-338">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0e44-338">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0e44-339">给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0e44-339">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0e44-340">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-340">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-341">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-341">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-342">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0e44-342">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="b0e44-343">_BstrResourceID_指定的文件具有不同 FileSystemPath 比指定。</span><span class="sxs-lookup"><span data-stu-id="b0e44-343">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="b0e44-344">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-344">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-345">指定的文件已具有挂起的不同缓存中的更改，并且尚未不能与使用者的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-345">The file specified already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-347">提供 WebPath 低于其他的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-347">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-348">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-348">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-349">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-349">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a><span data-ttu-id="b0e44-350">ILSCLocalSyncClient::RenameFile</span><span class="sxs-lookup"><span data-stu-id="b0e44-350">ILSCLocalSyncClient::RenameFile</span></span>
<span data-ttu-id="b0e44-351"><a name="ILSCLocalSyncClient_RenameFile"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-351"></span></span>

<span data-ttu-id="b0e44-352">RenameFile 将为给定的资源 Id 关联的新 URL 和本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-352">RenameFile will associate a new URL and local path for a given ResourceID.</span></span> <span data-ttu-id="b0e44-353">如果资源 Id 指定的文件不存在在缓存中，将进行尝试创建并将其标记为下载。</span><span class="sxs-lookup"><span data-stu-id="b0e44-353">If the file specified by the ResourceID doesn't already exist in the cache, an attempt will be made to create it and mark it for download.</span></span>
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-354">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-354">Parameters</span></span>

 <span data-ttu-id="b0e44-355">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-355">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0e44-356">标识文件的资源 Id 字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-356">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0e44-357">此值必须为非空最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-357">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0e44-358">_bstrNewFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-358">_bstrNewFileSystemPath_</span></span>
  
<span data-ttu-id="b0e44-359">一个字符串，用于指定文件的新本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-359">A string which specifies the new local path for the file.</span></span> <span data-ttu-id="b0e44-360">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-360">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0e44-361">此路径必须是由 FileSystemDirectoryHint 进行初始化通话时指定目录树中。</span><span class="sxs-lookup"><span data-stu-id="b0e44-361">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span> 
  
 <span data-ttu-id="b0e44-362">_bstrNewWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-362">_bstrNewWebPath_</span></span>
  
<span data-ttu-id="b0e44-363">一个指定文件的新 URL 的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-363">A string which specifies the new URL for the file.</span></span> <span data-ttu-id="b0e44-364">此值必须为非空有效的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。</span><span class="sxs-lookup"><span data-stu-id="b0e44-364">This value must be non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by http://support.microsoft.com/kb/208427.</span></span> 
  
 <span data-ttu-id="b0e44-365">_fBlockUploads_</span><span class="sxs-lookup"><span data-stu-id="b0e44-365">_fBlockUploads_</span></span>
  
<span data-ttu-id="b0e44-366">指定是否当前允许文件将上载到新位置。</span><span class="sxs-lookup"><span data-stu-id="b0e44-366">Specifies whether uploads to the new location are allowed currently.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-367">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-367">Return values</span></span>

|<span data-ttu-id="b0e44-368">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-368">Value</span></span>|<span data-ttu-id="b0e44-369">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-369">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-370">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-370">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-371">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-371">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-372">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-372">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-373">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-373">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-374">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0e44-374">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0e44-375">_BstrNewFileSystemPath_或_bstrNewWebPath_已经存在任何缓存中的另一个文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-375">The  _bstrNewFileSystemPath_ or  _bstrNewWebPath_ already exist on another file in any cache.</span></span> <span data-ttu-id="b0e44-376">类型的事件，则返回此错误时，会发送 LSCEventType_OnFilePathConflict。</span><span class="sxs-lookup"><span data-stu-id="b0e44-376">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="b0e44-377">请参阅[ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-377">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="b0e44-378">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0e44-378">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0e44-379">运行此方法时，从缓存中已删除的文件信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-379">The file information was deleted from the cache while this method was running.</span></span>  <br/> |
|<span data-ttu-id="b0e44-380">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0e44-380">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0e44-381">给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0e44-381">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0e44-382">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-382">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-383">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-383">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-384">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-384">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-385">指定的文件当前 Office 应用程序中进行同步。</span><span class="sxs-lookup"><span data-stu-id="b0e44-385">The file specified is currently synchronizing in an Office application.</span></span>  <br/> |
|<span data-ttu-id="b0e44-386">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-386">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-387">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-387">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a><span data-ttu-id="b0e44-388">ILSCLocalSyncClient::ResetCache</span><span class="sxs-lookup"><span data-stu-id="b0e44-388">ILSCLocalSyncClient::ResetCache</span></span>
<span data-ttu-id="b0e44-389"><a name="ILSCLocalSyncClient_ResetCache"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-389"></span></span>

<span data-ttu-id="b0e44-390">ResetCache 将删除与已提供在初始化 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-390">ResetCache will delete the cache associated with the SuppliedID that was provided on Initialize.</span></span> <span data-ttu-id="b0e44-391">这包括的所有文件信息，但将保留在客户端和服务器上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-391">This includes all of the file information, but will leave the files on both the client and the server.</span></span> <span data-ttu-id="b0e44-392">此方法还使处于部分未初始化的状态的对象。</span><span class="sxs-lookup"><span data-stu-id="b0e44-392">This method also leaves the object in a partially uninitialized state.</span></span> <span data-ttu-id="b0e44-393">唯一有效呼叫后这是[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)或[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-393">The only valid calls after this are [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) or [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="b0e44-394">如果初始化失败并返回 E_LSC_CACHEMISMATCH，可能会调用此方法将删除与已附带的失败呼叫 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-394">This method MAY be called if Initialize fails and returns E_LSC_CACHEMISMATCH, and will delete the cache associated with the SuppliedID that was provided with the failing call.</span></span>
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a><span data-ttu-id="b0e44-395">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-395">Parameters</span></span>

<span data-ttu-id="b0e44-396">无</span><span class="sxs-lookup"><span data-stu-id="b0e44-396">None</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-397">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-397">Return values</span></span>

|<span data-ttu-id="b0e44-398">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-398">Value</span></span>|<span data-ttu-id="b0e44-399">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-399">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-400">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-400">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-401">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-401">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-402">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-402">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-403">在过去未成功调用[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 。</span><span class="sxs-lookup"><span data-stu-id="b0e44-403">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was not successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-404">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-404">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-405">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-405">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a><span data-ttu-id="b0e44-406">ILSCLocalSyncClient::ServerFileChange</span><span class="sxs-lookup"><span data-stu-id="b0e44-406">ILSCLocalSyncClient::ServerFileChange</span></span>
<span data-ttu-id="b0e44-407"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-407"></span></span>

<span data-ttu-id="b0e44-408">ServerFileChange 告知 CsiSyncClient COM 对象标记指定的文件进行下载。</span><span class="sxs-lookup"><span data-stu-id="b0e44-408">ServerFileChange tells the CsiSyncClient COM object to mark the specified file for download.</span></span> <span data-ttu-id="b0e44-409">编辑 Office 应用程序中打开该文件时，此方法将返回 S_OK 而不将标记 （应用程序应该已执行此步骤时更改） 下载的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-409">If the file is open in an Office application for edit, this method will return S_OK without marking the file for download (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="b0e44-410">此方法将允许下载如果它被标记为下载阻止以前 （请参阅 RenameFile）。</span><span class="sxs-lookup"><span data-stu-id="b0e44-410">This method will allow downloads if it was marked as downloads blocked previously (see RenameFile).</span></span>
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-411">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-411">Parameters</span></span>

|<span data-ttu-id="b0e44-412">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-412">Parameter</span></span>|<span data-ttu-id="b0e44-413">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-413">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-414">bstrFileSystemPath</span><span class="sxs-lookup"><span data-stu-id="b0e44-414">bstrFileSystemPath</span></span>  <br/> |<span data-ttu-id="b0e44-415">一个字符串，用于标识客户端上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-415">A string which identifies the file on the client.</span></span> <span data-ttu-id="b0e44-416">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-416">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0e44-417">此路径必须是由 FileSystemDirectoryHint 进行初始化通话时指定目录树中。</span><span class="sxs-lookup"><span data-stu-id="b0e44-417">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0e44-418">bstrResourceID</span><span class="sxs-lookup"><span data-stu-id="b0e44-418">bstrResourceID</span></span>  <br/> |<span data-ttu-id="b0e44-419">标识文件的资源 Id 字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-419">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0e44-420">此值必须为非空最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b0e44-420">This value must be non-empty with a maximum of 128 characters.</span></span>  <br/> |
|<span data-ttu-id="b0e44-421">bstrWebPath</span><span class="sxs-lookup"><span data-stu-id="b0e44-421">bstrWebPath</span></span>  <br/> |<span data-ttu-id="b0e44-422">一个字符串，用于标识的服务器上的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-422">A string which identifies the file on the server.</span></span> <span data-ttu-id="b0e44-423">此值必须是有效的非空的 URL，但不得多于 INTERNET_MAX_URL_LENGTH，定义的http://support.microsoft.com/kb/208427。</span><span class="sxs-lookup"><span data-stu-id="b0e44-423">This value must be a non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by http://support.microsoft.com/kb/208427.</span></span>  <br/> |
   
##### <a name="return-values"></a><span data-ttu-id="b0e44-424">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-424">Return values</span></span>

|<span data-ttu-id="b0e44-425">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-425">Value</span></span>|<span data-ttu-id="b0e44-426">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-426">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-427">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-427">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-428">未能设置缓存连接状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-428">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="b0e44-429">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0e44-429">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0e44-430">_BstrFileSystemPath_指定的文件具有不同的资源 Id 与指定。</span><span class="sxs-lookup"><span data-stu-id="b0e44-430">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span>  <br/> |
|<span data-ttu-id="b0e44-431">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b0e44-431">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="b0e44-432">由 CsiSyncClient COM 对象不支持的给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0e44-432">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0e44-433">请参阅 GetSupportedFileExtensions。</span><span class="sxs-lookup"><span data-stu-id="b0e44-433">See GetSupportedFileExtensions.</span></span>  <br/> |
|<span data-ttu-id="b0e44-434">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0e44-434">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0e44-435">中间操作中已删除文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-435">The file was deleted in mid-operation.</span></span>  <br/> |
|<span data-ttu-id="b0e44-436">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-436">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-437">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-437">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-438">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0e44-438">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0e44-439">给定的 FileSystemPath 不是由 FileSystemDirectoryHint 进行初始化通话时指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0e44-439">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0e44-440">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-440">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-441">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-441">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-442">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0e44-442">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="b0e44-443">_BstrResourceID_指定的文件具有不同 FileSystemPath 比指定。</span><span class="sxs-lookup"><span data-stu-id="b0e44-443">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="b0e44-444">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-444">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-445">指定的文件已具有挂起的不同缓存中的更改，并且尚未不能与使用者的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-445">The specified file already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="b0e44-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="b0e44-447">提供 WebPath 低于其他的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-447">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-448">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-448">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-449">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-449">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a><span data-ttu-id="b0e44-450">ILSCLocalSyncClient::SetClientConnectivityState</span><span class="sxs-lookup"><span data-stu-id="b0e44-450">ILSCLocalSyncClient::SetClientConnectivityState</span></span>
<span data-ttu-id="b0e44-451"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-451"></span></span>

<span data-ttu-id="b0e44-452">将缓存设置为联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-452">Sets the cache into an online or offline state.</span></span> <span data-ttu-id="b0e44-453">如果脱机，Office 将尝试与该缓存，而不考虑每个单独的文件_fBlockUploads_设置中的任何文件的服务器进行通信。</span><span class="sxs-lookup"><span data-stu-id="b0e44-453">If offline, Office will not attempt to communicate with the server for any files in that cache, regardless of each individual file's  _fBlockUploads_ setting.</span></span> 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-454">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-454">Parameters</span></span>

 <span data-ttu-id="b0e44-455">_fIsOnline_</span><span class="sxs-lookup"><span data-stu-id="b0e44-455">_fIsOnline_</span></span>
  
<span data-ttu-id="b0e44-456">确定连接状态的缓存的布尔值。</span><span class="sxs-lookup"><span data-stu-id="b0e44-456">A boolean determining the connectivity state of the cache.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-457">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-457">Return values</span></span>

|<span data-ttu-id="b0e44-458">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-458">Value</span></span>|<span data-ttu-id="b0e44-459">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-459">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-460">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-460">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-461">未能设置缓存连接状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-461">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="b0e44-462">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-462">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-463">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-463">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-464">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-464">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-465">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-465">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-466">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-466">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-467">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-467">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a><span data-ttu-id="b0e44-468">ILSCLocalSyncClient::SetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="b0e44-468">ILSCLocalSyncClient::SetClientNetworkSyncPermission</span></span>
<span data-ttu-id="b0e44-469"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-469"></span></span>

<span data-ttu-id="b0e44-470">是重写用于 SetClientNetworkSyncPermission 或 restoreOffice 的同步启发的网络成本和电源使用率。</span><span class="sxs-lookup"><span data-stu-id="b0e44-470">SetClientNetworkSyncPermission is used to either override or restoreOffice's synchronizing heuristics for network cost and power usage.</span></span> <span data-ttu-id="b0e44-471">当在 3g 或其他跟踪成本很高网络，或在与要插入的电池上运行时，可以选择 Office 之前多此时阻止网络通信。</span><span class="sxs-lookup"><span data-stu-id="b0e44-471">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span> <span data-ttu-id="b0e44-472">此 API 的使用者可以使用它覆盖 Office 的启发并强制同步发生。</span><span class="sxs-lookup"><span data-stu-id="b0e44-472">The consumer of this API can use it to override Office's heuristics and force synchronizing to occur.</span></span>
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-473">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-473">Parameters</span></span>

 <span data-ttu-id="b0e44-474">_nspType_</span><span class="sxs-lookup"><span data-stu-id="b0e44-474">_nspType_</span></span>
  
<span data-ttu-id="b0e44-475">它定义重写的成本推断方法的标志。</span><span class="sxs-lookup"><span data-stu-id="b0e44-475">A flag which defines which cost heuristic to override.</span></span> <span data-ttu-id="b0e44-476">请参阅[枚举 LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="b0e44-476">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span>
  
 <span data-ttu-id="b0e44-477">_fEnableSync_</span><span class="sxs-lookup"><span data-stu-id="b0e44-477">_fEnableSync_</span></span>
  
<span data-ttu-id="b0e44-478">指定是否强制执行同步上，因此重写该成本推断方法，或不再重写。</span><span class="sxs-lookup"><span data-stu-id="b0e44-478">Specifies whether to force synchronizing on, thus overriding that cost heuristic, or to no longer override it.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-479">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-479">Return values</span></span>

|<span data-ttu-id="b0e44-480">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-480">Value</span></span>|<span data-ttu-id="b0e44-481">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-481">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-482">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-482">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-483">重写同步试探方法失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-483">Failure to override synchronizing heuristics.</span></span>  <br/> |
|<span data-ttu-id="b0e44-484">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-484">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-485">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-485">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-486">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-486">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-487">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-487">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a><span data-ttu-id="b0e44-488">ILSCLocalSyncClient::Uninitialize</span><span class="sxs-lookup"><span data-stu-id="b0e44-488">ILSCLocalSyncClient::Uninitialize</span></span>
<span data-ttu-id="b0e44-489"><a name="ILSCLocalSyncClient_Uninitialize"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-489"></span></span>

<span data-ttu-id="b0e44-490">卸载从的 COM 对象缓存，并执行结束操作。</span><span class="sxs-lookup"><span data-stu-id="b0e44-490">Unloads the cache from the COM object and perform closing operations.</span></span> <span data-ttu-id="b0e44-491">[ILSCLocalSyncClient::Uninitialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)必须在销毁 COM 对象之前调用。</span><span class="sxs-lookup"><span data-stu-id="b0e44-491">[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) MUST be called before destroying the COM object.</span></span> <span data-ttu-id="b0e44-492">调用后，可调用任何其他 Api、 COM 对象必须销毁和创建一个新的如果想要继续操作。</span><span class="sxs-lookup"><span data-stu-id="b0e44-492">Once called, no other APIs can be called, the COM object MUST be destroyed and a new one created if you wish to continue operations.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a><span data-ttu-id="b0e44-493">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-493">Parameters</span></span>

<span data-ttu-id="b0e44-494">无。</span><span class="sxs-lookup"><span data-stu-id="b0e44-494">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-495">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-495">Return values</span></span>

|<span data-ttu-id="b0e44-496">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-496">Value</span></span>|<span data-ttu-id="b0e44-497">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-497">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-498">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-498">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-499">取消初始化失败。</span><span class="sxs-lookup"><span data-stu-id="b0e44-499">Failure to uninitialize.</span></span>  <br/> |
|<span data-ttu-id="b0e44-500">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0e44-500">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0e44-501">[ILSCLocalSyncClient::Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)尚未成功调用过去。</span><span class="sxs-lookup"><span data-stu-id="b0e44-501">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0e44-502">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-502">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-503">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-503">The call succeeded.</span></span>  <br/> |
   
### <a name="interface-ienumlscevent"></a><span data-ttu-id="b0e44-504">接口 IEnumLSCEvent</span><span class="sxs-lookup"><span data-stu-id="b0e44-504">Interface IEnumLSCEvent</span></span>

<span data-ttu-id="b0e44-505">此接口表示 ILSCEvent 事件的列表。</span><span class="sxs-lookup"><span data-stu-id="b0e44-505">This interface represents a list of ILSCEvent events.</span></span>
  
<span data-ttu-id="b0e44-506">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0e44-506">**Public member functions**</span></span>

#### <a name="ienumlsceventfnext"></a><span data-ttu-id="b0e44-507">IEnumLSCEvent::FNext</span><span class="sxs-lookup"><span data-stu-id="b0e44-507">IEnumLSCEvent::FNext</span></span>

<span data-ttu-id="b0e44-508">从的事件列表中检索下一个事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-508">Retrieves the next event from the list of events.</span></span>
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-509">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-509">Parameters</span></span>

 <span data-ttu-id="b0e44-510">_ppiLSCEvent_</span><span class="sxs-lookup"><span data-stu-id="b0e44-510">_ppiLSCEvent_</span></span>
  
<span data-ttu-id="b0e44-511">指向 ILSCEvent 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b0e44-511">A pointer to an ILSCEvent interface.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-512">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-512">Return values</span></span>

|<span data-ttu-id="b0e44-513">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-513">Value</span></span>|<span data-ttu-id="b0e44-514">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-514">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-515">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-515">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-516">没有详细事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-516">There are no more events.</span></span>  <br/> |
|<span data-ttu-id="b0e44-517">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-517">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-518">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-518">The call was successful.</span></span>  <br/> |
   
#### <a name="ienumlsceventreset"></a><span data-ttu-id="b0e44-519">IEnumLSCEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="b0e44-519">IEnumLSCEvent::Reset</span></span>

<span data-ttu-id="b0e44-520">将枚举器重重置为第一个事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-520">Resets the enumerator to the first event.</span></span>
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a><span data-ttu-id="b0e44-521">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-521">Parameters</span></span>

<span data-ttu-id="b0e44-522">无。</span><span class="sxs-lookup"><span data-stu-id="b0e44-522">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-523">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-523">Return values</span></span>

<span data-ttu-id="b0e44-524">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-524">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent"></a><span data-ttu-id="b0e44-525">接口 ILSCEvent</span><span class="sxs-lookup"><span data-stu-id="b0e44-525">Interface ILSCEvent</span></span>

<span data-ttu-id="b0e44-526">此接口表示同步事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-526">This interface represents a synchronizing event.</span></span> <span data-ttu-id="b0e44-527">可以从界面检索有关事件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-527">All information about the event can be retrieved from the interface.</span></span>
  
<span data-ttu-id="b0e44-528">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0e44-528">**Public member functions**</span></span>

#### <a name="ilsceventgetconflictstatus"></a><span data-ttu-id="b0e44-529">ILSCEvent::GetConflictStatus</span><span class="sxs-lookup"><span data-stu-id="b0e44-529">ILSCEvent::GetConflictStatus</span></span>

<span data-ttu-id="b0e44-530">注意，此值填充[ILSCLocalSyncClient::GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)调用时，不时事件的创建，以便您只具有该文件，不文件冲突状态更改时的状态的当前状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-530">Note that this value is populated when [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) is called, not when the event was created, so you will only have the current status of the file, not the status of the file when the conflict status changed.</span></span> 
  
<span data-ttu-id="b0e44-531">事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnLocalConflictStateChanged 时，仅将填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0e44-531">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnLocalConflictStateChanged.</span></span> 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-532">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-532">Parameters</span></span>

 <span data-ttu-id="b0e44-533">_pfIsInConflict_</span><span class="sxs-lookup"><span data-stu-id="b0e44-533">_pfIsInConflict_</span></span>
  
<span data-ttu-id="b0e44-534">与事件关联的文件的冲突当前状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-534">The current conflict status of the file associated with the event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-535">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-535">Return values</span></span>

<span data-ttu-id="b0e44-536">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-536">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeterror"></a><span data-ttu-id="b0e44-537">ILSCEvent::GetError</span><span class="sxs-lookup"><span data-stu-id="b0e44-537">ILSCEvent::GetError</span></span>

<span data-ttu-id="b0e44-538">此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。</span><span class="sxs-lookup"><span data-stu-id="b0e44-538">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-539">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-539">Parameters</span></span>

 <span data-ttu-id="b0e44-540">_pnError_</span><span class="sxs-lookup"><span data-stu-id="b0e44-540">_pnError_</span></span>
  
<span data-ttu-id="b0e44-541">与该事件关联的错误。</span><span class="sxs-lookup"><span data-stu-id="b0e44-541">The error associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-542">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-542">Return values</span></span>

<span data-ttu-id="b0e44-543">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-543">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetetag"></a><span data-ttu-id="b0e44-544">ILSCEvent::GetETag</span><span class="sxs-lookup"><span data-stu-id="b0e44-544">ILSCEvent::GetETag</span></span>

<span data-ttu-id="b0e44-545">此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。</span><span class="sxs-lookup"><span data-stu-id="b0e44-545">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-546">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-546">Parameters</span></span>

 <span data-ttu-id="b0e44-547">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="b0e44-547">_pbstrETag_</span></span>
  
<span data-ttu-id="b0e44-548">与此事件关联的 ETag</span><span class="sxs-lookup"><span data-stu-id="b0e44-548">The ETag associated with this event</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-549">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-549">Return values</span></span>

<span data-ttu-id="b0e44-550">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-550">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeteventtype"></a><span data-ttu-id="b0e44-551">ILSCEvent::GetEventType</span><span class="sxs-lookup"><span data-stu-id="b0e44-551">ILSCEvent::GetEventType</span></span>

<span data-ttu-id="b0e44-552">获取该事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-552">Gets the type for this event.</span></span>
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-553">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-553">Parameters</span></span>

 <span data-ttu-id="b0e44-554">_pnEventType_</span><span class="sxs-lookup"><span data-stu-id="b0e44-554">_pnEventType_</span></span>
  
<span data-ttu-id="b0e44-555">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-555">The event type of this event.</span></span> <span data-ttu-id="b0e44-556">有效的值，请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。</span><span class="sxs-lookup"><span data-stu-id="b0e44-556">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for valid values.</span></span> <span data-ttu-id="b0e44-557">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-557">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-558">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-558">Return values</span></span>

|<span data-ttu-id="b0e44-559">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-559">Value</span></span>|<span data-ttu-id="b0e44-560">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-560">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-561">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-561">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-562">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-562">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-563">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-563">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-564">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-564">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a><span data-ttu-id="b0e44-565">ILSCEvent::GetLocalWorkingPath</span><span class="sxs-lookup"><span data-stu-id="b0e44-565">ILSCEvent::GetLocalWorkingPath</span></span>

<span data-ttu-id="b0e44-566">获取此事件的本地工作路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-566">Gets the local working path for this event.</span></span>
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-567">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-567">Parameters</span></span>

 <span data-ttu-id="b0e44-568">_pbstrLocalWorkingPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-568">_pbstrLocalWorkingPath_</span></span>
  
<span data-ttu-id="b0e44-569">此事件与相关文件的本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-569">The local path of the file to which this event pertains.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-570">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-570">Return values</span></span>

<span data-ttu-id="b0e44-571">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-571">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceid"></a><span data-ttu-id="b0e44-572">ILSCEvent::GetResourceID</span><span class="sxs-lookup"><span data-stu-id="b0e44-572">ILSCEvent::GetResourceID</span></span>

<span data-ttu-id="b0e44-573">获取事件的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="b0e44-573">Gets the resource ID for the event.</span></span>
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-574">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-574">Parameters</span></span>

 <span data-ttu-id="b0e44-575">_pbstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0e44-575">_pbstrResourceID_</span></span>
  
<span data-ttu-id="b0e44-576">与此事件关联的文件的资源 Id。</span><span class="sxs-lookup"><span data-stu-id="b0e44-576">The ResourceID of the file associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-577">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-577">Return values</span></span>

<span data-ttu-id="b0e44-578">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-578">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceidattempted"></a><span data-ttu-id="b0e44-579">ILSCEvent::GetResourceIDAttempted</span><span class="sxs-lookup"><span data-stu-id="b0e44-579">ILSCEvent::GetResourceIDAttempted</span></span>

<span data-ttu-id="b0e44-580">事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnFilePathConflict 时，仅将填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0e44-580">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> <span data-ttu-id="b0e44-581">调用[ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient::ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient::RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)与另一个文件置于 Office 文件缓存中，会导致 Web 路径或本地路径冲突时这生成事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-581">When a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) would cause a Web Path or Local Path collision with another file in the Office file cache, this event is generated.</span></span> 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-582">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-582">Parameters</span></span>

 <span data-ttu-id="b0e44-583">_pbstrResourceIDAttempted_</span><span class="sxs-lookup"><span data-stu-id="b0e44-583">_pbstrResourceIDAttempted_</span></span>
  
<span data-ttu-id="b0e44-584">ResourceID 导致获取生成该事件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-584">The ResourceID that caused this event to get generated.</span></span> <span data-ttu-id="b0e44-585">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-585">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-586">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-586">Return values</span></span>

<span data-ttu-id="b0e44-587">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-587">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetsyncerrortype"></a><span data-ttu-id="b0e44-588">ILSCEvent::GetSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="b0e44-588">ILSCEvent::GetSyncErrorType</span></span>

<span data-ttu-id="b0e44-589">此值只填充 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)时发生。</span><span class="sxs-lookup"><span data-stu-id="b0e44-589">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-590">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-590">Parameters</span></span>

 <span data-ttu-id="b0e44-591">_pnSyncErrorType_</span><span class="sxs-lookup"><span data-stu-id="b0e44-591">_pnSyncErrorType_</span></span>
  
<span data-ttu-id="b0e44-592">与该事件关联的错误类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-592">The error type associated with this event.</span></span> <span data-ttu-id="b0e44-593">潜在的值，请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。</span><span class="sxs-lookup"><span data-stu-id="b0e44-593">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for potential values.</span></span> <span data-ttu-id="b0e44-594">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-594">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-595">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-595">Return values</span></span>

|<span data-ttu-id="b0e44-596">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-596">Value</span></span>|<span data-ttu-id="b0e44-597">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-597">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-598">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-598">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-599">一个或多个参数均无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-599">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-600">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-600">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-601">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-601">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetwebpath"></a><span data-ttu-id="b0e44-602">ILSCEvent::GetWebPath</span><span class="sxs-lookup"><span data-stu-id="b0e44-602">ILSCEvent::GetWebPath</span></span>

<span data-ttu-id="b0e44-603">事件[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) LSCEventType_OnFilePathConflict 时，仅将填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0e44-603">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-604">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-604">Parameters</span></span>

 <span data-ttu-id="b0e44-605">_pbstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0e44-605">_pbstrWebPath_</span></span>
  
<span data-ttu-id="b0e44-606">指定与此事件关联的 Web 路径。</span><span class="sxs-lookup"><span data-stu-id="b0e44-606">Specifies the Web Path associated with this event.</span></span> <span data-ttu-id="b0e44-607">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-607">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-608">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-608">Return values</span></span>

<span data-ttu-id="b0e44-609">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-609">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent2"></a><span data-ttu-id="b0e44-610">接口 ILSCEvent2</span><span class="sxs-lookup"><span data-stu-id="b0e44-610">Interface ILSCEvent2</span></span>

<span data-ttu-id="b0e44-611">此接口包含有关同步事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-611">This interface holds additional information about a synchronizing event.</span></span>
  
<span data-ttu-id="b0e44-612">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0e44-612">**Public member functions**</span></span>

#### <a name="ilscevent2geterrorchain"></a><span data-ttu-id="b0e44-613">ILSCEvent2::GetErrorChain</span><span class="sxs-lookup"><span data-stu-id="b0e44-613">ILSCEvent2::GetErrorChain</span></span>

<span data-ttu-id="b0e44-614">获取有关同步事件链错误信息。</span><span class="sxs-lookup"><span data-stu-id="b0e44-614">Gets the error chain information about a synchronizing event.</span></span>
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-615">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-615">Parameters</span></span>

 <span data-ttu-id="b0e44-616">_pbstrErrorChain_</span><span class="sxs-lookup"><span data-stu-id="b0e44-616">_pbstrErrorChain_</span></span>
  
<span data-ttu-id="b0e44-617">要保留错误链信息的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0e44-617">A string to hold the error chain information.</span></span> <span data-ttu-id="b0e44-618">不得为空。</span><span class="sxs-lookup"><span data-stu-id="b0e44-618">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-619">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-619">Return values</span></span>

|<span data-ttu-id="b0e44-620">值</span><span class="sxs-lookup"><span data-stu-id="b0e44-620">Value</span></span>|<span data-ttu-id="b0e44-621">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-621">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-622">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b0e44-622">E_NOTIMPL</span></span>  <br/> |<span data-ttu-id="b0e44-623">安装的 Office 版本不支持此接口</span><span class="sxs-lookup"><span data-stu-id="b0e44-623">The installed version of Office does not support this interface</span></span>  <br/> |
|<span data-ttu-id="b0e44-624">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0e44-624">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0e44-625">一个或多个参数值是无效。</span><span class="sxs-lookup"><span data-stu-id="b0e44-625">One or more of the parameter values are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0e44-626">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0e44-626">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0e44-627">错误链信息不可用。</span><span class="sxs-lookup"><span data-stu-id="b0e44-627">The error chain information is not available.</span></span>  <br/> |
|<span data-ttu-id="b0e44-628">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0e44-628">S_OK</span></span>  <br/> |<span data-ttu-id="b0e44-629">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="b0e44-629">The call was successful.</span></span>  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a><span data-ttu-id="b0e44-630">接口 IPartnerActivityCallback</span><span class="sxs-lookup"><span data-stu-id="b0e44-630">Interface IPartnerActivityCallback</span></span>

<span data-ttu-id="b0e44-631">此接口提供对 CSISyncClient COM 对象的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b0e44-631">This interface provides a callback function to the CSISyncClient COM object.</span></span>
  
<span data-ttu-id="b0e44-632">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0e44-632">**Public member functions**</span></span>

#### <a name="ipartneractivitycallbackeventoccurred"></a><span data-ttu-id="b0e44-633">IPartnerActivityCallback::EventOccurred</span><span class="sxs-lookup"><span data-stu-id="b0e44-633">IPartnerActivityCallback::EventOccurred</span></span>

<span data-ttu-id="b0e44-634">这是分配给 CsiSyncClient COM 对象的对象上的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b0e44-634">This is a callback function on the object given to the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0e44-635">预计事件发生时 （请参阅为有效的事件类型的[枚举 LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) ），CsiSyncClient COM 对象将调用此方法时，信号使用者。</span><span class="sxs-lookup"><span data-stu-id="b0e44-635">It's expected that when an Event occurs (see [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid event types), the CsiSyncClient COM object will call this method, signalling the consumer.</span></span> 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a><span data-ttu-id="b0e44-636">参数</span><span class="sxs-lookup"><span data-stu-id="b0e44-636">Parameters</span></span>

 <span data-ttu-id="b0e44-637">_eEventTypeOccurred_</span><span class="sxs-lookup"><span data-stu-id="b0e44-637">_eEventTypeOccurred_</span></span>
  
<span data-ttu-id="b0e44-638">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-638">The event type of this event.</span></span> <span data-ttu-id="b0e44-639">有效的值，请参阅[枚举 LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 。</span><span class="sxs-lookup"><span data-stu-id="b0e44-639">See [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid values.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0e44-640">返回值</span><span class="sxs-lookup"><span data-stu-id="b0e44-640">Return values</span></span>

<span data-ttu-id="b0e44-641">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0e44-641">Always returns S_OK.</span></span>
  
## <a name="enumerations"></a><span data-ttu-id="b0e44-642">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-642">Enumerations</span></span>

<span data-ttu-id="b0e44-643">CSISyncClient 使用将下列枚举。</span><span class="sxs-lookup"><span data-stu-id="b0e44-643">CSISyncClient uses the following enumerations.</span></span>
  
### <a name="enum-lsceventsyncerrortype"></a><span data-ttu-id="b0e44-644">枚举 LSCEventSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="b0e44-644">Enum LSCEventSyncErrorType</span></span>
<span data-ttu-id="b0e44-645"><a name="Enum_LSCEventSyncErrorType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-645"></span></span>

<span data-ttu-id="b0e44-646">此枚举指定类别的文件同步时可能出现的错误。</span><span class="sxs-lookup"><span data-stu-id="b0e44-646">This enumeration specifies the categories of errors that can occur while synchronizing a file.</span></span>
  
|<span data-ttu-id="b0e44-647">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-647">Enumerator</span></span>|<span data-ttu-id="b0e44-648">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-648">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span><span class="sxs-lookup"><span data-stu-id="b0e44-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span></span>  <br/> |<span data-ttu-id="b0e44-650">此事件的同步错误是意外，并且可能需要特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="b0e44-650">The synchronizing error of this event was unexpected, and may require special consideration.</span></span> <span data-ttu-id="b0e44-651">默认情况下，用户可能需要介入。</span><span class="sxs-lookup"><span data-stu-id="b0e44-651">By default, the user may have to intervene.</span></span>  <br/> |
|<span data-ttu-id="b0e44-652">LSCEventSyncErrorType_NoInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0e44-652">LSCEventSyncErrorType_NoInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0e44-653">此事件的同步错误不需要特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="b0e44-653">The synchronizing error of this event does not need special consideration.</span></span> <span data-ttu-id="b0e44-654">Office 将自动处理。</span><span class="sxs-lookup"><span data-stu-id="b0e44-654">Office will handle it automatically.</span></span>  <br/> |
|<span data-ttu-id="b0e44-655">LSCEventSyncErrorType_UserInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0e44-655">LSCEventSyncErrorType_UserInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0e44-656">此事件的同步错误要求用户解决。</span><span class="sxs-lookup"><span data-stu-id="b0e44-656">The synchronizing error of this event requires a user to resolve it.</span></span> <span data-ttu-id="b0e44-657">例如，合并冲突错误要求用户在打开文档并将其合并。</span><span class="sxs-lookup"><span data-stu-id="b0e44-657">For example, merge conflict error requires a user to open the document and merge it.</span></span>  <br/> |
|<span data-ttu-id="b0e44-658">LSCEventSyncErrorType_WaitingOnClient</span><span class="sxs-lookup"><span data-stu-id="b0e44-658">LSCEventSyncErrorType_WaitingOnClient</span></span>  <br/> |<span data-ttu-id="b0e44-659">此事件的同步错误需要使用者进行干预，但应不需要用户的特殊注意事项。</span><span class="sxs-lookup"><span data-stu-id="b0e44-659">The synchronizing error of this event requires the consumer to intervene, but should not require special consideration by the user.</span></span>  <br/> |
|<span data-ttu-id="b0e44-660">LSCEventSyncErrorType_ClientInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0e44-660">LSCEventSyncErrorType_ClientInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0e44-661">此事件的同步错误需要使用者的特殊情况介入。</span><span class="sxs-lookup"><span data-stu-id="b0e44-661">The synchronizing error of this event requires the consumer to intervene as a special case.</span></span>  <br/> |
|<span data-ttu-id="b0e44-662">LSCEventSyncErrorType_Max</span><span class="sxs-lookup"><span data-stu-id="b0e44-662">LSCEventSyncErrorType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtype"></a><span data-ttu-id="b0e44-663">枚举 LSCEventType</span><span class="sxs-lookup"><span data-stu-id="b0e44-663">Enum LSCEventType</span></span>
<span data-ttu-id="b0e44-664"><a name="Enum_LSCEventType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-664"></span></span>

<span data-ttu-id="b0e44-665">此枚举指定特定文件可能会发生的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-665">This enumeration specifies the type of events that can occur for a particular file.</span></span>
  
|<span data-ttu-id="b0e44-666">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-666">Enumerator</span></span>|<span data-ttu-id="b0e44-667">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-667">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-668">LSCEventType_None</span><span class="sxs-lookup"><span data-stu-id="b0e44-668">LSCEventType_None</span></span>  <br/> ||
|<span data-ttu-id="b0e44-669">LSCEventType_OnLocalChanges</span><span class="sxs-lookup"><span data-stu-id="b0e44-669">LSCEventType_OnLocalChanges</span></span>  <br/> |<span data-ttu-id="b0e44-670">对本地文件进行更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-670">Changes were made to a local file.</span></span>  <br/> |
|<span data-ttu-id="b0e44-671">LSCEventType_OnOpenedByUser</span><span class="sxs-lookup"><span data-stu-id="b0e44-671">LSCEventType_OnOpenedByUser</span></span>  <br/> |<span data-ttu-id="b0e44-672">用户打开文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-672">A user opened a file.</span></span>  <br/> |
|<span data-ttu-id="b0e44-673">LSCEventType_OnServerChangesDownloaded</span><span class="sxs-lookup"><span data-stu-id="b0e44-673">LSCEventType_OnServerChangesDownloaded</span></span>  <br/> |<span data-ttu-id="b0e44-674">完成从服务器下载文件的更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-674">Finished downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="b0e44-675">LSCEventType_OnLocalChangesUploaded</span><span class="sxs-lookup"><span data-stu-id="b0e44-675">LSCEventType_OnLocalChangesUploaded</span></span>  <br/> |<span data-ttu-id="b0e44-676">完成上载到服务器的文件的更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-676">Finished uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="b0e44-677">LSCEventType_OnLocalConflictStateChanged</span><span class="sxs-lookup"><span data-stu-id="b0e44-677">LSCEventType_OnLocalConflictStateChanged</span></span>  <br/> |<span data-ttu-id="b0e44-678">合并冲突状态的文件已更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-678">The merge conflict state of a file has changed.</span></span>  <br/> |
|<span data-ttu-id="b0e44-679">LSCEventType_OnFileAdded</span><span class="sxs-lookup"><span data-stu-id="b0e44-679">LSCEventType_OnFileAdded</span></span>  <br/> |<span data-ttu-id="b0e44-680">添加了一个文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-680">A file was added.</span></span>  <br/> |
|<span data-ttu-id="b0e44-681">LSCEventType_OnFileDeleted</span><span class="sxs-lookup"><span data-stu-id="b0e44-681">LSCEventType_OnFileDeleted</span></span>  <br/> |<span data-ttu-id="b0e44-682">已删除文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-682">A file was deleted.</span></span>  <br/> |
|<span data-ttu-id="b0e44-683">LSCEventType_OnSyncEnabled</span><span class="sxs-lookup"><span data-stu-id="b0e44-683">LSCEventType_OnSyncEnabled</span></span>  <br/> |<span data-ttu-id="b0e44-684">同步已启用的用户的文件。</span><span class="sxs-lookup"><span data-stu-id="b0e44-684">Synchronizing was enabled for a user's files.</span></span>  <br/> |
|<span data-ttu-id="b0e44-685">LSCEventType_OnServerChangesDownloadStarted</span><span class="sxs-lookup"><span data-stu-id="b0e44-685">LSCEventType_OnServerChangesDownloadStarted</span></span>  <br/> |<span data-ttu-id="b0e44-686">启动从服务器下载文件的更改。</span><span class="sxs-lookup"><span data-stu-id="b0e44-686">Started downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="b0e44-687">LSCEventType_OnLocalChangesUploadStarted</span><span class="sxs-lookup"><span data-stu-id="b0e44-687">LSCEventType_OnLocalChangesUploadStarted</span></span>  <br/> |<span data-ttu-id="b0e44-688">启动文件更改上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="b0e44-688">Started uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="b0e44-689">LSCEventType_OnFilePathConflict</span><span class="sxs-lookup"><span data-stu-id="b0e44-689">LSCEventType_OnFilePathConflict</span></span>  <br/> |<span data-ttu-id="b0e44-690">此事件时调用[ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)， [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)，生成或[ILSCLocalSyncClient::RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)与另一个文件导致 Web 路径或本地路径冲突Office 文件缓存。</span><span class="sxs-lookup"><span data-stu-id="b0e44-690">This event is generated when a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) causes a Web Path or Local Path collision with another file in the Office file cache.</span></span>  <br/> |
|<span data-ttu-id="b0e44-691">LSCEventType_OnFileForked</span><span class="sxs-lookup"><span data-stu-id="b0e44-691">LSCEventType_OnFileForked</span></span>  <br/> ||
|<span data-ttu-id="b0e44-692">LSCEventType_Max</span><span class="sxs-lookup"><span data-stu-id="b0e44-692">LSCEventType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a><span data-ttu-id="b0e44-693">枚举 LSCEventTypeOccurred</span><span class="sxs-lookup"><span data-stu-id="b0e44-693">Enum LSCEventTypeOccurred</span></span>
<span data-ttu-id="b0e44-694"><a name="Enum_LSCEventTypeOccurred"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-694"></span></span>

<span data-ttu-id="b0e44-695">此枚举指定可能发生的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0e44-695">This enumeration specifies the type of events that can occur.</span></span> <span data-ttu-id="b0e44-696">使用者需要调用基于事件类型的特定 ILSCLocalSyncClient 函数。</span><span class="sxs-lookup"><span data-stu-id="b0e44-696">The consumer needs to call specific ILSCLocalSyncClient functions based on the event type.</span></span>
  
|<span data-ttu-id="b0e44-697">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-697">Enumerator</span></span>|<span data-ttu-id="b0e44-698">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-698">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-699">LSCEventTypeOccurred_GetChanges</span><span class="sxs-lookup"><span data-stu-id="b0e44-699">LSCEventTypeOccurred_GetChanges</span></span>  <br/> |<span data-ttu-id="b0e44-700">发生 ILSCEvent。</span><span class="sxs-lookup"><span data-stu-id="b0e44-700">An ILSCEvent has occurred.</span></span> <span data-ttu-id="b0e44-701">使用者应调用[ILSCLocalSyncClient::GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)检索数据。</span><span class="sxs-lookup"><span data-stu-id="b0e44-701">The consumer should call [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) to retrieve the data.</span></span>  <br/> |
|<span data-ttu-id="b0e44-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="b0e44-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span></span>  <br/> |<span data-ttu-id="b0e44-703">已更改的受支持的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0e44-703">The supported file extensions have changed.</span></span> <span data-ttu-id="b0e44-704">使用者应调用[ILSCLocalSyncClient::GetSupportedFileExtensions](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)检索新的受支持的扩展名列表。</span><span class="sxs-lookup"><span data-stu-id="b0e44-704">The consumer should call [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions) to retrieve the new list of supported extensions.</span></span>  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a><span data-ttu-id="b0e44-705">枚举 LSCNetworkSyncPermissionType</span><span class="sxs-lookup"><span data-stu-id="b0e44-705">Enum LSCNetworkSyncPermissionType</span></span>
<span data-ttu-id="b0e44-706"><a name="Enum_LSCNetworkSyncPermissionType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-706"></span></span>

<span data-ttu-id="b0e44-707">此枚举指定用于网络成本推断方法的标志。</span><span class="sxs-lookup"><span data-stu-id="b0e44-707">This enumeration specifies the flags used for a network cost heuristic.</span></span> 

|<span data-ttu-id="b0e44-708">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-708">Enumerator</span></span>|<span data-ttu-id="b0e44-709">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-709">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-710">LSCNetworkSyncPermissionType_HighCost</span><span class="sxs-lookup"><span data-stu-id="b0e44-710">LSCNetworkSyncPermissionType_HighCost</span></span>  <br/> |<span data-ttu-id="b0e44-711">如果昂贵网络 （如 3g) 的成本推断方法将被覆盖，则为 true。</span><span class="sxs-lookup"><span data-stu-id="b0e44-711">True if the cost heuristic for expensive networks (such as 3G) is overridden.</span></span>  <br/> |
|<span data-ttu-id="b0e44-712">LSCNetworkSyncPermissionType_HighPowerUsage</span><span class="sxs-lookup"><span data-stu-id="b0e44-712">LSCNetworkSyncPermissionType_HighPowerUsage</span></span>  <br/> |<span data-ttu-id="b0e44-713">如果 （如电池） 的电源使用成本推断方法将被覆盖，则为 true。</span><span class="sxs-lookup"><span data-stu-id="b0e44-713">True if the cost heuristic for power usage (such as a battery) is overridden.</span></span>  <br/> |
   
### <a name="enum-lscstatusflag"></a><span data-ttu-id="b0e44-714">枚举 LSCStatusFlag</span><span class="sxs-lookup"><span data-stu-id="b0e44-714">Enum LSCStatusFlag</span></span>
<span data-ttu-id="b0e44-715"><a name="Enum_LSCStatusFlag"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-715"></span></span>

<span data-ttu-id="b0e44-716">此枚举用于表示文件的同步状态。</span><span class="sxs-lookup"><span data-stu-id="b0e44-716">This enumeration is used to represent the synchronize status of a file.</span></span> 
  
|<span data-ttu-id="b0e44-717">枚举</span><span class="sxs-lookup"><span data-stu-id="b0e44-717">Enumerator</span></span>|<span data-ttu-id="b0e44-718">说明</span><span class="sxs-lookup"><span data-stu-id="b0e44-718">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0e44-719">LCSStatusFlag_None</span><span class="sxs-lookup"><span data-stu-id="b0e44-719">LCSStatusFlag_None</span></span>  <br/> ||
|<span data-ttu-id="b0e44-720">LSCStatusFlag_UploadPending</span><span class="sxs-lookup"><span data-stu-id="b0e44-720">LSCStatusFlag_UploadPending</span></span>  <br/> |<span data-ttu-id="b0e44-721">如果没有挂起的数据发送到服务器文件，则为 true。</span><span class="sxs-lookup"><span data-stu-id="b0e44-721">True if there is pending data to send to the server file.</span></span>  <br/> |
|<span data-ttu-id="b0e44-722">LSCStatusFlag_DownloadPending</span><span class="sxs-lookup"><span data-stu-id="b0e44-722">LSCStatusFlag_DownloadPending</span></span>  <br/> |<span data-ttu-id="b0e44-723">如果没有待处理的要从服务器文件下载的数据，则为 true。</span><span class="sxs-lookup"><span data-stu-id="b0e44-723">True if there is pending data to download from the server file.</span></span>  <br/> |
|<span data-ttu-id="b0e44-724">LSCStatusFlag_LocalFileUnchanged</span><span class="sxs-lookup"><span data-stu-id="b0e44-724">LSCStatusFlag_LocalFileUnchanged</span></span>  <br/> |<span data-ttu-id="b0e44-725">如果数据 Office 具有其缓存中的文件，则磁盘上的数据的最新副本。</span><span class="sxs-lookup"><span data-stu-id="b0e44-725">True if the data Office has on the file in its cache is the most recent copy of the data on disk.</span></span>  <br/> |
   

