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
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a><span data-ttu-id="01242-103">使用 CSISyncClient 控制 ODC Office文档 (缓存) </span><span class="sxs-lookup"><span data-stu-id="01242-103">Using CSISyncClient to control the Office Document Cache (ODC)</span></span>

<span data-ttu-id="01242-104">了解如何使用 CSISyncClient 控制 ODC Office缓存 (缓存) 。</span><span class="sxs-lookup"><span data-stu-id="01242-104">Learn how to use CSISyncClient to control the Office Document Cache (ODC).</span></span>
  
<span data-ttu-id="01242-105">CSISyncClient 是一个非 proc COM (CsiSyncClient.exe) ，它允许 Microsoft OneDrive 控制 Office 文档缓存 (ODC) 的行为。</span><span class="sxs-lookup"><span data-stu-id="01242-105">CSISyncClient is an out-of-proc COM server (CsiSyncClient.exe) that allows Microsoft OneDrive to control the behavior of the Office Document Cache (ODC).</span></span> <span data-ttu-id="01242-106">例如，OneDrive通过 CSISyncClient 调用 ODC，将文件上载和下载至启用了 MS-FSSHTTP 的终结点和从这些终结点下载文件。</span><span class="sxs-lookup"><span data-stu-id="01242-106">For example, OneDrive may call upon the ODC via CSISyncClient to upload and download files to and from MS-FSSHTTP enabled endpoints.</span></span> <span data-ttu-id="01242-107">这样一来，Office支持高级服务的功能，例如共同创作和从脱机到联机的无缝转换。</span><span class="sxs-lookup"><span data-stu-id="01242-107">This enables advanced service-backed features in Office, such as co-authoring and seamless transitions from offline to online.</span></span>
  
<span data-ttu-id="01242-108">CsiSyncClient 适用于 Office 桌面 (x86 和 x64) 。</span><span class="sxs-lookup"><span data-stu-id="01242-108">CsiSyncClient is available in Office Desktop (both x86 and x64).</span></span> <span data-ttu-id="01242-109">注意：虽然更高版本的 Office可能会随 CsiSyncClient 一起提供，但该过程将仅用于向后兼容。</span><span class="sxs-lookup"><span data-stu-id="01242-109">Note: While newer versions of Office may ship with CsiSyncClient, the process will be used for backward compatibility only.</span></span> <span data-ttu-id="01242-110">CsiSyncClient 接口和控制 ODC 的方法将在未来版本的 odC 中Office。</span><span class="sxs-lookup"><span data-stu-id="01242-110">The CsiSyncClient interface and the methodology of controlling the ODC will change in future versions of Office.</span></span>
  
<span data-ttu-id="01242-111">课程 ID 当前设置为仅响应OneDrive。</span><span class="sxs-lookup"><span data-stu-id="01242-111">The class ID is currently set to respond only to OneDrive.</span></span>
  
<span data-ttu-id="01242-112">COM 对象可以用作非 proc COM 服务器，并运行在 CsiSyncClient.exe。</span><span class="sxs-lookup"><span data-stu-id="01242-112">The COM object is usable as an out-of-proc COM server and runs in CsiSyncClient.exe.</span></span> <span data-ttu-id="01242-113">由于 ODC 使用) Office 的 Access (存在限制，因此 x64 Office 表示 x64 COM 对象，x86 Office 表示 x86 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="01242-113">Due to limitations with Access (which the ODC uses), it ships with the bit type that Office comes in, so x64 Office means an x64 COM object, or x86 Office means an x86 COM object.</span></span> <span data-ttu-id="01242-114">要绕开此限制，将 CLSCTX_LOCAL_SERVER指定为 CoCreateInstance 的一部分将 COM 对象作为非 proc COM 服务器托管，从而允许跨位兼容性。</span><span class="sxs-lookup"><span data-stu-id="01242-114">To get around this limitation, specifying CLSCTX_LOCAL_SERVER as part of the CoCreateInstance will have the COM object be hosted as an out-of-proc COM server, allowing cross-bitness compatibility.</span></span>
  
## <a name="interfaces"></a><span data-ttu-id="01242-115">接口</span><span class="sxs-lookup"><span data-stu-id="01242-115">Interfaces</span></span>

<span data-ttu-id="01242-116">CSISyncClient 使用下列接口。</span><span class="sxs-lookup"><span data-stu-id="01242-116">CSISyncClient uses the following interfaces.</span></span>
  
### <a name="interface-ilsclocalsyncclient"></a><span data-ttu-id="01242-117">接口 ILSCLocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="01242-117">Interface ILSCLocalSyncClient</span></span>

<span data-ttu-id="01242-118">这是用于同步文件中文件的主要Office。</span><span class="sxs-lookup"><span data-stu-id="01242-118">This is the primary interface used to synchronize files in Office.</span></span>
  
- <span data-ttu-id="01242-119">ProgID：Office。LocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="01242-119">ProgID: Office.LocalSyncClient</span></span>
- <span data-ttu-id="01242-120">CLSID：{14286318-B6CF-49a1-81FC-D74AD94902F9}</span><span class="sxs-lookup"><span data-stu-id="01242-120">CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}</span></span>
- <span data-ttu-id="01242-121">TypeLib：{66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span><span class="sxs-lookup"><span data-stu-id="01242-121">TypeLib: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span></span>
   
<span data-ttu-id="01242-122">公开的 COM 对象用作非 proc 服务器。</span><span class="sxs-lookup"><span data-stu-id="01242-122">The COM object that is exposed is used as an out-of-proc server.</span></span> <span data-ttu-id="01242-123">将 CLSCTX_LOCAL_SERVER CoCreateInstance 允许 64bit 和 32bit 进程之间的可共存性。</span><span class="sxs-lookup"><span data-stu-id="01242-123">Specifying CLSCTX_LOCAL_SERVER as part of CoCreateInstance allows compatability between 64bit and 32bit processes.</span></span>
  
<span data-ttu-id="01242-124">共同创建 COM 对象后，必须先调用[ILSCLocalSyncClient：：Initialize。](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)</span><span class="sxs-lookup"><span data-stu-id="01242-124">Once you've co-created the COM object, you MUST call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) first.</span></span> <span data-ttu-id="01242-125">[ILSCLocalSyncClient：：Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)成功完成后，你可任意按需要经常调用任何 API。</span><span class="sxs-lookup"><span data-stu-id="01242-125">Once [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has completed successfully, you may call any API as often as you wish and in any order.</span></span> <span data-ttu-id="01242-126">还可以对已初始化的对象调用 [ILSCLocalSyncClient：：Initialize， ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 但此操作不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="01242-126">You may also call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) on an already initialized object, but this does nothing.</span></span> 
  
<span data-ttu-id="01242-127">上一段落的例外情况是 [ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 和 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="01242-127">The exceptions to the previous paragraph are [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) and [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="01242-128">在 COM 对象上调用 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) 后，必须销毁该对象并创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="01242-128">After you call [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) on the COM object, you MUST destroy that object and create a new one.</span></span> <span data-ttu-id="01242-129">[ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 将删除子缓存、删除缓存中所有关联的文件信息，但将文档保留磁盘上。</span><span class="sxs-lookup"><span data-stu-id="01242-129">[ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) will delete your subcache, delete all associated file information in the cache, but leave the documents on disk.</span></span> <span data-ttu-id="01242-130">它还保持与缓存通信的状态不变。</span><span class="sxs-lookup"><span data-stu-id="01242-130">It also leaves the state intact for communicating with the cache.</span></span> <span data-ttu-id="01242-131">这允许你再次调用 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 以创建新缓存，而无需销毁并重新创建 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="01242-131">This allows you to call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) again to create a new cache without having to destroy and recreate the COM object.</span></span> 
  
<span data-ttu-id="01242-132">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="01242-132">**Public member functions**</span></span>

#### <a name="ilsclocalsyncclientdeletefile"></a><span data-ttu-id="01242-133">ILSCLocalSyncClient：:D eleteFile</span><span class="sxs-lookup"><span data-stu-id="01242-133">ILSCLocalSyncClient::DeleteFile</span></span>

<span data-ttu-id="01242-134">DeleteFile 用于从缓存中删除文件信息。</span><span class="sxs-lookup"><span data-stu-id="01242-134">DeleteFile is used to remove the file information from the cache.</span></span> <span data-ttu-id="01242-135">但是，此方法将关联的文件保留磁盘上和服务器上。</span><span class="sxs-lookup"><span data-stu-id="01242-135">However, this method will leave the associated file on disk and on the server.</span></span>
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="01242-136">参数</span><span class="sxs-lookup"><span data-stu-id="01242-136">Parameters</span></span>

 <span data-ttu-id="01242-137">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="01242-137">_bstrResourceID_</span></span>
  
<span data-ttu-id="01242-138">标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-138">The string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="01242-139">此值必须非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-139">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-140">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-140">Return values</span></span>

|<span data-ttu-id="01242-141">值</span><span class="sxs-lookup"><span data-stu-id="01242-141">Value</span></span>|<span data-ttu-id="01242-142">说明</span><span class="sxs-lookup"><span data-stu-id="01242-142">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-143">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-143">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-144">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-144">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-145">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-145">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-146">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-146">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-147">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-147">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-148">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-148">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-149">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="01242-149">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="01242-150">给定的 ResourceID 不在缓存中。</span><span class="sxs-lookup"><span data-stu-id="01242-150">The given ResourceID is not in the cache.</span></span>  <br/> |
|<span data-ttu-id="01242-151">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-151">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-152">过去未成功调用 Initialize。</span><span class="sxs-lookup"><span data-stu-id="01242-152">Initialize has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-153">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-153">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="01242-154">文件当前正在同步或打开，无法删除。</span><span class="sxs-lookup"><span data-stu-id="01242-154">The file is currently synchronizing or open and cannot be deleted.</span></span>  <br/> |
|<span data-ttu-id="01242-155">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-155">S_OK</span></span>  <br/> |<span data-ttu-id="01242-156">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-156">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a><span data-ttu-id="01242-157">ILSCLocalSyncClient：：GetChanges</span><span class="sxs-lookup"><span data-stu-id="01242-157">ILSCLocalSyncClient::GetChanges</span></span>
<span data-ttu-id="01242-158"><a name="ILSCLocalSyncClient_GetChanges"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-158"><a name="ILSCLocalSyncClient_GetChanges"> </a></span></span>

<span data-ttu-id="01242-159">GetChanges 返回 ILSCEvent 对象的枚举器，并返回一个令牌，该令牌将给予对 GetChanges 的下一个调用（假设使用者已处理上一组事件）。</span><span class="sxs-lookup"><span data-stu-id="01242-159">GetChanges returns an enumerator of ILSCEvent objects, and also returns a token that is given to the next call to GetChanges, assuming the consumer has processed the previous set of events.</span></span> <span data-ttu-id="01242-160">指定的  _nPreviousChangesToken_ 之前的事件将被删除且不可用。</span><span class="sxs-lookup"><span data-stu-id="01242-160">Events before the  _nPreviousChangesToken_ specified will be deleted and unavailable.</span></span> <span data-ttu-id="01242-161">如果没有要处理的事件 _，pnCurrentChangesToken_ 的值应该与 _nPreviousChangesToken_ 相同，但仍将设置 _ppiEvents。_</span><span class="sxs-lookup"><span data-stu-id="01242-161">If there are no events to be processed,  _pnCurrentChangesToken_ should be the same value as  _nPreviousChangesToken_, but  _ppiEvents_ will still be set.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a><span data-ttu-id="01242-162">参数</span><span class="sxs-lookup"><span data-stu-id="01242-162">Parameters</span></span>

 <span data-ttu-id="01242-163">_nPreviousChangesToken_</span><span class="sxs-lookup"><span data-stu-id="01242-163">_nPreviousChangesToken_</span></span>
  
<span data-ttu-id="01242-164">标识使用者上次处理的事件。</span><span class="sxs-lookup"><span data-stu-id="01242-164">Identifies which event was last processed by the consumer.</span></span> 
  
 <span data-ttu-id="01242-165">_pnCurrentChangesToken_</span><span class="sxs-lookup"><span data-stu-id="01242-165">_pnCurrentChangesToken_</span></span>
  
<span data-ttu-id="01242-166">标识要交给消费者的最新事件。</span><span class="sxs-lookup"><span data-stu-id="01242-166">Identifies the most recent event being handed to the consumer.</span></span> <span data-ttu-id="01242-167">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-167">Must not be null.</span></span>
  
 <span data-ttu-id="01242-168">_ppiEvents_</span><span class="sxs-lookup"><span data-stu-id="01242-168">_ppiEvents_</span></span>
  
<span data-ttu-id="01242-169">向消费者提供的事件的枚举器。</span><span class="sxs-lookup"><span data-stu-id="01242-169">An enumerator for the events handed to the consumer.</span></span> <span data-ttu-id="01242-170">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-170">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-171">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-171">Return values</span></span>

|<span data-ttu-id="01242-172">值</span><span class="sxs-lookup"><span data-stu-id="01242-172">Value</span></span>|<span data-ttu-id="01242-173">说明</span><span class="sxs-lookup"><span data-stu-id="01242-173">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-174">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-174">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-175">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-175">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-176">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-176">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-177">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-177">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-178">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-178">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-179">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-179">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-180">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-180">S_OK</span></span>  <br/> |<span data-ttu-id="01242-181">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-181">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a><span data-ttu-id="01242-182">ILSCLocalSyncClient：：GetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="01242-182">ILSCLocalSyncClient::GetClientNetworkSyncPermission</span></span>

<span data-ttu-id="01242-183">GetClientNetworkSyncPermission 用于查询Office网络成本和电源使用情况的同步启发是否被覆盖。</span><span class="sxs-lookup"><span data-stu-id="01242-183">GetClientNetworkSyncPermission is used to query whether Office's synchronizing heuristics for network cost and power usage are overridden.</span></span> <span data-ttu-id="01242-184">当使用 3G 或其他高成本网络时，或者当使用电池运行与插入时，Office可能会选择阻止网络流量，直到更适当的时间。</span><span class="sxs-lookup"><span data-stu-id="01242-184">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span>
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a><span data-ttu-id="01242-185">参数</span><span class="sxs-lookup"><span data-stu-id="01242-185">Parameters</span></span>

 <span data-ttu-id="01242-186">_nspType_</span><span class="sxs-lookup"><span data-stu-id="01242-186">_nspType_</span></span>
  
<span data-ttu-id="01242-187">定义要查询的成本启发式标记。</span><span class="sxs-lookup"><span data-stu-id="01242-187">A flag which defines which cost heuristic to query.</span></span> <span data-ttu-id="01242-188">请参阅 [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="01242-188">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span> 
  
 <span data-ttu-id="01242-189">_pfSyncEnabled_</span><span class="sxs-lookup"><span data-stu-id="01242-189">_pfSyncEnabled_</span></span>
  
<span data-ttu-id="01242-190">指定当前是否覆盖请求的成本启发。</span><span class="sxs-lookup"><span data-stu-id="01242-190">Specifies whether the requested cost heuristic is currently overridden or not.</span></span> <span data-ttu-id="01242-191">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-191">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-192">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-192">Return values</span></span>

|<span data-ttu-id="01242-193">值</span><span class="sxs-lookup"><span data-stu-id="01242-193">Value</span></span>|<span data-ttu-id="01242-194">说明</span><span class="sxs-lookup"><span data-stu-id="01242-194">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-195">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-195">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-196">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-196">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-197">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-197">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-198">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-198">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-199">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-199">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-200">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-200">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-201">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-201">S_OK</span></span>  <br/> |<span data-ttu-id="01242-202">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-202">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a><span data-ttu-id="01242-203">ILSCLocalSyncClient：：GetFileStatus</span><span class="sxs-lookup"><span data-stu-id="01242-203">ILSCLocalSyncClient::GetFileStatus</span></span>

<span data-ttu-id="01242-204">GetFileStatus 用于收集特定文件的信息：它是否位于缓存中、它是否具有与服务器副本的挂起通信，以及 Office 2013 具有本地副本中最新数据。</span><span class="sxs-lookup"><span data-stu-id="01242-204">GetFileStatus is used to gather information for a specific file: whether it exists in the cache, if it has pending communication with the server copy, and if Office 2013 has the most up to date data from the local copy.</span></span> <span data-ttu-id="01242-205">它需要 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag) 值的位标志来确定 CsiSyncClient COM 对象要查询的信息。</span><span class="sxs-lookup"><span data-stu-id="01242-205">It requires a bitwise flag of [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag) values to determine what information the CsiSyncClient COM object is to query for.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a><span data-ttu-id="01242-206">参数</span><span class="sxs-lookup"><span data-stu-id="01242-206">Parameters</span></span>

 <span data-ttu-id="01242-207">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="01242-207">_bstrResourceID_</span></span>
  
<span data-ttu-id="01242-208">标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-208">The string which identifies the file on the client.</span></span> <span data-ttu-id="01242-209">此值必须非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-209">This value must be non-empty, with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="01242-210">_sfRequestedStatus_</span><span class="sxs-lookup"><span data-stu-id="01242-210">_sfRequestedStatus_</span></span>
  
<span data-ttu-id="01242-211">定义要返回的信息的标志。</span><span class="sxs-lookup"><span data-stu-id="01242-211">A flag which defines what information to return.</span></span> <span data-ttu-id="01242-212">请参阅 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="01242-212">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
 <span data-ttu-id="01242-213">_pbstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="01242-213">_pbstrFileSystemPath_</span></span>
  
<span data-ttu-id="01242-214">标识由  _bstrResourceID_ 标识的文件在客户端上的位置的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-214">The string which identifies the location of the file identified by  _bstrResourceID_ on the client.</span></span> <span data-ttu-id="01242-215">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-215">Must not be null.</span></span> 
  
 <span data-ttu-id="01242-216">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="01242-216">_pbstrETag_</span></span>
  
<span data-ttu-id="01242-217">一个字符串，其中包含由  _bstrResourceID_ 标识的文件的 eTag。</span><span class="sxs-lookup"><span data-stu-id="01242-217">A string which will contain the eTag for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="01242-218">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-218">Must not be null.</span></span> 
  
 <span data-ttu-id="01242-219">_psfFileStatus_</span><span class="sxs-lookup"><span data-stu-id="01242-219">_psfFileStatus_</span></span>
  
<span data-ttu-id="01242-220">一个标志，其中包含通过  _sfRequestedStatus_ 为  _bstrResourceID_ 标识的文件请求的状态。</span><span class="sxs-lookup"><span data-stu-id="01242-220">A flag which will contain the status requested via  _sfRequestedStatus_ for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="01242-221">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-221">Must not be null.</span></span> <span data-ttu-id="01242-222">请参阅 [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="01242-222">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-223">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-223">Return values</span></span>

|<span data-ttu-id="01242-224">值</span><span class="sxs-lookup"><span data-stu-id="01242-224">Value</span></span>|<span data-ttu-id="01242-225">说明</span><span class="sxs-lookup"><span data-stu-id="01242-225">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-226">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-226">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-227">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-227">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-228">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-228">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-229">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-229">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-230">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="01242-230">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="01242-231">_bstrResourceID_ 指定的文件信息在缓存中不存在。</span><span class="sxs-lookup"><span data-stu-id="01242-231">The file information specified by  _bstrResourceID_ does not exist in the cache.</span></span>  <br/> |
|<span data-ttu-id="01242-232">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01242-232">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="01242-233">LSCStatusFlag_LocalFileUnchanged请求，或者  _bstrResourceID_ 指定的文件已锁定或丢失。</span><span class="sxs-lookup"><span data-stu-id="01242-233">LSCStatusFlag_LocalFileUnchanged was requested or the file specified by  _bstrResourceID_ is locked or missing.</span></span>  <br/> |
|<span data-ttu-id="01242-234">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-234">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-235">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-235">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-236">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-236">S_OK</span></span>  <br/> |<span data-ttu-id="01242-237">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-237">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a><span data-ttu-id="01242-238">ILSCLocalSyncClient：：GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="01242-238">ILSCLocalSyncClient::GetSupportedFileExtensions</span></span>
<span data-ttu-id="01242-239"><a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-239"><a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a></span></span>

<span data-ttu-id="01242-240">GetSupportedFileExtensions 返回由管道分隔的文件扩展名的列表，这些扩展名当前受 CsiSyncClient COM 对象支持。</span><span class="sxs-lookup"><span data-stu-id="01242-240">GetSupportedFileExtensions returns a list of pipe-delimited file extensions which are currently supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="01242-241">请注意，此列表可能会更改，并且将通过 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 上提供的 IPartnerActivityCallback 对象通知使用者 (EventOccured) 。</span><span class="sxs-lookup"><span data-stu-id="01242-241">Note that this list may change, and the consumer will be notified of a change via the IPartnerActivityCallback object provided on [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (See EventOccured).</span></span> 
  
<span data-ttu-id="01242-242">返回的字符串示例如下："|docx|docm|pptx|"</span><span class="sxs-lookup"><span data-stu-id="01242-242">An example of the string returned is as follows: "|docx|docm|pptx|"</span></span>
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a><span data-ttu-id="01242-243">参数</span><span class="sxs-lookup"><span data-stu-id="01242-243">Parameters</span></span>

 <span data-ttu-id="01242-244">_pbstrSupportedFileExtensions_</span><span class="sxs-lookup"><span data-stu-id="01242-244">_pbstrSupportedFileExtensions_</span></span>
  
<span data-ttu-id="01242-245">使用 CsiSyncClient COM 对象支持的一组通过管道分隔的文件扩展名设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-245">A string to be set with a pipe-delimited set of file extensions supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="01242-246">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-246">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-247">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-247">Return values</span></span>

|<span data-ttu-id="01242-248">值</span><span class="sxs-lookup"><span data-stu-id="01242-248">Value</span></span>|<span data-ttu-id="01242-249">说明</span><span class="sxs-lookup"><span data-stu-id="01242-249">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-250">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-250">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-251">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-251">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-252">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-252">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-253">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-253">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-254">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-254">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-255">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-255">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-256">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-256">S_OK</span></span>  <br/> |<span data-ttu-id="01242-257">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-257">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a><span data-ttu-id="01242-258">ILSCLocalSyncClient：：Initialize</span><span class="sxs-lookup"><span data-stu-id="01242-258">ILSCLocalSyncClient::Initialize</span></span>
<span data-ttu-id="01242-259"><a name="ILSCLocalSyncClient_Initialize"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-259"><a name="ILSCLocalSyncClient_Initialize"> </a></span></span>

<span data-ttu-id="01242-260">Initialize 必须是第一个调用的方法。</span><span class="sxs-lookup"><span data-stu-id="01242-260">Initialize must be the first method called.</span></span> <span data-ttu-id="01242-261">否则，所有其他 API 将返回E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="01242-261">Otherwise, all other APIs will return E_LSC_NOTINITIALIZED.</span></span> <span data-ttu-id="01242-262">对已初始化的对象调用 Initialize 将返回 S_OK，并且不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="01242-262">Calling Initialize on an already initialized object returns S_OK and does nothing.</span></span> <span data-ttu-id="01242-263">如果E_LSC_CACHEMISMATCH，则调用方可能调用 [ILSCLocalSyncClient：：ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) 以删除与给定 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-263">If E_LSC_CACHEMISMATCH is returned, the caller may call [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) to delete the cache associated with the given SuppliedID.</span></span> <span data-ttu-id="01242-264">但是，在这种情况下，其他 API 仍将返回E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="01242-264">However, in this case other APIs will still return E_LSC_NOTINITIALIZED.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a><span data-ttu-id="01242-265">参数</span><span class="sxs-lookup"><span data-stu-id="01242-265">Parameters</span></span>

 <span data-ttu-id="01242-266">_bstrSuppliedID_</span><span class="sxs-lookup"><span data-stu-id="01242-266">_bstrSuppliedID_</span></span>
  
<span data-ttu-id="01242-267">标识使用者以及要使用哪个缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-267">Identifies the consumer and which cache to use.</span></span> <span data-ttu-id="01242-268">必须非空，最多 32 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-268">Must be non-empty with a maximum of 32 characters.</span></span> 
  
 <span data-ttu-id="01242-269">_bstrProgID_</span><span class="sxs-lookup"><span data-stu-id="01242-269">_bstrProgID_</span></span>
  
<span data-ttu-id="01242-270">标识用于双向通信的使用者的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="01242-270">Identifies the consumer's COM object for two-way communication.</span></span> <span data-ttu-id="01242-271">必须非空，最多 39 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-271">Must be non-empty with a maximum of 39 characters.</span></span> <span data-ttu-id="01242-272">有关[ \< ProgID \> 的信息，请参阅 ProgID](https://docs.microsoft.com/windows/desktop/com/-progid--key)密钥。</span><span class="sxs-lookup"><span data-stu-id="01242-272">See [\<ProgID\> Key](https://docs.microsoft.com/windows/desktop/com/-progid--key) for more information about ProgIDs.</span></span> 
  
 <span data-ttu-id="01242-273">_bstrFileSystemDirectoryHint_</span><span class="sxs-lookup"><span data-stu-id="01242-273">_bstrFileSystemDirectoryHint_</span></span>
  
<span data-ttu-id="01242-274">标识将存储本地文件的目录根目录。</span><span class="sxs-lookup"><span data-stu-id="01242-274">Identifies the directory root in which local files will be stored.</span></span> <span data-ttu-id="01242-275">不得为空，最多为 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-275">Must be non-empty with a maximum of 256 characters.</span></span> <span data-ttu-id="01242-276">目录必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="01242-276">The directory must already exist.</span></span> 
  
 <span data-ttu-id="01242-277">_pEventCallback_</span><span class="sxs-lookup"><span data-stu-id="01242-277">_pEventCallback_</span></span>
  
<span data-ttu-id="01242-278">CsiSyncClient 将在更改时通知的回调接口。</span><span class="sxs-lookup"><span data-stu-id="01242-278">The callback interface which CsiSyncClient will notify on changes.</span></span> <span data-ttu-id="01242-279">请参阅 IPartnerActivityCallback：：EventOccurred。</span><span class="sxs-lookup"><span data-stu-id="01242-279">See IPartnerActivityCallback::EventOccurred.</span></span> <span data-ttu-id="01242-280">此值不能为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-280">This value must not be null.</span></span> 
  
 <span data-ttu-id="01242-281">_pfCreatedNewCache_</span><span class="sxs-lookup"><span data-stu-id="01242-281">_pfCreatedNewCache_</span></span>
  
<span data-ttu-id="01242-282">返回是否已创建一个新缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-282">Returns whether a new cache was created.</span></span> <span data-ttu-id="01242-283">如果没有与 SuppliedID 关联的缓存，将创建一个缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-283">If no cache is associated with the SuppliedID, one will be created.</span></span> <span data-ttu-id="01242-284">此值不能为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-284">This value must not be null.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-285">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-285">Return values</span></span>

|<span data-ttu-id="01242-286">值</span><span class="sxs-lookup"><span data-stu-id="01242-286">Value</span></span>|<span data-ttu-id="01242-287">说明</span><span class="sxs-lookup"><span data-stu-id="01242-287">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-288">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-288">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-289">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-289">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-290">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-290">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-291">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-291">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-292">E_LSC_CACHEMISMATCH</span><span class="sxs-lookup"><span data-stu-id="01242-292">E_LSC_CACHEMISMATCH</span></span>  <br/> |<span data-ttu-id="01242-293">SuppliedID 已具有与其关联的缓存，但 ProgId 或 FileSystemDirectoryHint 与提供的缓存不同。</span><span class="sxs-lookup"><span data-stu-id="01242-293">A SuppliedID already has a cache associated with it, but has a different ProgId or FileSystemDirectoryHint than the ones provided.</span></span>  <br/> |
|<span data-ttu-id="01242-294">E_LSC_DIRECTORYHINTCONFLICT</span><span class="sxs-lookup"><span data-stu-id="01242-294">E_LSC_DIRECTORYHINTCONFLICT</span></span>  <br/> |<span data-ttu-id="01242-295">FileSystemDirectoryHint (或子文件夹) 缓存中已存在。</span><span class="sxs-lookup"><span data-stu-id="01242-295">The FileSystemDirectoryHint (or a subfolder) already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="01242-296">E_LAC_PROGIDCONFLICT</span><span class="sxs-lookup"><span data-stu-id="01242-296">E_LAC_PROGIDCONFLICT</span></span>  <br/> |<span data-ttu-id="01242-297">ProgID 已存在于其他缓存中。</span><span class="sxs-lookup"><span data-stu-id="01242-297">The ProgID already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="01242-298">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-298">S_OK</span></span>  <br/> |<span data-ttu-id="01242-299">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-299">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a><span data-ttu-id="01242-300">ILSCLocalSyncClient：：LocalFileChange</span><span class="sxs-lookup"><span data-stu-id="01242-300">ILSCLocalSyncClient::LocalFileChange</span></span>
<span data-ttu-id="01242-301"><a name="ILSCLocalSyncClient_LocalFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-301"><a name="ILSCLocalSyncClient_LocalFileChange"> </a></span></span>

<span data-ttu-id="01242-302">LocalFileChange 用于告诉 CsiSyncClient COM 对象尝试上载指定文件。</span><span class="sxs-lookup"><span data-stu-id="01242-302">LocalFileChange is used to tell the CsiSyncClient COM object to attempt to upload the specified file.</span></span> <span data-ttu-id="01242-303">方法将准备文件进行上载，包括读取文件的当前内容。</span><span class="sxs-lookup"><span data-stu-id="01242-303">The method will prepare the file for upload, including reading the file's current contents.</span></span> <span data-ttu-id="01242-304">如果上载已挂起，将放弃之前上载的内容，并准备新内容进行上载。</span><span class="sxs-lookup"><span data-stu-id="01242-304">If an upload is already pending, the previous upload will be discarded and the new contents prepared for upload.</span></span> <span data-ttu-id="01242-305">如果文件在应用程序中打开进行编辑，此方法将返回 S_OK而不准备文件上载 (如果文件发生更改，则应用程序应该已经执行) 。</span><span class="sxs-lookup"><span data-stu-id="01242-305">If the file is open for editing in an application, this method will return S_OK without preparing the file for upload (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="01242-306">如果之前将此方法标记为已阻止上传， ([ILSCLocalSyncClient：：RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)) 。</span><span class="sxs-lookup"><span data-stu-id="01242-306">This method will allow uploads if it was marked as uploads blocked previously (see [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)).</span></span>
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="01242-307">参数</span><span class="sxs-lookup"><span data-stu-id="01242-307">Parameters</span></span>

 <span data-ttu-id="01242-308">_bstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="01242-308">_bstrFileSystemPath_</span></span>
  
<span data-ttu-id="01242-309">标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-309">A string which identifies the file on the client.</span></span> <span data-ttu-id="01242-310">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="01242-310">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="01242-311">当调用 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 时，此路径必须位于 FileSystemDirectoryHint 指定的目录树中。</span><span class="sxs-lookup"><span data-stu-id="01242-311">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was made.</span></span> 
  
 <span data-ttu-id="01242-312">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="01242-312">_bstrResourceID_</span></span>
  
<span data-ttu-id="01242-313">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-313">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="01242-314">此值必须非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-314">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="01242-315">_bstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="01242-315">_bstrWebPath_</span></span>
  
<span data-ttu-id="01242-316">一个标识服务器上文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-316">A string which identifies the file on the server.</span></span> <span data-ttu-id="01242-317">此值必须为非空的有效 URL，但不得超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。</span><span class="sxs-lookup"><span data-stu-id="01242-317">This value must be non-empty, valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-318">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-318">Return values</span></span>

|<span data-ttu-id="01242-319">值</span><span class="sxs-lookup"><span data-stu-id="01242-319">Value</span></span>|<span data-ttu-id="01242-320">说明</span><span class="sxs-lookup"><span data-stu-id="01242-320">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-321">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-321">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-322">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-322">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-323">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-323">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-324">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-324">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-325">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="01242-325">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="01242-326">_bstrFileSystemPath_ 指定的文件与指定的 ResourceID 不同。</span><span class="sxs-lookup"><span data-stu-id="01242-326">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span> <span data-ttu-id="01242-327">返回此错误LSCEventType_OnFilePathConflict发送类型为 LSCEventType_OnFilePathConflict 的事件。</span><span class="sxs-lookup"><span data-stu-id="01242-327">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="01242-328">请参阅 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="01242-328">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="01242-329">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="01242-329">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="01242-330">文件在操作期间被删除。</span><span class="sxs-lookup"><span data-stu-id="01242-330">The file was deleted mid-operation.</span></span>  <br/> |
|<span data-ttu-id="01242-331">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="01242-331">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="01242-332">CsiSyncClient COM 对象不支持给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="01242-332">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="01242-333">请参阅 [ILSCLocalSyncClient：：GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。</span><span class="sxs-lookup"><span data-stu-id="01242-333">See [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions).</span></span>  <br/> |
|<span data-ttu-id="01242-334">E_LSC_FILEUPTODATE</span><span class="sxs-lookup"><span data-stu-id="01242-334">E_LSC_FILEUPTODATE</span></span>  <br/> |<span data-ttu-id="01242-335">COM 对象没有计划上载，因为缓存中的文件具有来自磁盘的最新更改。</span><span class="sxs-lookup"><span data-stu-id="01242-335">The COM object did not schedule an upload because the file in the cache had the most recent changes from the disk.</span></span>  <br/> |
|<span data-ttu-id="01242-336">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01242-336">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="01242-337">_bstrFileSystemPath_ 指定的文件丢失或锁定。</span><span class="sxs-lookup"><span data-stu-id="01242-337">The file specified by  _bstrFileSystemPath_ is missing or locked.</span></span>  <br/> |
|<span data-ttu-id="01242-338">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="01242-338">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="01242-339">调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="01242-339">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="01242-340">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-340">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-341">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-341">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-342">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="01242-342">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="01242-343">_bstrResourceID_ 指定的文件与指定的 FileSystemPath 不同。</span><span class="sxs-lookup"><span data-stu-id="01242-343">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="01242-344">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-344">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="01242-345">指定的文件已在其他缓存中具有挂起的更改，并且无法与使用者的缓存相关联。</span><span class="sxs-lookup"><span data-stu-id="01242-345">The file specified already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="01242-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="01242-347">提供的 WebPath 属于不同的缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-347">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="01242-348">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-348">S_OK</span></span>  <br/> |<span data-ttu-id="01242-349">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-349">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a><span data-ttu-id="01242-350">ILSCLocalSyncClient：：RenameFile</span><span class="sxs-lookup"><span data-stu-id="01242-350">ILSCLocalSyncClient::RenameFile</span></span>
<span data-ttu-id="01242-351"><a name="ILSCLocalSyncClient_RenameFile"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-351"><a name="ILSCLocalSyncClient_RenameFile"> </a></span></span>

<span data-ttu-id="01242-352">RenameFile 将关联给定 ResourceID 的新 URL 和本地路径。</span><span class="sxs-lookup"><span data-stu-id="01242-352">RenameFile will associate a new URL and local path for a given ResourceID.</span></span> <span data-ttu-id="01242-353">如果 ResourceID 指定的文件在缓存中不存在，将尝试创建该文件并标记为下载。</span><span class="sxs-lookup"><span data-stu-id="01242-353">If the file specified by the ResourceID doesn't already exist in the cache, an attempt will be made to create it and mark it for download.</span></span>
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a><span data-ttu-id="01242-354">参数</span><span class="sxs-lookup"><span data-stu-id="01242-354">Parameters</span></span>

 <span data-ttu-id="01242-355">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="01242-355">_bstrResourceID_</span></span>
  
<span data-ttu-id="01242-356">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-356">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="01242-357">此值必须非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-357">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="01242-358">_bstrNewFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="01242-358">_bstrNewFileSystemPath_</span></span>
  
<span data-ttu-id="01242-359">指定文件的新本地路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-359">A string which specifies the new local path for the file.</span></span> <span data-ttu-id="01242-360">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="01242-360">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="01242-361">当调用 Initialize 时，此路径必须在 FileSystemDirectoryHint 指定的目录树中。</span><span class="sxs-lookup"><span data-stu-id="01242-361">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span> 
  
 <span data-ttu-id="01242-362">_bstrNewWebPath_</span><span class="sxs-lookup"><span data-stu-id="01242-362">_bstrNewWebPath_</span></span>
  
<span data-ttu-id="01242-363">指定文件的新 URL 的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-363">A string which specifies the new URL for the file.</span></span> <span data-ttu-id="01242-364">此值必须为非空的有效 URL，但不超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。</span><span class="sxs-lookup"><span data-stu-id="01242-364">This value must be non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span> 
  
 <span data-ttu-id="01242-365">_fBlockUploads_</span><span class="sxs-lookup"><span data-stu-id="01242-365">_fBlockUploads_</span></span>
  
<span data-ttu-id="01242-366">指定当前是否允许上载到新位置。</span><span class="sxs-lookup"><span data-stu-id="01242-366">Specifies whether uploads to the new location are allowed currently.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-367">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-367">Return values</span></span>

|<span data-ttu-id="01242-368">值</span><span class="sxs-lookup"><span data-stu-id="01242-368">Value</span></span>|<span data-ttu-id="01242-369">说明</span><span class="sxs-lookup"><span data-stu-id="01242-369">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-370">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-370">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-371">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-371">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-372">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-372">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-373">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-373">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-374">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="01242-374">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="01242-375">_bstrNewFileSystemPath_ 或 _bstrNewWebPath_ 已存在于任何缓存中的另一个文件上。</span><span class="sxs-lookup"><span data-stu-id="01242-375">The  _bstrNewFileSystemPath_ or  _bstrNewWebPath_ already exist on another file in any cache.</span></span> <span data-ttu-id="01242-376">返回此错误LSCEventType_OnFilePathConflict发送类型为 LSCEventType_OnFilePathConflict 的事件。</span><span class="sxs-lookup"><span data-stu-id="01242-376">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="01242-377">请参阅 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="01242-377">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="01242-378">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="01242-378">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="01242-379">在此方法运行时，文件信息从缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="01242-379">The file information was deleted from the cache while this method was running.</span></span>  <br/> |
|<span data-ttu-id="01242-380">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="01242-380">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="01242-381">调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="01242-381">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="01242-382">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-382">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-383">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-383">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-384">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-384">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="01242-385">指定的文件当前正在Office同步。</span><span class="sxs-lookup"><span data-stu-id="01242-385">The file specified is currently synchronizing in an Office application.</span></span>  <br/> |
|<span data-ttu-id="01242-386">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-386">S_OK</span></span>  <br/> |<span data-ttu-id="01242-387">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-387">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a><span data-ttu-id="01242-388">ILSCLocalSyncClient：：ResetCache</span><span class="sxs-lookup"><span data-stu-id="01242-388">ILSCLocalSyncClient::ResetCache</span></span>
<span data-ttu-id="01242-389"><a name="ILSCLocalSyncClient_ResetCache"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-389"><a name="ILSCLocalSyncClient_ResetCache"> </a></span></span>

<span data-ttu-id="01242-390">ResetCache 将删除与 Initialize 上提供的 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-390">ResetCache will delete the cache associated with the SuppliedID that was provided on Initialize.</span></span> <span data-ttu-id="01242-391">这包括所有文件信息，但文件将同时保留在服务器上和客户端上。</span><span class="sxs-lookup"><span data-stu-id="01242-391">This includes all of the file information, but will leave the files on both the client and the server.</span></span> <span data-ttu-id="01242-392">此方法还会使对象部分未初始化。</span><span class="sxs-lookup"><span data-stu-id="01242-392">This method also leaves the object in a partially uninitialized state.</span></span> <span data-ttu-id="01242-393">在此之后，唯一有效的调用是 [ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 或 [ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="01242-393">The only valid calls after this are [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) or [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="01242-394">如果 Initialize 失败并返回 E_LSC_CACHEMISMATCH，可能会调用此方法，并且将删除与失败调用提供的 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-394">This method MAY be called if Initialize fails and returns E_LSC_CACHEMISMATCH, and will delete the cache associated with the SuppliedID that was provided with the failing call.</span></span>
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a><span data-ttu-id="01242-395">参数</span><span class="sxs-lookup"><span data-stu-id="01242-395">Parameters</span></span>

<span data-ttu-id="01242-396">无</span><span class="sxs-lookup"><span data-stu-id="01242-396">None</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-397">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-397">Return values</span></span>

|<span data-ttu-id="01242-398">值</span><span class="sxs-lookup"><span data-stu-id="01242-398">Value</span></span>|<span data-ttu-id="01242-399">说明</span><span class="sxs-lookup"><span data-stu-id="01242-399">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-400">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-400">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-401">调用失败。</span><span class="sxs-lookup"><span data-stu-id="01242-401">The call failed.</span></span>  <br/> |
|<span data-ttu-id="01242-402">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-402">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-403">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-403">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was not successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-404">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-404">S_OK</span></span>  <br/> |<span data-ttu-id="01242-405">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-405">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a><span data-ttu-id="01242-406">ILSCLocalSyncClient：：ServerFileChange</span><span class="sxs-lookup"><span data-stu-id="01242-406">ILSCLocalSyncClient::ServerFileChange</span></span>
<span data-ttu-id="01242-407"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-407"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span></span>

<span data-ttu-id="01242-408">ServerFileChange 指示 CsiSyncClient COM 对象标记指定的文件进行下载。</span><span class="sxs-lookup"><span data-stu-id="01242-408">ServerFileChange tells the CsiSyncClient COM object to mark the specified file for download.</span></span> <span data-ttu-id="01242-409">如果文件在 Office 应用程序中打开进行编辑，此方法将返回 S_OK而不将文件标记为下载 (如果文件发生更改，则应用程序应该已经执行) 。</span><span class="sxs-lookup"><span data-stu-id="01242-409">If the file is open in an Office application for edit, this method will return S_OK without marking the file for download (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="01242-410">如果之前将其标记为已阻止下载，此方法将允许下载 (RenameFile) 。</span><span class="sxs-lookup"><span data-stu-id="01242-410">This method will allow downloads if it was marked as downloads blocked previously (see RenameFile).</span></span>
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="01242-411">参数</span><span class="sxs-lookup"><span data-stu-id="01242-411">Parameters</span></span>

|<span data-ttu-id="01242-412">参数</span><span class="sxs-lookup"><span data-stu-id="01242-412">Parameter</span></span>|<span data-ttu-id="01242-413">说明</span><span class="sxs-lookup"><span data-stu-id="01242-413">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-414">bstrFileSystemPath</span><span class="sxs-lookup"><span data-stu-id="01242-414">bstrFileSystemPath</span></span>  <br/> |<span data-ttu-id="01242-415">标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-415">A string which identifies the file on the client.</span></span> <span data-ttu-id="01242-416">此值必须是最多包含 256 个字符的非空本地路径。</span><span class="sxs-lookup"><span data-stu-id="01242-416">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="01242-417">当调用 Initialize 时，此路径必须在 FileSystemDirectoryHint 指定的目录树中。</span><span class="sxs-lookup"><span data-stu-id="01242-417">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="01242-418">bstrResourceID</span><span class="sxs-lookup"><span data-stu-id="01242-418">bstrResourceID</span></span>  <br/> |<span data-ttu-id="01242-419">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-419">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="01242-420">此值必须非空，最多为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="01242-420">This value must be non-empty with a maximum of 128 characters.</span></span>  <br/> |
|<span data-ttu-id="01242-421">bstrWebPath</span><span class="sxs-lookup"><span data-stu-id="01242-421">bstrWebPath</span></span>  <br/> |<span data-ttu-id="01242-422">一个标识服务器上文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-422">A string which identifies the file on the server.</span></span> <span data-ttu-id="01242-423">此值必须是非空的有效 URL，但不超过 INTERNET_MAX_URL_LENGTH，如 https://support.microsoft.com/kb/208427 所定义。</span><span class="sxs-lookup"><span data-stu-id="01242-423">This value must be a non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span>  <br/> |
   
##### <a name="return-values"></a><span data-ttu-id="01242-424">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-424">Return values</span></span>

|<span data-ttu-id="01242-425">值</span><span class="sxs-lookup"><span data-stu-id="01242-425">Value</span></span>|<span data-ttu-id="01242-426">说明</span><span class="sxs-lookup"><span data-stu-id="01242-426">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-427">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-427">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-428">设置缓存连接状态失败。</span><span class="sxs-lookup"><span data-stu-id="01242-428">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="01242-429">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="01242-429">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="01242-430">_bstrFileSystemPath_ 指定的文件与指定的 ResourceID 不同。</span><span class="sxs-lookup"><span data-stu-id="01242-430">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span>  <br/> |
|<span data-ttu-id="01242-431">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="01242-431">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="01242-432">CsiSyncClient COM 对象不支持给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="01242-432">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="01242-433">请参阅 GetSupportedFileExtensions。</span><span class="sxs-lookup"><span data-stu-id="01242-433">See GetSupportedFileExtensions.</span></span>  <br/> |
|<span data-ttu-id="01242-434">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="01242-434">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="01242-435">文件在操作期间被删除。</span><span class="sxs-lookup"><span data-stu-id="01242-435">The file was deleted in mid-operation.</span></span>  <br/> |
|<span data-ttu-id="01242-436">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-436">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-437">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-437">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-438">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="01242-438">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="01242-439">调用 Initialize 时，给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="01242-439">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="01242-440">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-440">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-441">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-441">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-442">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="01242-442">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="01242-443">_bstrResourceID_ 指定的文件与指定的 FileSystemPath 不同。</span><span class="sxs-lookup"><span data-stu-id="01242-443">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="01242-444">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-444">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="01242-445">指定的文件已在其他缓存中具有挂起的更改，并且无法与使用者的缓存相关联。</span><span class="sxs-lookup"><span data-stu-id="01242-445">The specified file already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="01242-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="01242-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="01242-447">提供的 WebPath 属于不同的缓存。</span><span class="sxs-lookup"><span data-stu-id="01242-447">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="01242-448">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-448">S_OK</span></span>  <br/> |<span data-ttu-id="01242-449">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-449">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a><span data-ttu-id="01242-450">ILSCLocalSyncClient：：SetClientConnectivityState</span><span class="sxs-lookup"><span data-stu-id="01242-450">ILSCLocalSyncClient::SetClientConnectivityState</span></span>
<span data-ttu-id="01242-451"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-451"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span></span>

<span data-ttu-id="01242-452">将缓存设置为联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="01242-452">Sets the cache into an online or offline state.</span></span> <span data-ttu-id="01242-453">如果脱机Office，系统将不会尝试与该缓存中任何文件的服务器通信，而不管每个文件的 _fBlockUploads_ 设置如何。</span><span class="sxs-lookup"><span data-stu-id="01242-453">If offline, Office will not attempt to communicate with the server for any files in that cache, regardless of each individual file's  _fBlockUploads_ setting.</span></span> 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a><span data-ttu-id="01242-454">参数</span><span class="sxs-lookup"><span data-stu-id="01242-454">Parameters</span></span>

 <span data-ttu-id="01242-455">_fIsOnline_</span><span class="sxs-lookup"><span data-stu-id="01242-455">_fIsOnline_</span></span>
  
<span data-ttu-id="01242-456">确定缓存的连接状态 Boolean。</span><span class="sxs-lookup"><span data-stu-id="01242-456">A boolean determining the connectivity state of the cache.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-457">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-457">Return values</span></span>

|<span data-ttu-id="01242-458">值</span><span class="sxs-lookup"><span data-stu-id="01242-458">Value</span></span>|<span data-ttu-id="01242-459">说明</span><span class="sxs-lookup"><span data-stu-id="01242-459">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-460">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-460">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-461">设置缓存连接状态失败。</span><span class="sxs-lookup"><span data-stu-id="01242-461">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="01242-462">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-462">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-463">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-463">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-464">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-464">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-465">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-465">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-466">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-466">S_OK</span></span>  <br/> |<span data-ttu-id="01242-467">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-467">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a><span data-ttu-id="01242-468">ILSCLocalSyncClient：：SetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="01242-468">ILSCLocalSyncClient::SetClientNetworkSyncPermission</span></span>
<span data-ttu-id="01242-469"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-469"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span></span>

<span data-ttu-id="01242-470">SetClientNetworkSyncPermission 用于覆盖或还原Office 同步网络成本和电源使用情况的启发。</span><span class="sxs-lookup"><span data-stu-id="01242-470">SetClientNetworkSyncPermission is used to either override or restoreOffice's synchronizing heuristics for network cost and power usage.</span></span> <span data-ttu-id="01242-471">当使用 3G 或其他高成本网络时，或者当使用电池运行与插入时，Office可能会选择阻止网络流量，直到更适当的时间。</span><span class="sxs-lookup"><span data-stu-id="01242-471">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span> <span data-ttu-id="01242-472">此 API 的使用者可以使用它替代Office启发式操作并强制同步发生。</span><span class="sxs-lookup"><span data-stu-id="01242-472">The consumer of this API can use it to override Office's heuristics and force synchronizing to occur.</span></span>
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a><span data-ttu-id="01242-473">参数</span><span class="sxs-lookup"><span data-stu-id="01242-473">Parameters</span></span>

 <span data-ttu-id="01242-474">_nspType_</span><span class="sxs-lookup"><span data-stu-id="01242-474">_nspType_</span></span>
  
<span data-ttu-id="01242-475">定义要覆盖的成本启发式标记。</span><span class="sxs-lookup"><span data-stu-id="01242-475">A flag which defines which cost heuristic to override.</span></span> <span data-ttu-id="01242-476">请参阅 [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="01242-476">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span>
  
 <span data-ttu-id="01242-477">_fEnableSync_</span><span class="sxs-lookup"><span data-stu-id="01242-477">_fEnableSync_</span></span>
  
<span data-ttu-id="01242-478">指定是强制同步，从而替代成本启发式，还是不再覆盖它。</span><span class="sxs-lookup"><span data-stu-id="01242-478">Specifies whether to force synchronizing on, thus overriding that cost heuristic, or to no longer override it.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-479">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-479">Return values</span></span>

|<span data-ttu-id="01242-480">值</span><span class="sxs-lookup"><span data-stu-id="01242-480">Value</span></span>|<span data-ttu-id="01242-481">说明</span><span class="sxs-lookup"><span data-stu-id="01242-481">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-482">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-482">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-483">无法覆盖同步启发。</span><span class="sxs-lookup"><span data-stu-id="01242-483">Failure to override synchronizing heuristics.</span></span>  <br/> |
|<span data-ttu-id="01242-484">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-484">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-485">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-485">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-486">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-486">S_OK</span></span>  <br/> |<span data-ttu-id="01242-487">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-487">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a><span data-ttu-id="01242-488">ILSCLocalSyncClient：：Uninitialize</span><span class="sxs-lookup"><span data-stu-id="01242-488">ILSCLocalSyncClient::Uninitialize</span></span>
<span data-ttu-id="01242-489"><a name="ILSCLocalSyncClient_Uninitialize"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-489"><a name="ILSCLocalSyncClient_Uninitialize"> </a></span></span>

<span data-ttu-id="01242-490">从 COM 对象卸载缓存并执行关闭操作。</span><span class="sxs-lookup"><span data-stu-id="01242-490">Unloads the cache from the COM object and perform closing operations.</span></span> <span data-ttu-id="01242-491">[ILSCLocalSyncClient：：Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) 必须在销毁 COM 对象之前调用 。</span><span class="sxs-lookup"><span data-stu-id="01242-491">[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) MUST be called before destroying the COM object.</span></span> <span data-ttu-id="01242-492">调用后，如果想继续操作，则必须销毁 COM 对象并创建一个新 API。</span><span class="sxs-lookup"><span data-stu-id="01242-492">Once called, no other APIs can be called, the COM object MUST be destroyed and a new one created if you wish to continue operations.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a><span data-ttu-id="01242-493">参数</span><span class="sxs-lookup"><span data-stu-id="01242-493">Parameters</span></span>

<span data-ttu-id="01242-494">无。</span><span class="sxs-lookup"><span data-stu-id="01242-494">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-495">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-495">Return values</span></span>

|<span data-ttu-id="01242-496">值</span><span class="sxs-lookup"><span data-stu-id="01242-496">Value</span></span>|<span data-ttu-id="01242-497">说明</span><span class="sxs-lookup"><span data-stu-id="01242-497">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-498">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-498">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-499">无法取消初始化。</span><span class="sxs-lookup"><span data-stu-id="01242-499">Failure to uninitialize.</span></span>  <br/> |
|<span data-ttu-id="01242-500">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="01242-500">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="01242-501">[ILSCLocalSyncClient：：Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) 过去未成功调用。</span><span class="sxs-lookup"><span data-stu-id="01242-501">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="01242-502">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-502">S_OK</span></span>  <br/> |<span data-ttu-id="01242-503">调用成功。</span><span class="sxs-lookup"><span data-stu-id="01242-503">The call succeeded.</span></span>  <br/> |
   
### <a name="interface-ienumlscevent"></a><span data-ttu-id="01242-504">接口 IEnumLSCEvent</span><span class="sxs-lookup"><span data-stu-id="01242-504">Interface IEnumLSCEvent</span></span>

<span data-ttu-id="01242-505">此接口表示 ILSCEvent 事件的列表。</span><span class="sxs-lookup"><span data-stu-id="01242-505">This interface represents a list of ILSCEvent events.</span></span>
  
<span data-ttu-id="01242-506">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="01242-506">**Public member functions**</span></span>

#### <a name="ienumlsceventfnext"></a><span data-ttu-id="01242-507">IEnumLSCEvent：：FNext</span><span class="sxs-lookup"><span data-stu-id="01242-507">IEnumLSCEvent::FNext</span></span>

<span data-ttu-id="01242-508">从事件列表中检索下一个事件。</span><span class="sxs-lookup"><span data-stu-id="01242-508">Retrieves the next event from the list of events.</span></span>
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a><span data-ttu-id="01242-509">参数</span><span class="sxs-lookup"><span data-stu-id="01242-509">Parameters</span></span>

 <span data-ttu-id="01242-510">_ppiLSCEvent_</span><span class="sxs-lookup"><span data-stu-id="01242-510">_ppiLSCEvent_</span></span>
  
<span data-ttu-id="01242-511">指向 ILSCEvent 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="01242-511">A pointer to an ILSCEvent interface.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-512">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-512">Return values</span></span>

|<span data-ttu-id="01242-513">值</span><span class="sxs-lookup"><span data-stu-id="01242-513">Value</span></span>|<span data-ttu-id="01242-514">说明</span><span class="sxs-lookup"><span data-stu-id="01242-514">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-515">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-515">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-516">不再有事件。</span><span class="sxs-lookup"><span data-stu-id="01242-516">There are no more events.</span></span>  <br/> |
|<span data-ttu-id="01242-517">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-517">S_OK</span></span>  <br/> |<span data-ttu-id="01242-518">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="01242-518">The call was successful.</span></span>  <br/> |
   
#### <a name="ienumlsceventreset"></a><span data-ttu-id="01242-519">IEnumLSCEvent：：Reset</span><span class="sxs-lookup"><span data-stu-id="01242-519">IEnumLSCEvent::Reset</span></span>

<span data-ttu-id="01242-520">将枚举器重置为第一个事件。</span><span class="sxs-lookup"><span data-stu-id="01242-520">Resets the enumerator to the first event.</span></span>
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a><span data-ttu-id="01242-521">参数</span><span class="sxs-lookup"><span data-stu-id="01242-521">Parameters</span></span>

<span data-ttu-id="01242-522">无。</span><span class="sxs-lookup"><span data-stu-id="01242-522">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-523">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-523">Return values</span></span>

<span data-ttu-id="01242-524">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-524">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent"></a><span data-ttu-id="01242-525">接口 ILSCEvent</span><span class="sxs-lookup"><span data-stu-id="01242-525">Interface ILSCEvent</span></span>

<span data-ttu-id="01242-526">此接口表示同步事件。</span><span class="sxs-lookup"><span data-stu-id="01242-526">This interface represents a synchronizing event.</span></span> <span data-ttu-id="01242-527">可以从接口检索有关事件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="01242-527">All information about the event can be retrieved from the interface.</span></span>
  
<span data-ttu-id="01242-528">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="01242-528">**Public member functions**</span></span>

#### <a name="ilsceventgetconflictstatus"></a><span data-ttu-id="01242-529">ILSCEvent：：GetConflictStatus</span><span class="sxs-lookup"><span data-stu-id="01242-529">ILSCEvent::GetConflictStatus</span></span>

<span data-ttu-id="01242-530">请注意，此值在 [调用 ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) 时填充，而不是创建事件时填充，因此，您将只具有文件的当前状态，而不是冲突状态更改时文件的状态。</span><span class="sxs-lookup"><span data-stu-id="01242-530">Note that this value is populated when [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) is called, not when the event was created, so you will only have the current status of the file, not the status of the file when the conflict status changed.</span></span> 
  
<span data-ttu-id="01242-531">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnLocalConflictStateChanged。</span><span class="sxs-lookup"><span data-stu-id="01242-531">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnLocalConflictStateChanged.</span></span> 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a><span data-ttu-id="01242-532">参数</span><span class="sxs-lookup"><span data-stu-id="01242-532">Parameters</span></span>

 <span data-ttu-id="01242-533">_pfIsInConflict_</span><span class="sxs-lookup"><span data-stu-id="01242-533">_pfIsInConflict_</span></span>
  
<span data-ttu-id="01242-534">与事件关联的文件的当前冲突状态。</span><span class="sxs-lookup"><span data-stu-id="01242-534">The current conflict status of the file associated with the event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-535">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-535">Return values</span></span>

<span data-ttu-id="01242-536">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-536">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeterror"></a><span data-ttu-id="01242-537">ILSCEvent：：GetError</span><span class="sxs-lookup"><span data-stu-id="01242-537">ILSCEvent::GetError</span></span>

<span data-ttu-id="01242-538">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。</span><span class="sxs-lookup"><span data-stu-id="01242-538">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a><span data-ttu-id="01242-539">参数</span><span class="sxs-lookup"><span data-stu-id="01242-539">Parameters</span></span>

 <span data-ttu-id="01242-540">_pnError_</span><span class="sxs-lookup"><span data-stu-id="01242-540">_pnError_</span></span>
  
<span data-ttu-id="01242-541">与此事件关联的错误。</span><span class="sxs-lookup"><span data-stu-id="01242-541">The error associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-542">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-542">Return values</span></span>

<span data-ttu-id="01242-543">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-543">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetetag"></a><span data-ttu-id="01242-544">ILSCEvent：：GetETag</span><span class="sxs-lookup"><span data-stu-id="01242-544">ILSCEvent::GetETag</span></span>

<span data-ttu-id="01242-545">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。</span><span class="sxs-lookup"><span data-stu-id="01242-545">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a><span data-ttu-id="01242-546">参数</span><span class="sxs-lookup"><span data-stu-id="01242-546">Parameters</span></span>

 <span data-ttu-id="01242-547">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="01242-547">_pbstrETag_</span></span>
  
<span data-ttu-id="01242-548">与此事件关联的 ETag</span><span class="sxs-lookup"><span data-stu-id="01242-548">The ETag associated with this event</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-549">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-549">Return values</span></span>

<span data-ttu-id="01242-550">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-550">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeteventtype"></a><span data-ttu-id="01242-551">ILSCEvent：：GetEventType</span><span class="sxs-lookup"><span data-stu-id="01242-551">ILSCEvent::GetEventType</span></span>

<span data-ttu-id="01242-552">获取此事件的类型。</span><span class="sxs-lookup"><span data-stu-id="01242-552">Gets the type for this event.</span></span>
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a><span data-ttu-id="01242-553">参数</span><span class="sxs-lookup"><span data-stu-id="01242-553">Parameters</span></span>

 <span data-ttu-id="01242-554">_pnEventType_</span><span class="sxs-lookup"><span data-stu-id="01242-554">_pnEventType_</span></span>
  
<span data-ttu-id="01242-555">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="01242-555">The event type of this event.</span></span> <span data-ttu-id="01242-556">有关[有效值，请参阅 Enum LSCEventType。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)</span><span class="sxs-lookup"><span data-stu-id="01242-556">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for valid values.</span></span> <span data-ttu-id="01242-557">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-557">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-558">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-558">Return values</span></span>

|<span data-ttu-id="01242-559">值</span><span class="sxs-lookup"><span data-stu-id="01242-559">Value</span></span>|<span data-ttu-id="01242-560">说明</span><span class="sxs-lookup"><span data-stu-id="01242-560">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-561">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-561">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-562">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-562">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-563">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-563">S_OK</span></span>  <br/> |<span data-ttu-id="01242-564">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="01242-564">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a><span data-ttu-id="01242-565">ILSCEvent：：GetLocalWorkingPath</span><span class="sxs-lookup"><span data-stu-id="01242-565">ILSCEvent::GetLocalWorkingPath</span></span>

<span data-ttu-id="01242-566">获取此事件的本地工作路径。</span><span class="sxs-lookup"><span data-stu-id="01242-566">Gets the local working path for this event.</span></span>
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a><span data-ttu-id="01242-567">参数</span><span class="sxs-lookup"><span data-stu-id="01242-567">Parameters</span></span>

 <span data-ttu-id="01242-568">_pbstrLocalWorkingPath_</span><span class="sxs-lookup"><span data-stu-id="01242-568">_pbstrLocalWorkingPath_</span></span>
  
<span data-ttu-id="01242-569">与此事件相关的文件的本地路径。</span><span class="sxs-lookup"><span data-stu-id="01242-569">The local path of the file to which this event pertains.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-570">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-570">Return values</span></span>

<span data-ttu-id="01242-571">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-571">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceid"></a><span data-ttu-id="01242-572">ILSCEvent：：GetResourceID</span><span class="sxs-lookup"><span data-stu-id="01242-572">ILSCEvent::GetResourceID</span></span>

<span data-ttu-id="01242-573">获取事件的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="01242-573">Gets the resource ID for the event.</span></span>
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="01242-574">参数</span><span class="sxs-lookup"><span data-stu-id="01242-574">Parameters</span></span>

 <span data-ttu-id="01242-575">_pbstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="01242-575">_pbstrResourceID_</span></span>
  
<span data-ttu-id="01242-576">与此事件关联的文件的 ResourceID。</span><span class="sxs-lookup"><span data-stu-id="01242-576">The ResourceID of the file associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="01242-577">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-577">Return values</span></span>

<span data-ttu-id="01242-578">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-578">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceidattempted"></a><span data-ttu-id="01242-579">ILSCEvent：：GetResourceIDAttempted</span><span class="sxs-lookup"><span data-stu-id="01242-579">ILSCEvent::GetResourceIDAttempted</span></span>

<span data-ttu-id="01242-580">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnFilePathConflict。</span><span class="sxs-lookup"><span data-stu-id="01242-580">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> <span data-ttu-id="01242-581">当调用[ILSCLocalSyncClient：：LocalFileChange、ILSCLocalSyncClient：：ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)或[ILSCLocalSyncClient：：RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)将导致 Web 路径或本地路径与 Office 文件缓存中的另一个文件冲突时，将生成此事件。 [ ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)</span><span class="sxs-lookup"><span data-stu-id="01242-581">When a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) would cause a Web Path or Local Path collision with another file in the Office file cache, this event is generated.</span></span> 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a><span data-ttu-id="01242-582">参数</span><span class="sxs-lookup"><span data-stu-id="01242-582">Parameters</span></span>

 <span data-ttu-id="01242-583">_pbstrResourceIDAttempted_</span><span class="sxs-lookup"><span data-stu-id="01242-583">_pbstrResourceIDAttempted_</span></span>
  
<span data-ttu-id="01242-584">导致生成此事件的 ResourceID。</span><span class="sxs-lookup"><span data-stu-id="01242-584">The ResourceID that caused this event to get generated.</span></span> <span data-ttu-id="01242-585">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-585">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-586">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-586">Return values</span></span>

<span data-ttu-id="01242-587">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-587">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetsyncerrortype"></a><span data-ttu-id="01242-588">ILSCEvent：：GetSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="01242-588">ILSCEvent::GetSyncErrorType</span></span>

<span data-ttu-id="01242-589">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded。</span><span class="sxs-lookup"><span data-stu-id="01242-589">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a><span data-ttu-id="01242-590">参数</span><span class="sxs-lookup"><span data-stu-id="01242-590">Parameters</span></span>

 <span data-ttu-id="01242-591">_pnSyncErrorType_</span><span class="sxs-lookup"><span data-stu-id="01242-591">_pnSyncErrorType_</span></span>
  
<span data-ttu-id="01242-592">与此事件关联的错误类型。</span><span class="sxs-lookup"><span data-stu-id="01242-592">The error type associated with this event.</span></span> <span data-ttu-id="01242-593">有关[可能的值，请参阅 Enum LSCEventType。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)</span><span class="sxs-lookup"><span data-stu-id="01242-593">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for potential values.</span></span> <span data-ttu-id="01242-594">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-594">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-595">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-595">Return values</span></span>

|<span data-ttu-id="01242-596">值</span><span class="sxs-lookup"><span data-stu-id="01242-596">Value</span></span>|<span data-ttu-id="01242-597">说明</span><span class="sxs-lookup"><span data-stu-id="01242-597">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-598">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-598">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-599">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="01242-599">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-600">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-600">S_OK</span></span>  <br/> |<span data-ttu-id="01242-601">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="01242-601">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetwebpath"></a><span data-ttu-id="01242-602">ILSCEvent：：GetWebPath</span><span class="sxs-lookup"><span data-stu-id="01242-602">ILSCEvent::GetWebPath</span></span>

<span data-ttu-id="01242-603">此值仅在事件的 [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 为 LSCEventType_OnFilePathConflict。</span><span class="sxs-lookup"><span data-stu-id="01242-603">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a><span data-ttu-id="01242-604">参数</span><span class="sxs-lookup"><span data-stu-id="01242-604">Parameters</span></span>

 <span data-ttu-id="01242-605">_pbstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="01242-605">_pbstrWebPath_</span></span>
  
<span data-ttu-id="01242-606">指定与此事件关联的 Web 路径。</span><span class="sxs-lookup"><span data-stu-id="01242-606">Specifies the Web Path associated with this event.</span></span> <span data-ttu-id="01242-607">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-607">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-608">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-608">Return values</span></span>

<span data-ttu-id="01242-609">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-609">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent2"></a><span data-ttu-id="01242-610">接口 ILSCEvent2</span><span class="sxs-lookup"><span data-stu-id="01242-610">Interface ILSCEvent2</span></span>

<span data-ttu-id="01242-611">此接口包含有关同步事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="01242-611">This interface holds additional information about a synchronizing event.</span></span>
  
<span data-ttu-id="01242-612">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="01242-612">**Public member functions**</span></span>

#### <a name="ilscevent2geterrorchain"></a><span data-ttu-id="01242-613">ILSCEvent2：：GetErrorChain</span><span class="sxs-lookup"><span data-stu-id="01242-613">ILSCEvent2::GetErrorChain</span></span>

<span data-ttu-id="01242-614">获取有关同步事件的错误链信息。</span><span class="sxs-lookup"><span data-stu-id="01242-614">Gets the error chain information about a synchronizing event.</span></span>
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a><span data-ttu-id="01242-615">参数</span><span class="sxs-lookup"><span data-stu-id="01242-615">Parameters</span></span>

 <span data-ttu-id="01242-616">_pbstrErrorChain_</span><span class="sxs-lookup"><span data-stu-id="01242-616">_pbstrErrorChain_</span></span>
  
<span data-ttu-id="01242-617">用于保存错误链信息的字符串。</span><span class="sxs-lookup"><span data-stu-id="01242-617">A string to hold the error chain information.</span></span> <span data-ttu-id="01242-618">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="01242-618">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-619">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-619">Return values</span></span>

|<span data-ttu-id="01242-620">值</span><span class="sxs-lookup"><span data-stu-id="01242-620">Value</span></span>|<span data-ttu-id="01242-621">说明</span><span class="sxs-lookup"><span data-stu-id="01242-621">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-622">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="01242-622">E_NOTIMPL</span></span>  <br/> |<span data-ttu-id="01242-623">已安装版本的 Office不支持此接口</span><span class="sxs-lookup"><span data-stu-id="01242-623">The installed version of Office does not support this interface</span></span>  <br/> |
|<span data-ttu-id="01242-624">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="01242-624">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="01242-625">一个或多个参数值无效。</span><span class="sxs-lookup"><span data-stu-id="01242-625">One or more of the parameter values are invalid.</span></span>  <br/> |
|<span data-ttu-id="01242-626">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01242-626">E_FAIL</span></span>  <br/> |<span data-ttu-id="01242-627">错误链信息不可用。</span><span class="sxs-lookup"><span data-stu-id="01242-627">The error chain information is not available.</span></span>  <br/> |
|<span data-ttu-id="01242-628">S_OK</span><span class="sxs-lookup"><span data-stu-id="01242-628">S_OK</span></span>  <br/> |<span data-ttu-id="01242-629">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="01242-629">The call was successful.</span></span>  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a><span data-ttu-id="01242-630">Interface IPartnerActivityCallback</span><span class="sxs-lookup"><span data-stu-id="01242-630">Interface IPartnerActivityCallback</span></span>

<span data-ttu-id="01242-631">此接口为 CSISyncClient COM 对象提供回调函数。</span><span class="sxs-lookup"><span data-stu-id="01242-631">This interface provides a callback function to the CSISyncClient COM object.</span></span>
  
<span data-ttu-id="01242-632">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="01242-632">**Public member functions**</span></span>

#### <a name="ipartneractivitycallbackeventoccurred"></a><span data-ttu-id="01242-633">IPartnerActivityCallback：：EventOccurred</span><span class="sxs-lookup"><span data-stu-id="01242-633">IPartnerActivityCallback::EventOccurred</span></span>

<span data-ttu-id="01242-634">这是给定给 CsiSyncClient COM 对象的对象上的回调函数。</span><span class="sxs-lookup"><span data-stu-id="01242-634">This is a callback function on the object given to the CsiSyncClient COM object.</span></span> <span data-ttu-id="01242-635">预计当事件发生时， ([Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 了解有效的事件类型) ，CsiSyncClient COM 对象将调用此方法，从而影响使用者。</span><span class="sxs-lookup"><span data-stu-id="01242-635">It's expected that when an Event occurs (see [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid event types), the CsiSyncClient COM object will call this method, signalling the consumer.</span></span> 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a><span data-ttu-id="01242-636">参数</span><span class="sxs-lookup"><span data-stu-id="01242-636">Parameters</span></span>

 <span data-ttu-id="01242-637">_eEventTypeOccurred_</span><span class="sxs-lookup"><span data-stu-id="01242-637">_eEventTypeOccurred_</span></span>
  
<span data-ttu-id="01242-638">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="01242-638">The event type of this event.</span></span> <span data-ttu-id="01242-639">有关[有效值，请参阅 Enum LSCEventTypeOccurred。](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred)</span><span class="sxs-lookup"><span data-stu-id="01242-639">See [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid values.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="01242-640">返回值</span><span class="sxs-lookup"><span data-stu-id="01242-640">Return values</span></span>

<span data-ttu-id="01242-641">始终返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="01242-641">Always returns S_OK.</span></span>
  
## <a name="enumerations"></a><span data-ttu-id="01242-642">枚举</span><span class="sxs-lookup"><span data-stu-id="01242-642">Enumerations</span></span>

<span data-ttu-id="01242-643">CSISyncClient 使用下列枚举。</span><span class="sxs-lookup"><span data-stu-id="01242-643">CSISyncClient uses the following enumerations.</span></span>
  
### <a name="enum-lsceventsyncerrortype"></a><span data-ttu-id="01242-644">枚举 LSCEventSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="01242-644">Enum LSCEventSyncErrorType</span></span>
<span data-ttu-id="01242-645"><a name="Enum_LSCEventSyncErrorType"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-645"><a name="Enum_LSCEventSyncErrorType"> </a></span></span>

<span data-ttu-id="01242-646">此枚举指定同步文件时可能会发生的错误类别。</span><span class="sxs-lookup"><span data-stu-id="01242-646">This enumeration specifies the categories of errors that can occur while synchronizing a file.</span></span>
  
|<span data-ttu-id="01242-647">枚举器</span><span class="sxs-lookup"><span data-stu-id="01242-647">Enumerator</span></span>|<span data-ttu-id="01242-648">说明</span><span class="sxs-lookup"><span data-stu-id="01242-648">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span><span class="sxs-lookup"><span data-stu-id="01242-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span></span>  <br/> |<span data-ttu-id="01242-650">此事件的同步错误是意外的，可能需要特别注意。</span><span class="sxs-lookup"><span data-stu-id="01242-650">The synchronizing error of this event was unexpected, and may require special consideration.</span></span> <span data-ttu-id="01242-651">默认情况下，用户可能必须介入。</span><span class="sxs-lookup"><span data-stu-id="01242-651">By default, the user may have to intervene.</span></span>  <br/> |
|<span data-ttu-id="01242-652">LSCEventSyncErrorType_NoInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="01242-652">LSCEventSyncErrorType_NoInterventionRequired</span></span>  <br/> |<span data-ttu-id="01242-653">此事件的同步错误不需要特别考虑。</span><span class="sxs-lookup"><span data-stu-id="01242-653">The synchronizing error of this event does not need special consideration.</span></span> <span data-ttu-id="01242-654">Office自动处理它。</span><span class="sxs-lookup"><span data-stu-id="01242-654">Office will handle it automatically.</span></span>  <br/> |
|<span data-ttu-id="01242-655">LSCEventSyncErrorType_UserInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="01242-655">LSCEventSyncErrorType_UserInterventionRequired</span></span>  <br/> |<span data-ttu-id="01242-656">此事件的同步错误需要用户进行解析。</span><span class="sxs-lookup"><span data-stu-id="01242-656">The synchronizing error of this event requires a user to resolve it.</span></span> <span data-ttu-id="01242-657">例如，合并冲突错误要求用户打开文档并合并它。</span><span class="sxs-lookup"><span data-stu-id="01242-657">For example, merge conflict error requires a user to open the document and merge it.</span></span>  <br/> |
|<span data-ttu-id="01242-658">LSCEventSyncErrorType_WaitingOnClient</span><span class="sxs-lookup"><span data-stu-id="01242-658">LSCEventSyncErrorType_WaitingOnClient</span></span>  <br/> |<span data-ttu-id="01242-659">此事件的同步错误需要消费者介入，但不需要用户特别考虑。</span><span class="sxs-lookup"><span data-stu-id="01242-659">The synchronizing error of this event requires the consumer to intervene, but should not require special consideration by the user.</span></span>  <br/> |
|<span data-ttu-id="01242-660">LSCEventSyncErrorType_ClientInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="01242-660">LSCEventSyncErrorType_ClientInterventionRequired</span></span>  <br/> |<span data-ttu-id="01242-661">此事件的同步错误要求消费者以特殊情况介入。</span><span class="sxs-lookup"><span data-stu-id="01242-661">The synchronizing error of this event requires the consumer to intervene as a special case.</span></span>  <br/> |
|<span data-ttu-id="01242-662">LSCEventSyncErrorType_Max</span><span class="sxs-lookup"><span data-stu-id="01242-662">LSCEventSyncErrorType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtype"></a><span data-ttu-id="01242-663">枚举 LSCEventType</span><span class="sxs-lookup"><span data-stu-id="01242-663">Enum LSCEventType</span></span>
<span data-ttu-id="01242-664"><a name="Enum_LSCEventType"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-664"><a name="Enum_LSCEventType"> </a></span></span>

<span data-ttu-id="01242-665">此枚举指定特定文件可发生的事件类型。</span><span class="sxs-lookup"><span data-stu-id="01242-665">This enumeration specifies the type of events that can occur for a particular file.</span></span>
  
|<span data-ttu-id="01242-666">枚举器</span><span class="sxs-lookup"><span data-stu-id="01242-666">Enumerator</span></span>|<span data-ttu-id="01242-667">说明</span><span class="sxs-lookup"><span data-stu-id="01242-667">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-668">LSCEventType_None</span><span class="sxs-lookup"><span data-stu-id="01242-668">LSCEventType_None</span></span>  <br/> ||
|<span data-ttu-id="01242-669">LSCEventType_OnLocalChanges</span><span class="sxs-lookup"><span data-stu-id="01242-669">LSCEventType_OnLocalChanges</span></span>  <br/> |<span data-ttu-id="01242-670">对本地文件进行了更改。</span><span class="sxs-lookup"><span data-stu-id="01242-670">Changes were made to a local file.</span></span>  <br/> |
|<span data-ttu-id="01242-671">LSCEventType_OnOpenedByUser</span><span class="sxs-lookup"><span data-stu-id="01242-671">LSCEventType_OnOpenedByUser</span></span>  <br/> |<span data-ttu-id="01242-672">用户打开文件。</span><span class="sxs-lookup"><span data-stu-id="01242-672">A user opened a file.</span></span>  <br/> |
|<span data-ttu-id="01242-673">LSCEventType_OnServerChangesDownloaded</span><span class="sxs-lookup"><span data-stu-id="01242-673">LSCEventType_OnServerChangesDownloaded</span></span>  <br/> |<span data-ttu-id="01242-674">从服务器下载完文件更改。</span><span class="sxs-lookup"><span data-stu-id="01242-674">Finished downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="01242-675">LSCEventType_OnLocalChangesUploaded</span><span class="sxs-lookup"><span data-stu-id="01242-675">LSCEventType_OnLocalChangesUploaded</span></span>  <br/> |<span data-ttu-id="01242-676">已完成将文件更改上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="01242-676">Finished uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="01242-677">LSCEventType_OnLocalConflictStateChanged</span><span class="sxs-lookup"><span data-stu-id="01242-677">LSCEventType_OnLocalConflictStateChanged</span></span>  <br/> |<span data-ttu-id="01242-678">文件的合并冲突状态已更改。</span><span class="sxs-lookup"><span data-stu-id="01242-678">The merge conflict state of a file has changed.</span></span>  <br/> |
|<span data-ttu-id="01242-679">LSCEventType_OnFileAdded</span><span class="sxs-lookup"><span data-stu-id="01242-679">LSCEventType_OnFileAdded</span></span>  <br/> |<span data-ttu-id="01242-680">已添加文件。</span><span class="sxs-lookup"><span data-stu-id="01242-680">A file was added.</span></span>  <br/> |
|<span data-ttu-id="01242-681">LSCEventType_OnFileDeleted</span><span class="sxs-lookup"><span data-stu-id="01242-681">LSCEventType_OnFileDeleted</span></span>  <br/> |<span data-ttu-id="01242-682">已删除文件。</span><span class="sxs-lookup"><span data-stu-id="01242-682">A file was deleted.</span></span>  <br/> |
|<span data-ttu-id="01242-683">LSCEventType_OnSyncEnabled</span><span class="sxs-lookup"><span data-stu-id="01242-683">LSCEventType_OnSyncEnabled</span></span>  <br/> |<span data-ttu-id="01242-684">为用户文件启用了同步。</span><span class="sxs-lookup"><span data-stu-id="01242-684">Synchronizing was enabled for a user's files.</span></span>  <br/> |
|<span data-ttu-id="01242-685">LSCEventType_OnServerChangesDownloadStarted</span><span class="sxs-lookup"><span data-stu-id="01242-685">LSCEventType_OnServerChangesDownloadStarted</span></span>  <br/> |<span data-ttu-id="01242-686">开始从服务器下载文件更改。</span><span class="sxs-lookup"><span data-stu-id="01242-686">Started downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="01242-687">LSCEventType_OnLocalChangesUploadStarted</span><span class="sxs-lookup"><span data-stu-id="01242-687">LSCEventType_OnLocalChangesUploadStarted</span></span>  <br/> |<span data-ttu-id="01242-688">开始将文件更改上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="01242-688">Started uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="01242-689">LSCEventType_OnFilePathConflict</span><span class="sxs-lookup"><span data-stu-id="01242-689">LSCEventType_OnFilePathConflict</span></span>  <br/> |<span data-ttu-id="01242-690">当对[ILSCLocalSyncClient：：LocalFileChange、ILSCLocalSyncClient：：ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)或[ILSCLocalSyncClient：：RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)的调用导致 Web 路径或本地路径与 Office 文件缓存中的另一个文件冲突时，将生成此事件。 [ ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)</span><span class="sxs-lookup"><span data-stu-id="01242-690">This event is generated when a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) causes a Web Path or Local Path collision with another file in the Office file cache.</span></span>  <br/> |
|<span data-ttu-id="01242-691">LSCEventType_OnFileForked</span><span class="sxs-lookup"><span data-stu-id="01242-691">LSCEventType_OnFileForked</span></span>  <br/> ||
|<span data-ttu-id="01242-692">LSCEventType_Max</span><span class="sxs-lookup"><span data-stu-id="01242-692">LSCEventType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a><span data-ttu-id="01242-693">枚举 LSCEventTypeOccurred</span><span class="sxs-lookup"><span data-stu-id="01242-693">Enum LSCEventTypeOccurred</span></span>
<span data-ttu-id="01242-694"><a name="Enum_LSCEventTypeOccurred"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-694"><a name="Enum_LSCEventTypeOccurred"> </a></span></span>

<span data-ttu-id="01242-695">此枚举指定可发生事件的类型。</span><span class="sxs-lookup"><span data-stu-id="01242-695">This enumeration specifies the type of events that can occur.</span></span> <span data-ttu-id="01242-696">使用者需要基于事件类型调用特定的 ILSCLocalSyncClient 函数。</span><span class="sxs-lookup"><span data-stu-id="01242-696">The consumer needs to call specific ILSCLocalSyncClient functions based on the event type.</span></span>
  
|<span data-ttu-id="01242-697">枚举器</span><span class="sxs-lookup"><span data-stu-id="01242-697">Enumerator</span></span>|<span data-ttu-id="01242-698">说明</span><span class="sxs-lookup"><span data-stu-id="01242-698">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-699">LSCEventTypeOccurred_GetChanges</span><span class="sxs-lookup"><span data-stu-id="01242-699">LSCEventTypeOccurred_GetChanges</span></span>  <br/> |<span data-ttu-id="01242-700">发生 ILSCEvent。</span><span class="sxs-lookup"><span data-stu-id="01242-700">An ILSCEvent has occurred.</span></span> <span data-ttu-id="01242-701">使用者应调用 [ILSCLocalSyncClient：：GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) 以检索数据。</span><span class="sxs-lookup"><span data-stu-id="01242-701">The consumer should call [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) to retrieve the data.</span></span>  <br/> |
|<span data-ttu-id="01242-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="01242-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span></span>  <br/> |<span data-ttu-id="01242-703">受支持的文件扩展名已更改。</span><span class="sxs-lookup"><span data-stu-id="01242-703">The supported file extensions have changed.</span></span> <span data-ttu-id="01242-704">使用者应调用 [ILSCLocalSyncClient：：GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions) 来检索受支持的扩展的新列表。</span><span class="sxs-lookup"><span data-stu-id="01242-704">The consumer should call [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions) to retrieve the new list of supported extensions.</span></span>  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a><span data-ttu-id="01242-705">枚举 LSCNetworkSyncPermissionType</span><span class="sxs-lookup"><span data-stu-id="01242-705">Enum LSCNetworkSyncPermissionType</span></span>
<span data-ttu-id="01242-706"><a name="Enum_LSCNetworkSyncPermissionType"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-706"><a name="Enum_LSCNetworkSyncPermissionType"> </a></span></span>

<span data-ttu-id="01242-707">此枚举指定用于网络成本启发的标志。</span><span class="sxs-lookup"><span data-stu-id="01242-707">This enumeration specifies the flags used for a network cost heuristic.</span></span> 

|<span data-ttu-id="01242-708">枚举器</span><span class="sxs-lookup"><span data-stu-id="01242-708">Enumerator</span></span>|<span data-ttu-id="01242-709">说明</span><span class="sxs-lookup"><span data-stu-id="01242-709">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-710">LSCNetworkSyncPermissionType_HighCost</span><span class="sxs-lookup"><span data-stu-id="01242-710">LSCNetworkSyncPermissionType_HighCost</span></span>  <br/> |<span data-ttu-id="01242-711">如果覆盖高成本网络（如 3G (）的成本启发) True。</span><span class="sxs-lookup"><span data-stu-id="01242-711">True if the cost heuristic for expensive networks (such as 3G) is overridden.</span></span>  <br/> |
|<span data-ttu-id="01242-712">LSCNetworkSyncPermissionType_HighPowerUsage</span><span class="sxs-lookup"><span data-stu-id="01242-712">LSCNetworkSyncPermissionType_HighPowerUsage</span></span>  <br/> |<span data-ttu-id="01242-713">如此 如果电源使用成本启发式 (例如电池) 覆盖。</span><span class="sxs-lookup"><span data-stu-id="01242-713">True if the cost heuristic for power usage (such as a battery) is overridden.</span></span>  <br/> |
   
### <a name="enum-lscstatusflag"></a><span data-ttu-id="01242-714">枚举 LSCStatusFlag</span><span class="sxs-lookup"><span data-stu-id="01242-714">Enum LSCStatusFlag</span></span>
<span data-ttu-id="01242-715"><a name="Enum_LSCStatusFlag"> </a></span><span class="sxs-lookup"><span data-stu-id="01242-715"><a name="Enum_LSCStatusFlag"> </a></span></span>

<span data-ttu-id="01242-716">此枚举用于表示文件的同步状态。</span><span class="sxs-lookup"><span data-stu-id="01242-716">This enumeration is used to represent the synchronize status of a file.</span></span> 
  
|<span data-ttu-id="01242-717">枚举器</span><span class="sxs-lookup"><span data-stu-id="01242-717">Enumerator</span></span>|<span data-ttu-id="01242-718">说明</span><span class="sxs-lookup"><span data-stu-id="01242-718">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="01242-719">LCSStatusFlag_None</span><span class="sxs-lookup"><span data-stu-id="01242-719">LCSStatusFlag_None</span></span>  <br/> ||
|<span data-ttu-id="01242-720">LSCStatusFlag_UploadPending</span><span class="sxs-lookup"><span data-stu-id="01242-720">LSCStatusFlag_UploadPending</span></span>  <br/> |<span data-ttu-id="01242-721">如此 如果有待发送到服务器文件的数据。</span><span class="sxs-lookup"><span data-stu-id="01242-721">True if there is pending data to send to the server file.</span></span>  <br/> |
|<span data-ttu-id="01242-722">LSCStatusFlag_DownloadPending</span><span class="sxs-lookup"><span data-stu-id="01242-722">LSCStatusFlag_DownloadPending</span></span>  <br/> |<span data-ttu-id="01242-723">如果服务器文件中存在要下载的待定数据，则其为 True。</span><span class="sxs-lookup"><span data-stu-id="01242-723">True if there is pending data to download from the server file.</span></span>  <br/> |
|<span data-ttu-id="01242-724">LSCStatusFlag_LocalFileUnchanged</span><span class="sxs-lookup"><span data-stu-id="01242-724">LSCStatusFlag_LocalFileUnchanged</span></span>  <br/> |<span data-ttu-id="01242-725">如此 如果Office文件在其缓存中具有的数据是磁盘上的最新数据副本。</span><span class="sxs-lookup"><span data-stu-id="01242-725">True if the data Office has on the file in its cache is the most recent copy of the data on disk.</span></span>  <br/> |
   

