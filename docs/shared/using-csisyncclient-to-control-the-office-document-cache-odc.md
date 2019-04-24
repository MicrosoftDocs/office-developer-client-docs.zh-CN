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
# <a name="using-csisyncclient-to-control-the-office-document-cache-odc"></a><span data-ttu-id="b0332-103">使用 CSISyncClient 控制 Office 文档缓存 (ODC)</span><span class="sxs-lookup"><span data-stu-id="b0332-103">Using CSISyncClient to control the Office Document Cache (ODC)</span></span>

<span data-ttu-id="b0332-104">了解如何使用 CSISyncClient 控制 Office 文档缓存 (ODC)。</span><span class="sxs-lookup"><span data-stu-id="b0332-104">Learn how to use CSISyncClient to control the Office Document Cache (ODC).</span></span>
  
<span data-ttu-id="b0332-105">CSISyncClient 是一个进程外 COM 服务器 (CSISyncClient), 它允许 Microsoft OneDrive 控制 Office 文档缓存 (ODC) 的行为。</span><span class="sxs-lookup"><span data-stu-id="b0332-105">CSISyncClient is an out-of-proc COM server (CsiSyncClient.exe) that allows Microsoft OneDrive to control the behavior of the Office Document Cache (ODC).</span></span> <span data-ttu-id="b0332-106">例如, OneDrive 可能会通过 CSISyncClient 在 ODC 上进行调用, 以在 MS ms-fsshttp 启用的终结点上传和下载文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-106">For example, OneDrive may call upon the ODC via CSISyncClient to upload and download files to and from MS-FSSHTTP enabled endpoints.</span></span> <span data-ttu-id="b0332-107">这将启用 Office 中的高级服务支持功能, 如共同创作和从脱机到联机的无缝转换。</span><span class="sxs-lookup"><span data-stu-id="b0332-107">This enables advanced service-backed features in Office, such as co-authoring and seamless transitions from offline to online.</span></span>
  
<span data-ttu-id="b0332-108">CsiSyncClient 在 Office Desktop (x86 和 x64) 中可用。</span><span class="sxs-lookup"><span data-stu-id="b0332-108">CsiSyncClient is available in Office Desktop (both x86 and x64).</span></span> <span data-ttu-id="b0332-109">注意: 虽然较新版本的 Office 可能附带 CsiSyncClient, 但此过程仅用于向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0332-109">Note: While newer versions of Office may ship with CsiSyncClient, the process will be used for backward compatibility only.</span></span> <span data-ttu-id="b0332-110">用于控制 ODC 的 CsiSyncClient 接口和方法在将来的 Office 版本中会发生变化。</span><span class="sxs-lookup"><span data-stu-id="b0332-110">The CsiSyncClient interface and the methodology of controlling the ODC will change in future versions of Office.</span></span>
  
<span data-ttu-id="b0332-111">类 ID 当前设置为仅响应 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="b0332-111">The class ID is currently set to respond only to OneDrive.</span></span>
  
<span data-ttu-id="b0332-112">com 对象可用作进程外 com 服务器, 并在 CsiSyncClient 中运行。</span><span class="sxs-lookup"><span data-stu-id="b0332-112">The COM object is usable as an out-of-proc COM server and runs in CsiSyncClient.exe.</span></span> <span data-ttu-id="b0332-113">由于 Access (ODC 使用) 的限制, 它附带了 Office 所带的位类型, 因此 x64 office 表示 x64 com 对象, 或 x86 office 表示 x86 com 对象。</span><span class="sxs-lookup"><span data-stu-id="b0332-113">Due to limitations with Access (which the ODC uses), it ships with the bit type that Office comes in, so x64 Office means an x64 COM object, or x86 Office means an x86 COM object.</span></span> <span data-ttu-id="b0332-114">若要避免此限制, 将 CLSCTX_LOCAL_SERVER 指定为 CoCreateInstance 的一部分会将 com 对象作为进程外 com 服务器托管, 从而允许跨位数兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0332-114">To get around this limitation, specifying CLSCTX_LOCAL_SERVER as part of the CoCreateInstance will have the COM object be hosted as an out-of-proc COM server, allowing cross-bitness compatibility.</span></span>
  
## <a name="interfaces"></a><span data-ttu-id="b0332-115">接口</span><span class="sxs-lookup"><span data-stu-id="b0332-115">Interfaces</span></span>

<span data-ttu-id="b0332-116">CSISyncClient 使用下列接口。</span><span class="sxs-lookup"><span data-stu-id="b0332-116">CSISyncClient uses the following interfaces.</span></span>
  
### <a name="interface-ilsclocalsyncclient"></a><span data-ttu-id="b0332-117">接口 ILSCLocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="b0332-117">Interface ILSCLocalSyncClient</span></span>

<span data-ttu-id="b0332-118">这是用于同步 Office 中的文件的主要界面。</span><span class="sxs-lookup"><span data-stu-id="b0332-118">This is the primary interface used to synchronize files in Office.</span></span>
  
- <span data-ttu-id="b0332-119">ProgID: LocalSyncClient</span><span class="sxs-lookup"><span data-stu-id="b0332-119">ProgID: Office.LocalSyncClient</span></span>
- <span data-ttu-id="b0332-120">CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}</span><span class="sxs-lookup"><span data-stu-id="b0332-120">CLSID: {14286318-B6CF-49a1-81FC-D74AD94902F9}</span></span>
- <span data-ttu-id="b0332-121">TypeLib: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span><span class="sxs-lookup"><span data-stu-id="b0332-121">TypeLib: {66CDD37F-D313-4e81-8C31-4198F3E42C3C}</span></span>
   
<span data-ttu-id="b0332-122">公开的 COM 对象用作进程外服务器。</span><span class="sxs-lookup"><span data-stu-id="b0332-122">The COM object that is exposed is used as an out-of-proc server.</span></span> <span data-ttu-id="b0332-123">将 CLSCTX_LOCAL_SERVER 指定为 CoCreateInstance 的一部分可以实现64位和32位进程之间的兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0332-123">Specifying CLSCTX_LOCAL_SERVER as part of CoCreateInstance allows compatability between 64bit and 32bit processes.</span></span>
  
<span data-ttu-id="b0332-124">共同创建 COM 对象后, 必须先调用[ILSCLocalSyncClient:: first 初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)。</span><span class="sxs-lookup"><span data-stu-id="b0332-124">Once you've co-created the COM object, you MUST call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) first.</span></span> <span data-ttu-id="b0332-125">一旦[ILSCLocalSyncClient:: 初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)成功完成, 您可以根据需要按任意顺序调用任何 API。</span><span class="sxs-lookup"><span data-stu-id="b0332-125">Once [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has completed successfully, you may call any API as often as you wish and in any order.</span></span> <span data-ttu-id="b0332-126">您还可以对已经初始化的对象调用[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) , 但这不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="b0332-126">You may also call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) on an already initialized object, but this does nothing.</span></span> 
  
<span data-ttu-id="b0332-127">前一段的例外情况是[ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)和[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="b0332-127">The exceptions to the previous paragraph are [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) and [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="b0332-128">在对 COM 对象调用[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)后, 必须销毁该对象并创建一个新对象。</span><span class="sxs-lookup"><span data-stu-id="b0332-128">After you call [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) on the COM object, you MUST destroy that object and create a new one.</span></span> <span data-ttu-id="b0332-129">[ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)将删除您的 subcache, 删除缓存中的所有关联文件信息, 但将这些文档保留在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="b0332-129">[ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) will delete your subcache, delete all associated file information in the cache, but leave the documents on disk.</span></span> <span data-ttu-id="b0332-130">它还保持与缓存进行通信的状态不变。</span><span class="sxs-lookup"><span data-stu-id="b0332-130">It also leaves the state intact for communicating with the cache.</span></span> <span data-ttu-id="b0332-131">这使您可以调用[ILSCLocalSyncClient:: 重新初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)以创建新的缓存, 而无需销毁并重新创建 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b0332-131">This allows you to call [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) again to create a new cache without having to destroy and recreate the COM object.</span></span> 
  
<span data-ttu-id="b0332-132">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0332-132">**Public member functions**</span></span>

#### <a name="ilsclocalsyncclientdeletefile"></a><span data-ttu-id="b0332-133">ILSCLocalSyncClient::D eletefile</span><span class="sxs-lookup"><span data-stu-id="b0332-133">ILSCLocalSyncClient::DeleteFile</span></span>

<span data-ttu-id="b0332-134">DeleteFile 用于从缓存中删除文件信息。</span><span class="sxs-lookup"><span data-stu-id="b0332-134">DeleteFile is used to remove the file information from the cache.</span></span> <span data-ttu-id="b0332-135">但是, 此方法将把关联的文件保留在磁盘上和服务器上。</span><span class="sxs-lookup"><span data-stu-id="b0332-135">However, this method will leave the associated file on disk and on the server.</span></span>
  
`HRESULT ILSCLocalSyncClient::DeleteFile ([in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0332-136">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-136">Parameters</span></span>

 <span data-ttu-id="b0332-137">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0332-137">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0332-138">标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-138">The string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0332-139">此值必须为非空, 最多为128个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-139">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-140">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-140">Return values</span></span>

|<span data-ttu-id="b0332-141">值</span><span class="sxs-lookup"><span data-stu-id="b0332-141">Value</span></span>|<span data-ttu-id="b0332-142">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-142">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-143">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-143">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-144">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-144">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-145">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-145">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-146">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-146">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-147">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-147">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-148">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-148">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-149">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0332-149">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0332-150">给定的 ResourceID 不在缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0332-150">The given ResourceID is not in the cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-151">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-151">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-152">过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-152">Initialize has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-153">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-153">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0332-154">文件当前正在同步或已打开, 无法删除。</span><span class="sxs-lookup"><span data-stu-id="b0332-154">The file is currently synchronizing or open and cannot be deleted.</span></span>  <br/> |
|<span data-ttu-id="b0332-155">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-155">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-156">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-156">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetchanges"></a><span data-ttu-id="b0332-157">ILSCLocalSyncClient:: GetChanges</span><span class="sxs-lookup"><span data-stu-id="b0332-157">ILSCLocalSyncClient::GetChanges</span></span>
<span data-ttu-id="b0332-158"><a name="ILSCLocalSyncClient_GetChanges"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-158"></span></span>

<span data-ttu-id="b0332-159">GetChanges 返回 ILSCEvent 对象的枚举器, 并且还返回一个令牌, 该令牌将提供给下一个对 GetChanges 的调用, 假定使用者已处理了以前的一组事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-159">GetChanges returns an enumerator of ILSCEvent objects, and also returns a token that is given to the next call to GetChanges, assuming the consumer has processed the previous set of events.</span></span> <span data-ttu-id="b0332-160">在指定的_nPreviousChangesToken_之前的事件将被删除且不可用。</span><span class="sxs-lookup"><span data-stu-id="b0332-160">Events before the  _nPreviousChangesToken_ specified will be deleted and unavailable.</span></span> <span data-ttu-id="b0332-161">如果没有要处理的事件, 则_pnCurrentChangesToken_应与_nPreviousChangesToken_的值相同, 但仍将设置_ppiEvents_ 。</span><span class="sxs-lookup"><span data-stu-id="b0332-161">If there are no events to be processed,  _pnCurrentChangesToken_ should be the same value as  _nPreviousChangesToken_, but  _ppiEvents_ will still be set.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetChanges ([in] LONG nPreviousChangesToken, [out] LONG * pnCurrentChangesToken, [out] IEnumLSCEvent ** ppiEvents)`

##### <a name="parameters"></a><span data-ttu-id="b0332-162">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-162">Parameters</span></span>

 <span data-ttu-id="b0332-163">_nPreviousChangesToken_</span><span class="sxs-lookup"><span data-stu-id="b0332-163">_nPreviousChangesToken_</span></span>
  
<span data-ttu-id="b0332-164">标识使用者上次处理的事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-164">Identifies which event was last processed by the consumer.</span></span> 
  
 <span data-ttu-id="b0332-165">_pnCurrentChangesToken_</span><span class="sxs-lookup"><span data-stu-id="b0332-165">_pnCurrentChangesToken_</span></span>
  
<span data-ttu-id="b0332-166">标识正在传递给使用者的最新事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-166">Identifies the most recent event being handed to the consumer.</span></span> <span data-ttu-id="b0332-167">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-167">Must not be null.</span></span>
  
 <span data-ttu-id="b0332-168">_ppiEvents_</span><span class="sxs-lookup"><span data-stu-id="b0332-168">_ppiEvents_</span></span>
  
<span data-ttu-id="b0332-169">传递给使用者的事件的枚举器。</span><span class="sxs-lookup"><span data-stu-id="b0332-169">An enumerator for the events handed to the consumer.</span></span> <span data-ttu-id="b0332-170">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-170">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-171">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-171">Return values</span></span>

|<span data-ttu-id="b0332-172">值</span><span class="sxs-lookup"><span data-stu-id="b0332-172">Value</span></span>|<span data-ttu-id="b0332-173">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-173">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-174">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-174">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-175">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-175">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-176">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-176">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-177">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-177">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-178">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-178">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-179">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-179">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-180">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-180">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-181">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-181">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetclientnetworksyncpermission"></a><span data-ttu-id="b0332-182">ILSCLocalSyncClient:: GetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="b0332-182">ILSCLocalSyncClient::GetClientNetworkSyncPermission</span></span>

<span data-ttu-id="b0332-183">GetClientNetworkSyncPermission 用于查询 Office 对网络成本和电源使用的同步试探法是否已被覆盖。</span><span class="sxs-lookup"><span data-stu-id="b0332-183">GetClientNetworkSyncPermission is used to query whether Office's synchronizing heuristics for network cost and power usage are overridden.</span></span> <span data-ttu-id="b0332-184">在3g 或其他高成本网络上, 或在使用电池运行而不是插入时, Office 可能会选择阻止网络流量, 直到 opportune 时间。</span><span class="sxs-lookup"><span data-stu-id="b0332-184">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span>
  
`HRESULT ILSCLocalSyncClient::GetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [out] VARIANT_BOOL * pfSyncEnabled)`

##### <a name="parameters"></a><span data-ttu-id="b0332-185">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-185">Parameters</span></span>

 <span data-ttu-id="b0332-186">_nspType_</span><span class="sxs-lookup"><span data-stu-id="b0332-186">_nspType_</span></span>
  
<span data-ttu-id="b0332-187">定义要查询的成本启发的标志。</span><span class="sxs-lookup"><span data-stu-id="b0332-187">A flag which defines which cost heuristic to query.</span></span> <span data-ttu-id="b0332-188">请参阅[Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="b0332-188">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span> 
  
 <span data-ttu-id="b0332-189">_pfSyncEnabled_</span><span class="sxs-lookup"><span data-stu-id="b0332-189">_pfSyncEnabled_</span></span>
  
<span data-ttu-id="b0332-190">指定请求的成本试探法当前是否已覆盖。</span><span class="sxs-lookup"><span data-stu-id="b0332-190">Specifies whether the requested cost heuristic is currently overridden or not.</span></span> <span data-ttu-id="b0332-191">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-191">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-192">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-192">Return values</span></span>

|<span data-ttu-id="b0332-193">值</span><span class="sxs-lookup"><span data-stu-id="b0332-193">Value</span></span>|<span data-ttu-id="b0332-194">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-194">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-195">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-195">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-196">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-196">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-197">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-197">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-198">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-198">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-199">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-199">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-200">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-200">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-201">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-201">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-202">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-202">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetfilestatus"></a><span data-ttu-id="b0332-203">ILSCLocalSyncClient:: GetFileStatus</span><span class="sxs-lookup"><span data-stu-id="b0332-203">ILSCLocalSyncClient::GetFileStatus</span></span>

<span data-ttu-id="b0332-204">GetFileStatus 用于收集特定文件的信息: 无论它是否存在于缓存中, 如果有挂起的与服务器副本的通信, 以及 Office 2013 是否具有来自本地副本的最新数据。</span><span class="sxs-lookup"><span data-stu-id="b0332-204">GetFileStatus is used to gather information for a specific file: whether it exists in the cache, if it has pending communication with the server copy, and if Office 2013 has the most up to date data from the local copy.</span></span> <span data-ttu-id="b0332-205">它需要[枚举 LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)值的按位标志, 以确定 CsiSyncClient COM 对象要查询的信息。</span><span class="sxs-lookup"><span data-stu-id="b0332-205">It requires a bitwise flag of [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag) values to determine what information the CsiSyncClient COM object is to query for.</span></span> 
  
`HRESULT ILSCLocalSyncClient::GetFileStatus ([in] BSTR bstrResourceID, [in] LSCStatusFlag sfRequestedStatus, [out] BSTR * pbstrFileSystemPath, [out] BSTR * pbstrETag, [out] LSCStatusFlag * psfFileStatus)`

##### <a name="parameters"></a><span data-ttu-id="b0332-206">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-206">Parameters</span></span>

 <span data-ttu-id="b0332-207">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0332-207">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0332-208">标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-208">The string which identifies the file on the client.</span></span> <span data-ttu-id="b0332-209">此值必须为非空, 最多为128个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-209">This value must be non-empty, with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0332-210">_sfRequestedStatus_</span><span class="sxs-lookup"><span data-stu-id="b0332-210">_sfRequestedStatus_</span></span>
  
<span data-ttu-id="b0332-211">定义要返回的信息的标志。</span><span class="sxs-lookup"><span data-stu-id="b0332-211">A flag which defines what information to return.</span></span> <span data-ttu-id="b0332-212">请参阅[Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="b0332-212">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
 <span data-ttu-id="b0332-213">_pbstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-213">_pbstrFileSystemPath_</span></span>
  
<span data-ttu-id="b0332-214">标识由客户端上的_bstrResourceID_标识的文件的位置的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-214">The string which identifies the location of the file identified by  _bstrResourceID_ on the client.</span></span> <span data-ttu-id="b0332-215">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-215">Must not be null.</span></span> 
  
 <span data-ttu-id="b0332-216">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="b0332-216">_pbstrETag_</span></span>
  
<span data-ttu-id="b0332-217">一个字符串, 它将包含由_bstrResourceID_标识的文件的 eTag。</span><span class="sxs-lookup"><span data-stu-id="b0332-217">A string which will contain the eTag for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="b0332-218">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-218">Must not be null.</span></span> 
  
 <span data-ttu-id="b0332-219">_psfFileStatus_</span><span class="sxs-lookup"><span data-stu-id="b0332-219">_psfFileStatus_</span></span>
  
<span data-ttu-id="b0332-220">一个标志, 该标志将包含通过_sfRequestedStatus_为_bstrResourceID_标识的文件请求的状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-220">A flag which will contain the status requested via  _sfRequestedStatus_ for the file identified by  _bstrResourceID_.</span></span> <span data-ttu-id="b0332-221">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-221">Must not be null.</span></span> <span data-ttu-id="b0332-222">请参阅[Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag)。</span><span class="sxs-lookup"><span data-stu-id="b0332-222">See [Enum LSCStatusFlag](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCStatusFlag).</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-223">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-223">Return values</span></span>

|<span data-ttu-id="b0332-224">值</span><span class="sxs-lookup"><span data-stu-id="b0332-224">Value</span></span>|<span data-ttu-id="b0332-225">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-225">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-226">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-226">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-227">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-227">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-228">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-228">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-229">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-229">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-230">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0332-230">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0332-231">_bstrResourceID_指定的文件信息在缓存中不存在。</span><span class="sxs-lookup"><span data-stu-id="b0332-231">The file information specified by  _bstrResourceID_ does not exist in the cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-232">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0332-232">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="b0332-233">已请求 LSCStatusFlag_LocalFileUnchanged 或_bstrResourceID_指定的文件已锁定或丢失。</span><span class="sxs-lookup"><span data-stu-id="b0332-233">LSCStatusFlag_LocalFileUnchanged was requested or the file specified by  _bstrResourceID_ is locked or missing.</span></span>  <br/> |
|<span data-ttu-id="b0332-234">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-234">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-235">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-235">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-236">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-236">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-237">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-237">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientgetsupportedfileextensions"></a><span data-ttu-id="b0332-238">ILSCLocalSyncClient:: GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="b0332-238">ILSCLocalSyncClient::GetSupportedFileExtensions</span></span>
<span data-ttu-id="b0332-239"><a name="ILSCLocalSyncClient_GetSupportedFileExtensions"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-239"></span></span>

<span data-ttu-id="b0332-240">GetSupportedFileExtensions 返回 CsiSyncClient COM 对象当前支持的、由管道分隔的文件扩展名列表。</span><span class="sxs-lookup"><span data-stu-id="b0332-240">GetSupportedFileExtensions returns a list of pipe-delimited file extensions which are currently supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0332-241">请注意, 此列表可能会发生更改, 并且将通过 ILSCLocalSyncClient 中提供的 IPartnerActivityCallback 对象通知使用者[:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (请参阅 EventOccured)。</span><span class="sxs-lookup"><span data-stu-id="b0332-241">Note that this list may change, and the consumer will be notified of a change via the IPartnerActivityCallback object provided on [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) (See EventOccured).</span></span> 
  
<span data-ttu-id="b0332-242">返回的字符串示例如下: "| .docx | .docm | .pptx |"</span><span class="sxs-lookup"><span data-stu-id="b0332-242">An example of the string returned is as follows: "|docx|docm|pptx|"</span></span>
  
`HRESULT ILSCLocalSyncClient::GetSupportedFileExtensions ([out] BSTR * pbstrSupportedFileExtensions)`

##### <a name="parameters"></a><span data-ttu-id="b0332-243">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-243">Parameters</span></span>

 <span data-ttu-id="b0332-244">_pbstrSupportedFileExtensions_</span><span class="sxs-lookup"><span data-stu-id="b0332-244">_pbstrSupportedFileExtensions_</span></span>
  
<span data-ttu-id="b0332-245">要使用 CsiSyncClient COM 对象支持的一组由管道分隔的文件扩展名进行设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-245">A string to be set with a pipe-delimited set of file extensions supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0332-246">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-246">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-247">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-247">Return values</span></span>

|<span data-ttu-id="b0332-248">值</span><span class="sxs-lookup"><span data-stu-id="b0332-248">Value</span></span>|<span data-ttu-id="b0332-249">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-249">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-250">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-250">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-251">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-251">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-252">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-252">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-253">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-253">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-254">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-254">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-255">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-255">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-256">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-256">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-257">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-257">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientinitialize"></a><span data-ttu-id="b0332-258">ILSCLocalSyncClient:: Initialize</span><span class="sxs-lookup"><span data-stu-id="b0332-258">ILSCLocalSyncClient::Initialize</span></span>
<span data-ttu-id="b0332-259"><a name="ILSCLocalSyncClient_Initialize"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-259"></span></span>

<span data-ttu-id="b0332-260">初始化必须是调用的第一个方法。</span><span class="sxs-lookup"><span data-stu-id="b0332-260">Initialize must be the first method called.</span></span> <span data-ttu-id="b0332-261">否则, 所有其他 api 将返回 E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="b0332-261">Otherwise, all other APIs will return E_LSC_NOTINITIALIZED.</span></span> <span data-ttu-id="b0332-262">对已初始化的对象调用 Initialize 将返回 S_OK, 并且不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b0332-262">Calling Initialize on an already initialized object returns S_OK and does nothing.</span></span> <span data-ttu-id="b0332-263">如果返回 E_LSC_CACHEMISMATCH, 则调用方可能会调用[ILSCLocalSyncClient:: ResetCache](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache)以删除与给定 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-263">If E_LSC_CACHEMISMATCH is returned, the caller may call [ILSCLocalSyncClient::ResetCache ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ResetCache) to delete the cache associated with the given SuppliedID.</span></span> <span data-ttu-id="b0332-264">但是, 在这种情况下, 其他 api 仍将返回 E_LSC_NOTINITIALIZED。</span><span class="sxs-lookup"><span data-stu-id="b0332-264">However, in this case other APIs will still return E_LSC_NOTINITIALIZED.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Initialize ([in] BSTR bstrSuppliedID, [in] BSTR bstrProgID, [in] BSTR bstrFileSystemDirectoryHint, [in] IPartnerActivityCallback * pEventCallback, [out] VARIANT_BOOL * pfCreatedNewCache)`

##### <a name="parameters"></a><span data-ttu-id="b0332-265">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-265">Parameters</span></span>

 <span data-ttu-id="b0332-266">_bstrSuppliedID_</span><span class="sxs-lookup"><span data-stu-id="b0332-266">_bstrSuppliedID_</span></span>
  
<span data-ttu-id="b0332-267">标识使用者以及要使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-267">Identifies the consumer and which cache to use.</span></span> <span data-ttu-id="b0332-268">必须为非空, 最多为32个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-268">Must be non-empty with a maximum of 32 characters.</span></span> 
  
 <span data-ttu-id="b0332-269">_bstrProgID_</span><span class="sxs-lookup"><span data-stu-id="b0332-269">_bstrProgID_</span></span>
  
<span data-ttu-id="b0332-270">标识用于双向通信的使用者的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="b0332-270">Identifies the consumer's COM object for two-way communication.</span></span> <span data-ttu-id="b0332-271">必须为非空, 最多为39个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-271">Must be non-empty with a maximum of 39 characters.</span></span> <span data-ttu-id="b0332-272">有关 ProgIDs 的详细信息, 请参阅[ \<ProgID\> Key](https://docs.microsoft.com/windows/desktop/com/-progid--key) 。</span><span class="sxs-lookup"><span data-stu-id="b0332-272">See [\<ProgID\> Key](https://docs.microsoft.com/windows/desktop/com/-progid--key) for more information about ProgIDs.</span></span> 
  
 <span data-ttu-id="b0332-273">_bstrFileSystemDirectoryHint_</span><span class="sxs-lookup"><span data-stu-id="b0332-273">_bstrFileSystemDirectoryHint_</span></span>
  
<span data-ttu-id="b0332-274">标识将在其中存储本地文件的目录根。</span><span class="sxs-lookup"><span data-stu-id="b0332-274">Identifies the directory root in which local files will be stored.</span></span> <span data-ttu-id="b0332-275">必须为非空, 最多为256个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-275">Must be non-empty with a maximum of 256 characters.</span></span> <span data-ttu-id="b0332-276">该目录必须已经存在。</span><span class="sxs-lookup"><span data-stu-id="b0332-276">The directory must already exist.</span></span> 
  
 <span data-ttu-id="b0332-277">_pEventCallback_</span><span class="sxs-lookup"><span data-stu-id="b0332-277">_pEventCallback_</span></span>
  
<span data-ttu-id="b0332-278">CsiSyncClient 将在发生更改时通知的回调接口。</span><span class="sxs-lookup"><span data-stu-id="b0332-278">The callback interface which CsiSyncClient will notify on changes.</span></span> <span data-ttu-id="b0332-279">请参阅 IPartnerActivityCallback:: EventOccurred。</span><span class="sxs-lookup"><span data-stu-id="b0332-279">See IPartnerActivityCallback::EventOccurred.</span></span> <span data-ttu-id="b0332-280">此值不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-280">This value must not be null.</span></span> 
  
 <span data-ttu-id="b0332-281">_pfCreatedNewCache_</span><span class="sxs-lookup"><span data-stu-id="b0332-281">_pfCreatedNewCache_</span></span>
  
<span data-ttu-id="b0332-282">返回一个指示是否已创建新的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-282">Returns whether a new cache was created.</span></span> <span data-ttu-id="b0332-283">如果没有与 SuppliedID 关联的缓存, 则将创建一个缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-283">If no cache is associated with the SuppliedID, one will be created.</span></span> <span data-ttu-id="b0332-284">此值不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-284">This value must not be null.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-285">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-285">Return values</span></span>

|<span data-ttu-id="b0332-286">值</span><span class="sxs-lookup"><span data-stu-id="b0332-286">Value</span></span>|<span data-ttu-id="b0332-287">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-287">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-288">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-288">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-289">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-289">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-290">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-290">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-291">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-291">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-292">E_LSC_CACHEMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0332-292">E_LSC_CACHEMISMATCH</span></span>  <br/> |<span data-ttu-id="b0332-293">SuppliedID 已有与之关联的缓存, 但其 ProgId 或 FileSystemDirectoryHint 与提供的是不同的 ProgId 或文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-293">A SuppliedID already has a cache associated with it, but has a different ProgId or FileSystemDirectoryHint than the ones provided.</span></span>  <br/> |
|<span data-ttu-id="b0332-294">E_LSC_DIRECTORYHINTCONFLICT</span><span class="sxs-lookup"><span data-stu-id="b0332-294">E_LSC_DIRECTORYHINTCONFLICT</span></span>  <br/> |<span data-ttu-id="b0332-295">FileSystemDirectoryHint (或子文件夹) 已存在于不同的缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0332-295">The FileSystemDirectoryHint (or a subfolder) already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-296">E_LAC_PROGIDCONFLICT</span><span class="sxs-lookup"><span data-stu-id="b0332-296">E_LAC_PROGIDCONFLICT</span></span>  <br/> |<span data-ttu-id="b0332-297">ProgID 已经存在于不同的缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0332-297">The ProgID already exists on a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-298">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-298">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-299">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-299">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientlocalfilechange"></a><span data-ttu-id="b0332-300">ILSCLocalSyncClient:: LocalFileChange</span><span class="sxs-lookup"><span data-stu-id="b0332-300">ILSCLocalSyncClient::LocalFileChange</span></span>
<span data-ttu-id="b0332-301"><a name="ILSCLocalSyncClient_LocalFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-301"></span></span>

<span data-ttu-id="b0332-302">LocalFileChange 用于通知 CsiSyncClient COM 对象尝试上传指定的文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-302">LocalFileChange is used to tell the CsiSyncClient COM object to attempt to upload the specified file.</span></span> <span data-ttu-id="b0332-303">此方法将为上载准备文件, 包括读取文件的当前内容。</span><span class="sxs-lookup"><span data-stu-id="b0332-303">The method will prepare the file for upload, including reading the file's current contents.</span></span> <span data-ttu-id="b0332-304">如果上载已挂起, 将放弃上一个上载, 并为上载准备好的新内容。</span><span class="sxs-lookup"><span data-stu-id="b0332-304">If an upload is already pending, the previous upload will be discarded and the new contents prepared for upload.</span></span> <span data-ttu-id="b0332-305">如果在应用程序中打开文件进行编辑, 则此方法将返回 S_OK, 而不准备上载文件 (如果存在更改, 应用程序应已执行此步骤)。</span><span class="sxs-lookup"><span data-stu-id="b0332-305">If the file is open for editing in an application, this method will return S_OK without preparing the file for upload (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="b0332-306">此方法将允许上载 (如果之前已将其标记为 "已阻止上载") (请参阅[ILSCLocalSyncClient:: RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile))。</span><span class="sxs-lookup"><span data-stu-id="b0332-306">This method will allow uploads if it was marked as uploads blocked previously (see [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)).</span></span>
  
`HRESULT ILSCLocalSyncClient::LocalFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0332-307">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-307">Parameters</span></span>

 <span data-ttu-id="b0332-308">_bstrFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-308">_bstrFileSystemPath_</span></span>
  
<span data-ttu-id="b0332-309">一个标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-309">A string which identifies the file on the client.</span></span> <span data-ttu-id="b0332-310">此值必须为非空的本地路径, 最多为256个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-310">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0332-311">调用[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)时, 此路径必须位于由 FileSystemDirectoryHint 指定的目录树中。</span><span class="sxs-lookup"><span data-stu-id="b0332-311">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was made.</span></span> 
  
 <span data-ttu-id="b0332-312">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0332-312">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0332-313">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-313">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0332-314">此值必须为非空, 最多为128个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-314">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0332-315">_bstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-315">_bstrWebPath_</span></span>
  
<span data-ttu-id="b0332-316">一个标识服务器上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-316">A string which identifies the file on the server.</span></span> <span data-ttu-id="b0332-317">此值必须为非空、有效的 URL, 但不能长于 INTERNET_MAX_URL_LENGTH 定义的https://support.microsoft.com/kb/208427。</span><span class="sxs-lookup"><span data-stu-id="b0332-317">This value must be non-empty, valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-318">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-318">Return values</span></span>

|<span data-ttu-id="b0332-319">值</span><span class="sxs-lookup"><span data-stu-id="b0332-319">Value</span></span>|<span data-ttu-id="b0332-320">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-320">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-321">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-321">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-322">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-322">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-323">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-323">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-324">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-324">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-325">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0332-325">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0332-326">_bstrFileSystemPath_指定的文件的 ResourceID 与指定的 ResourceID 不同。</span><span class="sxs-lookup"><span data-stu-id="b0332-326">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span> <span data-ttu-id="b0332-327">当返回此错误时, 将发送 LSCEventType_OnFilePathConflict 类型的事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-327">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="b0332-328">请参阅[ILSCLocalSyncClient:: GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="b0332-328">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="b0332-329">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0332-329">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0332-330">文件是在操作中删除的。</span><span class="sxs-lookup"><span data-stu-id="b0332-330">The file was deleted mid-operation.</span></span>  <br/> |
|<span data-ttu-id="b0332-331">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b0332-331">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="b0332-332">CsiSyncClient COM 对象不支持给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0332-332">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0332-333">请参阅[ILSCLocalSyncClient:: GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)。</span><span class="sxs-lookup"><span data-stu-id="b0332-333">See [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions).</span></span>  <br/> |
|<span data-ttu-id="b0332-334">E_LSC_FILEUPTODATE</span><span class="sxs-lookup"><span data-stu-id="b0332-334">E_LSC_FILEUPTODATE</span></span>  <br/> |<span data-ttu-id="b0332-335">由于缓存中的文件包含磁盘的最新更改, 因此 COM 对象未计划上载。</span><span class="sxs-lookup"><span data-stu-id="b0332-335">The COM object did not schedule an upload because the file in the cache had the most recent changes from the disk.</span></span>  <br/> |
|<span data-ttu-id="b0332-336">E_LSC_LOCALFILEUNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0332-336">E_LSC_LOCALFILEUNAVAILABLE</span></span>  <br/> |<span data-ttu-id="b0332-337">_bstrFileSystemPath_指定的文件已丢失或被锁定。</span><span class="sxs-lookup"><span data-stu-id="b0332-337">The file specified by  _bstrFileSystemPath_ is missing or locked.</span></span>  <br/> |
|<span data-ttu-id="b0332-338">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0332-338">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0332-339">在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0332-339">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0332-340">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-340">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-341">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-341">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-342">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0332-342">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="b0332-343">_bstrResourceID_指定的文件具有与指定的 FileSystemPath 不同的。</span><span class="sxs-lookup"><span data-stu-id="b0332-343">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="b0332-344">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-344">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0332-345">指定的文件在其他缓存中已有挂起的更改, 并且尚未与使用者的缓存关联。</span><span class="sxs-lookup"><span data-stu-id="b0332-345">The file specified already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-346">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="b0332-347">提供的 WebPath 位于不同的缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0332-347">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-348">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-348">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-349">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-349">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientrenamefile"></a><span data-ttu-id="b0332-350">ILSCLocalSyncClient:: RenameFile</span><span class="sxs-lookup"><span data-stu-id="b0332-350">ILSCLocalSyncClient::RenameFile</span></span>
<span data-ttu-id="b0332-351"><a name="ILSCLocalSyncClient_RenameFile"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-351"></span></span>

<span data-ttu-id="b0332-352">RenameFile 将为给定的 ResourceID 关联新的 URL 和本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0332-352">RenameFile will associate a new URL and local path for a given ResourceID.</span></span> <span data-ttu-id="b0332-353">如果由 ResourceID 指定的文件在缓存中不存在, 则将尝试创建该文件并将其标记为下载。</span><span class="sxs-lookup"><span data-stu-id="b0332-353">If the file specified by the ResourceID doesn't already exist in the cache, an attempt will be made to create it and mark it for download.</span></span>
  
`HRESULT ILSCLocalSyncClient::RenameFile ([in] BSTR bstrResourceID, [in] BSTR bstrNewFileSystemPath, [in] BSTR bstrNewWebPath, [in] VARIANT_BOOL fBlockUploads)`

##### <a name="parameters"></a><span data-ttu-id="b0332-354">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-354">Parameters</span></span>

 <span data-ttu-id="b0332-355">_bstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0332-355">_bstrResourceID_</span></span>
  
<span data-ttu-id="b0332-356">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-356">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0332-357">此值必须为非空, 最多为128个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-357">This value must be non-empty with a maximum of 128 characters.</span></span> 
  
 <span data-ttu-id="b0332-358">_bstrNewFileSystemPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-358">_bstrNewFileSystemPath_</span></span>
  
<span data-ttu-id="b0332-359">一个字符串, 它指定文件的新本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0332-359">A string which specifies the new local path for the file.</span></span> <span data-ttu-id="b0332-360">此值必须为非空的本地路径, 最多为256个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-360">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0332-361">此路径必须位于由 FileSystemDirectoryHint 指定的目录树中进行初始化调用时。</span><span class="sxs-lookup"><span data-stu-id="b0332-361">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span> 
  
 <span data-ttu-id="b0332-362">_bstrNewWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-362">_bstrNewWebPath_</span></span>
  
<span data-ttu-id="b0332-363">一个字符串, 指定文件的新 URL。</span><span class="sxs-lookup"><span data-stu-id="b0332-363">A string which specifies the new URL for the file.</span></span> <span data-ttu-id="b0332-364">此值必须为非空的有效 URL, 但不能超过 INTERNET_MAX_URL_LENGTH (由https://support.microsoft.com/kb/208427定义)。</span><span class="sxs-lookup"><span data-stu-id="b0332-364">This value must be non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span> 
  
 <span data-ttu-id="b0332-365">_fBlockUploads_</span><span class="sxs-lookup"><span data-stu-id="b0332-365">_fBlockUploads_</span></span>
  
<span data-ttu-id="b0332-366">指定当前是否允许上载到新位置。</span><span class="sxs-lookup"><span data-stu-id="b0332-366">Specifies whether uploads to the new location are allowed currently.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-367">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-367">Return values</span></span>

|<span data-ttu-id="b0332-368">值</span><span class="sxs-lookup"><span data-stu-id="b0332-368">Value</span></span>|<span data-ttu-id="b0332-369">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-369">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-370">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-370">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-371">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-371">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-372">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-372">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-373">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-373">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-374">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0332-374">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0332-375">_bstrNewFileSystemPath_或_bstrNewWebPath_已存在于任何缓存中的另一个文件上。</span><span class="sxs-lookup"><span data-stu-id="b0332-375">The  _bstrNewFileSystemPath_ or  _bstrNewWebPath_ already exist on another file in any cache.</span></span> <span data-ttu-id="b0332-376">当返回此错误时, 将发送 LSCEventType_OnFilePathConflict 类型的事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-376">An event of type LSCEventType_OnFilePathConflict is sent when this error is returned.</span></span> <span data-ttu-id="b0332-377">请参阅[ILSCLocalSyncClient:: GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)。</span><span class="sxs-lookup"><span data-stu-id="b0332-377">See [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges).</span></span>  <br/> |
|<span data-ttu-id="b0332-378">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0332-378">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0332-379">在此方法运行过程中, 文件信息已从缓存中删除。</span><span class="sxs-lookup"><span data-stu-id="b0332-379">The file information was deleted from the cache while this method was running.</span></span>  <br/> |
|<span data-ttu-id="b0332-380">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0332-380">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0332-381">在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0332-381">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0332-382">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-382">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-383">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-383">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-384">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-384">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0332-385">指定的文件当前在 Office 应用程序中进行同步。</span><span class="sxs-lookup"><span data-stu-id="b0332-385">The file specified is currently synchronizing in an Office application.</span></span>  <br/> |
|<span data-ttu-id="b0332-386">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-386">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-387">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-387">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientresetcache"></a><span data-ttu-id="b0332-388">ILSCLocalSyncClient:: ResetCache</span><span class="sxs-lookup"><span data-stu-id="b0332-388">ILSCLocalSyncClient::ResetCache</span></span>
<span data-ttu-id="b0332-389"><a name="ILSCLocalSyncClient_ResetCache"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-389"></span></span>

<span data-ttu-id="b0332-390">ResetCache 将删除与初始化时提供的 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-390">ResetCache will delete the cache associated with the SuppliedID that was provided on Initialize.</span></span> <span data-ttu-id="b0332-391">这包括所有文件信息, 但会将这些文件同时保留在客户端和服务器上。</span><span class="sxs-lookup"><span data-stu-id="b0332-391">This includes all of the file information, but will leave the files on both the client and the server.</span></span> <span data-ttu-id="b0332-392">此方法还会使对象处于部分未初始化状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-392">This method also leaves the object in a partially uninitialized state.</span></span> <span data-ttu-id="b0332-393">在此之后, 唯一有效的调用是[ILSCLocalSyncClient:: Initialize](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)或[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)。</span><span class="sxs-lookup"><span data-stu-id="b0332-393">The only valid calls after this are [ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) or [ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize).</span></span> <span data-ttu-id="b0332-394">如果初始化失败并返回 E_LSC_CACHEMISMATCH, 则可能会调用此方法, 并将删除与失败调用一起提供的 SuppliedID 关联的缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-394">This method MAY be called if Initialize fails and returns E_LSC_CACHEMISMATCH, and will delete the cache associated with the SuppliedID that was provided with the failing call.</span></span>
  
`HRESULT ILSCLocalSyncClient::ResetCache()`

##### <a name="parameters"></a><span data-ttu-id="b0332-395">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-395">Parameters</span></span>

<span data-ttu-id="b0332-396">无</span><span class="sxs-lookup"><span data-stu-id="b0332-396">None</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-397">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-397">Return values</span></span>

|<span data-ttu-id="b0332-398">值</span><span class="sxs-lookup"><span data-stu-id="b0332-398">Value</span></span>|<span data-ttu-id="b0332-399">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-399">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-400">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-400">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-401">调用失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-401">The call failed.</span></span>  <br/> |
|<span data-ttu-id="b0332-402">E_LSC_NOTINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-402">E_LSC_NOTINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-403">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用 Initialize。</span><span class="sxs-lookup"><span data-stu-id="b0332-403">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) was not successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-404">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-404">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-405">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-405">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientserverfilechange"></a><span data-ttu-id="b0332-406">ILSCLocalSyncClient:: ServerFileChange</span><span class="sxs-lookup"><span data-stu-id="b0332-406">ILSCLocalSyncClient::ServerFileChange</span></span>
<span data-ttu-id="b0332-407"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-407"></span></span>

<span data-ttu-id="b0332-408">ServerFileChange 通知 CsiSyncClient COM 对象将指定的文件标记为下载。</span><span class="sxs-lookup"><span data-stu-id="b0332-408">ServerFileChange tells the CsiSyncClient COM object to mark the specified file for download.</span></span> <span data-ttu-id="b0332-409">如果文件已在 Office 应用程序中打开, 则此方法将返回 S_OK, 而不标记要下载的文件 (如果存在更改, 应用程序应已执行此步骤)。</span><span class="sxs-lookup"><span data-stu-id="b0332-409">If the file is open in an Office application for edit, this method will return S_OK without marking the file for download (the application should already do this step if there are changes).</span></span>
  
<span data-ttu-id="b0332-410">如果之前已将下载标记为 "已阻止下载", 此方法将允许下载 (请参阅 RenameFile)。</span><span class="sxs-lookup"><span data-stu-id="b0332-410">This method will allow downloads if it was marked as downloads blocked previously (see RenameFile).</span></span>
  
`HRESULT ILSCLocalSyncClient::ServerFileChange ([in] BSTR bstrFileSystemPath, [in] BSTR bstrWebPath, [in] BSTR bstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0332-411">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-411">Parameters</span></span>

|<span data-ttu-id="b0332-412">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-412">Parameter</span></span>|<span data-ttu-id="b0332-413">描述</span><span class="sxs-lookup"><span data-stu-id="b0332-413">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-414">bstrFileSystemPath</span><span class="sxs-lookup"><span data-stu-id="b0332-414">bstrFileSystemPath</span></span>  <br/> |<span data-ttu-id="b0332-415">一个标识客户端上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-415">A string which identifies the file on the client.</span></span> <span data-ttu-id="b0332-416">此值必须为非空的本地路径, 最多为256个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-416">This value must be a non-empty local path with a maximum of 256 characters.</span></span> <span data-ttu-id="b0332-417">此路径必须位于由 FileSystemDirectoryHint 指定的目录树中进行初始化调用时。</span><span class="sxs-lookup"><span data-stu-id="b0332-417">This path must be in the directory tree specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0332-418">bstrResourceID</span><span class="sxs-lookup"><span data-stu-id="b0332-418">bstrResourceID</span></span>  <br/> |<span data-ttu-id="b0332-419">一个标识文件的 ResourceID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-419">A string which identifies the ResourceID of the file.</span></span> <span data-ttu-id="b0332-420">此值必须为非空, 最多为128个字符。</span><span class="sxs-lookup"><span data-stu-id="b0332-420">This value must be non-empty with a maximum of 128 characters.</span></span>  <br/> |
|<span data-ttu-id="b0332-421">bstrWebPath</span><span class="sxs-lookup"><span data-stu-id="b0332-421">bstrWebPath</span></span>  <br/> |<span data-ttu-id="b0332-422">一个标识服务器上的文件的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-422">A string which identifies the file on the server.</span></span> <span data-ttu-id="b0332-423">此值必须为非空的有效 URL, 但不能长于 INTERNET_MAX_URL_LENGTH 定义的https://support.microsoft.com/kb/208427。</span><span class="sxs-lookup"><span data-stu-id="b0332-423">This value must be a non-empty valid URL, but no longer than INTERNET_MAX_URL_LENGTH, as defined by https://support.microsoft.com/kb/208427.</span></span>  <br/> |
   
##### <a name="return-values"></a><span data-ttu-id="b0332-424">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-424">Return values</span></span>

|<span data-ttu-id="b0332-425">值</span><span class="sxs-lookup"><span data-stu-id="b0332-425">Value</span></span>|<span data-ttu-id="b0332-426">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-426">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-427">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-427">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-428">未能设置缓存连接状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-428">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="b0332-429">E_LSC_CONFLICTINGFILE</span><span class="sxs-lookup"><span data-stu-id="b0332-429">E_LSC_CONFLICTINGFILE</span></span>  <br/> |<span data-ttu-id="b0332-430">_bstrFileSystemPath_指定的文件的 ResourceID 与指定的 ResourceID 不同。</span><span class="sxs-lookup"><span data-stu-id="b0332-430">The file specified by  _bstrFileSystemPath_ has a different ResourceID than specified.</span></span>  <br/> |
|<span data-ttu-id="b0332-431">E_LSC_FILENOTSUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b0332-431">E_LSC_FILENOTSUPPORTED</span></span>  <br/> |<span data-ttu-id="b0332-432">CsiSyncClient COM 对象不支持给定的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="b0332-432">The given file extension is not supported by the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0332-433">请参阅 GetSupportedFileExtensions。</span><span class="sxs-lookup"><span data-stu-id="b0332-433">See GetSupportedFileExtensions.</span></span>  <br/> |
|<span data-ttu-id="b0332-434">E_LSC_FILENOTFOUND</span><span class="sxs-lookup"><span data-stu-id="b0332-434">E_LSC_FILENOTFOUND</span></span>  <br/> |<span data-ttu-id="b0332-435">在 mid 操作中删除了文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-435">The file was deleted in mid-operation.</span></span>  <br/> |
|<span data-ttu-id="b0332-436">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-436">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-437">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-437">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-438">E_LSC_LOCALPATHNOTMAPPED</span><span class="sxs-lookup"><span data-stu-id="b0332-438">E_LSC_LOCALPATHNOTMAPPED</span></span>  <br/> |<span data-ttu-id="b0332-439">在进行初始化调用时, 给定的 FileSystemPath 不在 FileSystemDirectoryHint 指定的目录根目录下。</span><span class="sxs-lookup"><span data-stu-id="b0332-439">The given FileSystemPath is not under the directory root specified by the FileSystemDirectoryHint when the call to Initialize was made.</span></span>  <br/> |
|<span data-ttu-id="b0332-440">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-440">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-441">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-441">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-442">E_LSC_PATHMISMATCH</span><span class="sxs-lookup"><span data-stu-id="b0332-442">E_LSC_PATHMISMATCH</span></span>  <br/> |<span data-ttu-id="b0332-443">_bstrResourceID_指定的文件具有与指定的 FileSystemPath 不同的。</span><span class="sxs-lookup"><span data-stu-id="b0332-443">The file specified by  _bstrResourceID_ has a different FileSystemPath than specified.</span></span>  <br/> |
|<span data-ttu-id="b0332-444">E_LSC_PENDINGCHANGESINCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-444">E_LSC_PENDINGCHANGESINCACHE</span></span>  <br/> |<span data-ttu-id="b0332-445">指定的文件在其他缓存中已有挂起的更改, 并且尚未与使用者的缓存关联。</span><span class="sxs-lookup"><span data-stu-id="b0332-445">The specified file already has pending changes in a different cache and cannot yet be associated with the consumer's cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span><span class="sxs-lookup"><span data-stu-id="b0332-446">E_LSC_SERVERPATHINDIFFERENTCACHE</span></span>  <br/> |<span data-ttu-id="b0332-447">提供的 WebPath 位于不同的缓存中。</span><span class="sxs-lookup"><span data-stu-id="b0332-447">The WebPath provided falls under a different cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-448">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-448">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-449">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-449">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientconnectivitystate"></a><span data-ttu-id="b0332-450">ILSCLocalSyncClient:: SetClientConnectivityState</span><span class="sxs-lookup"><span data-stu-id="b0332-450">ILSCLocalSyncClient::SetClientConnectivityState</span></span>
<span data-ttu-id="b0332-451"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-451"></span></span>

<span data-ttu-id="b0332-452">将缓存设置为联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-452">Sets the cache into an online or offline state.</span></span> <span data-ttu-id="b0332-453">如果脱机, 则无论每个文件的_fBlockUploads_设置如何, Office 都不会尝试与服务器进行缓存中任何文件的通信。</span><span class="sxs-lookup"><span data-stu-id="b0332-453">If offline, Office will not attempt to communicate with the server for any files in that cache, regardless of each individual file's  _fBlockUploads_ setting.</span></span> 
  
`HRESULT ILSCLocalSyncClient::SetClientConnectivityState ([in] VARIANT_BOOL fIsOnline)`

##### <a name="parameters"></a><span data-ttu-id="b0332-454">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-454">Parameters</span></span>

 <span data-ttu-id="b0332-455">_fIsOnline_</span><span class="sxs-lookup"><span data-stu-id="b0332-455">_fIsOnline_</span></span>
  
<span data-ttu-id="b0332-456">用于确定缓存的连接状态的布尔值。</span><span class="sxs-lookup"><span data-stu-id="b0332-456">A boolean determining the connectivity state of the cache.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-457">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-457">Return values</span></span>

|<span data-ttu-id="b0332-458">值</span><span class="sxs-lookup"><span data-stu-id="b0332-458">Value</span></span>|<span data-ttu-id="b0332-459">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-459">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-460">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-460">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-461">未能设置缓存连接状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-461">Failure to set the cache connectivity state.</span></span>  <br/> |
|<span data-ttu-id="b0332-462">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-462">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-463">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-463">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-464">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-464">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-465">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-465">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-466">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-466">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-467">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-467">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientsetclientnetworksyncpermission"></a><span data-ttu-id="b0332-468">ILSCLocalSyncClient:: SetClientNetworkSyncPermission</span><span class="sxs-lookup"><span data-stu-id="b0332-468">ILSCLocalSyncClient::SetClientNetworkSyncPermission</span></span>
<span data-ttu-id="b0332-469"><a name="ILSCLocalSyncClient_ServerFileChange"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-469"></span></span>

<span data-ttu-id="b0332-470">SetClientNetworkSyncPermission 用于替代或 restoreOffice 同步试探法以实现网络成本和电源使用。</span><span class="sxs-lookup"><span data-stu-id="b0332-470">SetClientNetworkSyncPermission is used to either override or restoreOffice's synchronizing heuristics for network cost and power usage.</span></span> <span data-ttu-id="b0332-471">在3g 或其他高成本网络上, 或在使用电池运行而不是插入时, Office 可能会选择阻止网络流量, 直到 opportune 时间。</span><span class="sxs-lookup"><span data-stu-id="b0332-471">When on a 3G or other high cost network, or when running on battery versus being plugged in, Office may choose to block network traffic until a more opportune time.</span></span> <span data-ttu-id="b0332-472">此 API 的使用者可以使用它来覆盖 Office 的试探方法并强制进行同步。</span><span class="sxs-lookup"><span data-stu-id="b0332-472">The consumer of this API can use it to override Office's heuristics and force synchronizing to occur.</span></span>
  
`HRESULT ILSCLocalSyncClient::SetClientNetworkSyncPermission ([in] LSCNetworkSyncPermissionType nspType, [in] VARIANT_BOOL fEnableSync)`

##### <a name="parameters"></a><span data-ttu-id="b0332-473">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-473">Parameters</span></span>

 <span data-ttu-id="b0332-474">_nspType_</span><span class="sxs-lookup"><span data-stu-id="b0332-474">_nspType_</span></span>
  
<span data-ttu-id="b0332-475">一个标志, 该标志定义要覆盖的成本试探法。</span><span class="sxs-lookup"><span data-stu-id="b0332-475">A flag which defines which cost heuristic to override.</span></span> <span data-ttu-id="b0332-476">请参阅[Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType)。</span><span class="sxs-lookup"><span data-stu-id="b0332-476">See [Enum LSCNetworkSyncPermissionType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCNetworkSyncPermissionType).</span></span>
  
 <span data-ttu-id="b0332-477">_fEnableSync_</span><span class="sxs-lookup"><span data-stu-id="b0332-477">_fEnableSync_</span></span>
  
<span data-ttu-id="b0332-478">指定是否强制在上进行同步, 从而替代该成本试探法, 或不再覆盖它。</span><span class="sxs-lookup"><span data-stu-id="b0332-478">Specifies whether to force synchronizing on, thus overriding that cost heuristic, or to no longer override it.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-479">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-479">Return values</span></span>

|<span data-ttu-id="b0332-480">值</span><span class="sxs-lookup"><span data-stu-id="b0332-480">Value</span></span>|<span data-ttu-id="b0332-481">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-481">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-482">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-482">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-483">重写同步试探法失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-483">Failure to override synchronizing heuristics.</span></span>  <br/> |
|<span data-ttu-id="b0332-484">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-484">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-485">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-485">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-486">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-486">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-487">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-487">The call succeeded.</span></span>  <br/> |
   
#### <a name="ilsclocalsyncclientuninitialize"></a><span data-ttu-id="b0332-488">ILSCLocalSyncClient:: 取消初始化</span><span class="sxs-lookup"><span data-stu-id="b0332-488">ILSCLocalSyncClient::Uninitialize</span></span>
<span data-ttu-id="b0332-489"><a name="ILSCLocalSyncClient_Uninitialize"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-489"></span></span>

<span data-ttu-id="b0332-490">从 COM 对象中卸载缓存并执行关闭操作。</span><span class="sxs-lookup"><span data-stu-id="b0332-490">Unloads the cache from the COM object and perform closing operations.</span></span> <span data-ttu-id="b0332-491">[ILSCLocalSyncClient:: 取消初始化](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize)在销毁 COM 对象之前, 必须调用。</span><span class="sxs-lookup"><span data-stu-id="b0332-491">[ILSCLocalSyncClient::Uninitialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Uninitialize) MUST be called before destroying the COM object.</span></span> <span data-ttu-id="b0332-492">调用后, 不能调用任何其他 api, 必须销毁 COM 对象并创建新的, 如果您想要继续操作。</span><span class="sxs-lookup"><span data-stu-id="b0332-492">Once called, no other APIs can be called, the COM object MUST be destroyed and a new one created if you wish to continue operations.</span></span> 
  
`HRESULT ILSCLocalSyncClient::Uninitialize ()`

##### <a name="parameters"></a><span data-ttu-id="b0332-493">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-493">Parameters</span></span>

<span data-ttu-id="b0332-494">无。</span><span class="sxs-lookup"><span data-stu-id="b0332-494">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-495">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-495">Return values</span></span>

|<span data-ttu-id="b0332-496">值</span><span class="sxs-lookup"><span data-stu-id="b0332-496">Value</span></span>|<span data-ttu-id="b0332-497">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-497">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-498">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-498">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-499">取消初始化失败。</span><span class="sxs-lookup"><span data-stu-id="b0332-499">Failure to uninitialize.</span></span>  <br/> |
|<span data-ttu-id="b0332-500">E_LSC_NOINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="b0332-500">E_LSC_NOINITIALIZED</span></span>  <br/> |<span data-ttu-id="b0332-501">[ILSCLocalSyncClient::](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize)过去未成功调用初始化。</span><span class="sxs-lookup"><span data-stu-id="b0332-501">[ILSCLocalSyncClient::Initialize ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_Initialize) has not been successfully called in the past.</span></span>  <br/> |
|<span data-ttu-id="b0332-502">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-502">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-503">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-503">The call succeeded.</span></span>  <br/> |
   
### <a name="interface-ienumlscevent"></a><span data-ttu-id="b0332-504">接口 IEnumLSCEvent</span><span class="sxs-lookup"><span data-stu-id="b0332-504">Interface IEnumLSCEvent</span></span>

<span data-ttu-id="b0332-505">此接口表示 ILSCEvent 事件的列表。</span><span class="sxs-lookup"><span data-stu-id="b0332-505">This interface represents a list of ILSCEvent events.</span></span>
  
<span data-ttu-id="b0332-506">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0332-506">**Public member functions**</span></span>

#### <a name="ienumlsceventfnext"></a><span data-ttu-id="b0332-507">IEnumLSCEvent:: FNext</span><span class="sxs-lookup"><span data-stu-id="b0332-507">IEnumLSCEvent::FNext</span></span>

<span data-ttu-id="b0332-508">从事件列表中检索下一个事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-508">Retrieves the next event from the list of events.</span></span>
  
`HRESULT IEnumLSCEvent::FNext ([out] ILSCEvent ** ppiLSCEvent)`

##### <a name="parameters"></a><span data-ttu-id="b0332-509">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-509">Parameters</span></span>

 <span data-ttu-id="b0332-510">_ppiLSCEvent_</span><span class="sxs-lookup"><span data-stu-id="b0332-510">_ppiLSCEvent_</span></span>
  
<span data-ttu-id="b0332-511">指向 ILSCEvent 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b0332-511">A pointer to an ILSCEvent interface.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-512">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-512">Return values</span></span>

|<span data-ttu-id="b0332-513">值</span><span class="sxs-lookup"><span data-stu-id="b0332-513">Value</span></span>|<span data-ttu-id="b0332-514">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-514">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-515">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-515">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-516">没有其他事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-516">There are no more events.</span></span>  <br/> |
|<span data-ttu-id="b0332-517">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-517">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-518">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-518">The call was successful.</span></span>  <br/> |
   
#### <a name="ienumlsceventreset"></a><span data-ttu-id="b0332-519">IEnumLSCEvent:: Reset</span><span class="sxs-lookup"><span data-stu-id="b0332-519">IEnumLSCEvent::Reset</span></span>

<span data-ttu-id="b0332-520">将枚举器重置为第一个事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-520">Resets the enumerator to the first event.</span></span>
  
`HRESULT IEnumLSCEvent::Reset ()`

##### <a name="parameters"></a><span data-ttu-id="b0332-521">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-521">Parameters</span></span>

<span data-ttu-id="b0332-522">无。</span><span class="sxs-lookup"><span data-stu-id="b0332-522">None.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-523">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-523">Return values</span></span>

<span data-ttu-id="b0332-524">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-524">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent"></a><span data-ttu-id="b0332-525">接口 ILSCEvent</span><span class="sxs-lookup"><span data-stu-id="b0332-525">Interface ILSCEvent</span></span>

<span data-ttu-id="b0332-526">此接口表示同步事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-526">This interface represents a synchronizing event.</span></span> <span data-ttu-id="b0332-527">可以从接口检索有关事件的所有信息。</span><span class="sxs-lookup"><span data-stu-id="b0332-527">All information about the event can be retrieved from the interface.</span></span>
  
<span data-ttu-id="b0332-528">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0332-528">**Public member functions**</span></span>

#### <a name="ilsceventgetconflictstatus"></a><span data-ttu-id="b0332-529">ILSCEvent:: GetConflictStatus</span><span class="sxs-lookup"><span data-stu-id="b0332-529">ILSCEvent::GetConflictStatus</span></span>

<span data-ttu-id="b0332-530">请注意, 在调用[ILSCLocalSyncClient:: GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)时, 将填充此值, 而不是在创建事件时填充, 因此您仅具有文件的当前状态, 而不是在冲突状态更改时文件的状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-530">Note that this value is populated when [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) is called, not when the event was created, so you will only have the current status of the file, not the status of the file when the conflict status changed.</span></span> 
  
<span data-ttu-id="b0332-531">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnLocalConflictStateChanged 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-531">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnLocalConflictStateChanged.</span></span> 
  
`HRESULT ILSCEvent::GetConflictStatus ([out] VARIANT_BOOL * pfIsInConflict)`

##### <a name="parameters"></a><span data-ttu-id="b0332-532">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-532">Parameters</span></span>

 <span data-ttu-id="b0332-533">_pfIsInConflict_</span><span class="sxs-lookup"><span data-stu-id="b0332-533">_pfIsInConflict_</span></span>
  
<span data-ttu-id="b0332-534">与事件关联的文件的当前冲突状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-534">The current conflict status of the file associated with the event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-535">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-535">Return values</span></span>

<span data-ttu-id="b0332-536">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-536">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeterror"></a><span data-ttu-id="b0332-537">ILSCEvent:: GetError</span><span class="sxs-lookup"><span data-stu-id="b0332-537">ILSCEvent::GetError</span></span>

<span data-ttu-id="b0332-538">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-538">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetError ([out] LONG * pnError)`

##### <a name="parameters"></a><span data-ttu-id="b0332-539">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-539">Parameters</span></span>

 <span data-ttu-id="b0332-540">_pnError_</span><span class="sxs-lookup"><span data-stu-id="b0332-540">_pnError_</span></span>
  
<span data-ttu-id="b0332-541">与此事件关联的错误。</span><span class="sxs-lookup"><span data-stu-id="b0332-541">The error associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-542">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-542">Return values</span></span>

<span data-ttu-id="b0332-543">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-543">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetetag"></a><span data-ttu-id="b0332-544">ILSCEvent:: GetETag</span><span class="sxs-lookup"><span data-stu-id="b0332-544">ILSCEvent::GetETag</span></span>

<span data-ttu-id="b0332-545">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-545">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetETag ([out] BSTR * pbstrETag)`

##### <a name="parameters"></a><span data-ttu-id="b0332-546">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-546">Parameters</span></span>

 <span data-ttu-id="b0332-547">_pbstrETag_</span><span class="sxs-lookup"><span data-stu-id="b0332-547">_pbstrETag_</span></span>
  
<span data-ttu-id="b0332-548">与此事件关联的 ETag</span><span class="sxs-lookup"><span data-stu-id="b0332-548">The ETag associated with this event</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-549">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-549">Return values</span></span>

<span data-ttu-id="b0332-550">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-550">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgeteventtype"></a><span data-ttu-id="b0332-551">ILSCEvent:: GetEventType</span><span class="sxs-lookup"><span data-stu-id="b0332-551">ILSCEvent::GetEventType</span></span>

<span data-ttu-id="b0332-552">获取此事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-552">Gets the type for this event.</span></span>
  
`HRESULT ILSCEvent::GetEventType ([out] LSCEventType * pnEventType)`

##### <a name="parameters"></a><span data-ttu-id="b0332-553">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-553">Parameters</span></span>

 <span data-ttu-id="b0332-554">_pnEventType_</span><span class="sxs-lookup"><span data-stu-id="b0332-554">_pnEventType_</span></span>
  
<span data-ttu-id="b0332-555">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-555">The event type of this event.</span></span> <span data-ttu-id="b0332-556">有关有效值, 请参阅[Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。</span><span class="sxs-lookup"><span data-stu-id="b0332-556">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for valid values.</span></span> <span data-ttu-id="b0332-557">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-557">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-558">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-558">Return values</span></span>

|<span data-ttu-id="b0332-559">值</span><span class="sxs-lookup"><span data-stu-id="b0332-559">Value</span></span>|<span data-ttu-id="b0332-560">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-560">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-561">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-561">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-562">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-562">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-563">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-563">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-564">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-564">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetlocalworkingpath"></a><span data-ttu-id="b0332-565">ILSCEvent:: GetLocalWorkingPath</span><span class="sxs-lookup"><span data-stu-id="b0332-565">ILSCEvent::GetLocalWorkingPath</span></span>

<span data-ttu-id="b0332-566">获取此事件的本地工作路径。</span><span class="sxs-lookup"><span data-stu-id="b0332-566">Gets the local working path for this event.</span></span>
  
`HRESULT ILSCEvent::GetLocalWorkingPath ([out] BSTR * pbstrLocalWorkingPath)`

##### <a name="parameters"></a><span data-ttu-id="b0332-567">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-567">Parameters</span></span>

 <span data-ttu-id="b0332-568">_pbstrLocalWorkingPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-568">_pbstrLocalWorkingPath_</span></span>
  
<span data-ttu-id="b0332-569">此事件所属于的文件的本地路径。</span><span class="sxs-lookup"><span data-stu-id="b0332-569">The local path of the file to which this event pertains.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-570">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-570">Return values</span></span>

<span data-ttu-id="b0332-571">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-571">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceid"></a><span data-ttu-id="b0332-572">ILSCEvent:: GetResourceID</span><span class="sxs-lookup"><span data-stu-id="b0332-572">ILSCEvent::GetResourceID</span></span>

<span data-ttu-id="b0332-573">获取事件的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="b0332-573">Gets the resource ID for the event.</span></span>
  
`HRESULT ILSCEvent::GetResourceID ([out] BSTR * pbstrResourceID)`

##### <a name="parameters"></a><span data-ttu-id="b0332-574">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-574">Parameters</span></span>

 <span data-ttu-id="b0332-575">_pbstrResourceID_</span><span class="sxs-lookup"><span data-stu-id="b0332-575">_pbstrResourceID_</span></span>
  
<span data-ttu-id="b0332-576">与此事件关联的文件的资源 id。</span><span class="sxs-lookup"><span data-stu-id="b0332-576">The ResourceID of the file associated with this event.</span></span>
  
##### <a name="return-values"></a><span data-ttu-id="b0332-577">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-577">Return values</span></span>

<span data-ttu-id="b0332-578">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-578">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetresourceidattempted"></a><span data-ttu-id="b0332-579">ILSCEvent:: GetResourceIDAttempted</span><span class="sxs-lookup"><span data-stu-id="b0332-579">ILSCEvent::GetResourceIDAttempted</span></span>

<span data-ttu-id="b0332-580">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnFilePathConflict 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-580">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> <span data-ttu-id="b0332-581">当调用[ILSCLocalSyncClient:: LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient:: ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient:: RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)导致 Web 路径或本地路径与 Office 文件缓存中的其他文件发生冲突时, 这生成事件。</span><span class="sxs-lookup"><span data-stu-id="b0332-581">When a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) would cause a Web Path or Local Path collision with another file in the Office file cache, this event is generated.</span></span> 
  
`HRESULT ILSCEvent::GetResourceIDAttempted ([out] BSTR * pbstrResourceIDAttempted)`

##### <a name="parameters"></a><span data-ttu-id="b0332-582">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-582">Parameters</span></span>

 <span data-ttu-id="b0332-583">_pbstrResourceIDAttempted_</span><span class="sxs-lookup"><span data-stu-id="b0332-583">_pbstrResourceIDAttempted_</span></span>
  
<span data-ttu-id="b0332-584">导致此事件生成的 ResourceID。</span><span class="sxs-lookup"><span data-stu-id="b0332-584">The ResourceID that caused this event to get generated.</span></span> <span data-ttu-id="b0332-585">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-585">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-586">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-586">Return values</span></span>

<span data-ttu-id="b0332-587">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-587">Always returns S_OK.</span></span> 
  
#### <a name="ilsceventgetsyncerrortype"></a><span data-ttu-id="b0332-588">ILSCEvent:: GetSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="b0332-588">ILSCEvent::GetSyncErrorType</span></span>

<span data-ttu-id="b0332-589">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnServerChangesDownloaded 或 LSCEventType_OnLocalChangesUploaded 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-589">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnServerChangesDownloaded or LSCEventType_OnLocalChangesUploaded.</span></span> 
  
`HRESULT ILSCEvent::GetSyncErrorType ([out] LSCEventSyncErrorType * pnSyncErrorType)`

##### <a name="parameters"></a><span data-ttu-id="b0332-590">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-590">Parameters</span></span>

 <span data-ttu-id="b0332-591">_pnSyncErrorType_</span><span class="sxs-lookup"><span data-stu-id="b0332-591">_pnSyncErrorType_</span></span>
  
<span data-ttu-id="b0332-592">与此事件关联的错误类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-592">The error type associated with this event.</span></span> <span data-ttu-id="b0332-593">有关潜在值, 请参阅[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) 。</span><span class="sxs-lookup"><span data-stu-id="b0332-593">See [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) for potential values.</span></span> <span data-ttu-id="b0332-594">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-594">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-595">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-595">Return values</span></span>

|<span data-ttu-id="b0332-596">值</span><span class="sxs-lookup"><span data-stu-id="b0332-596">Value</span></span>|<span data-ttu-id="b0332-597">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-597">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-598">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-598">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-599">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-599">One or more parameters are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-600">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-600">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-601">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-601">The call was successful.</span></span>  <br/> |
   
#### <a name="ilsceventgetwebpath"></a><span data-ttu-id="b0332-602">ILSCEvent:: GetWebPath</span><span class="sxs-lookup"><span data-stu-id="b0332-602">ILSCEvent::GetWebPath</span></span>

<span data-ttu-id="b0332-603">仅当事件的[枚举 LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType)为 LSCEventType_OnFilePathConflict 时, 才会填充此值。</span><span class="sxs-lookup"><span data-stu-id="b0332-603">This value is only populated when the [Enum LSCEventType](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventType) of the event is LSCEventType_OnFilePathConflict.</span></span> 
  
`HRESULT ILSCEvent::GetWebPath ([out] BSTR * pbstrWebPath)`

##### <a name="parameters"></a><span data-ttu-id="b0332-604">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-604">Parameters</span></span>

 <span data-ttu-id="b0332-605">_pbstrWebPath_</span><span class="sxs-lookup"><span data-stu-id="b0332-605">_pbstrWebPath_</span></span>
  
<span data-ttu-id="b0332-606">指定与此事件关联的 Web 路径。</span><span class="sxs-lookup"><span data-stu-id="b0332-606">Specifies the Web Path associated with this event.</span></span> <span data-ttu-id="b0332-607">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-607">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-608">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-608">Return values</span></span>

<span data-ttu-id="b0332-609">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-609">Always returns S_OK.</span></span> 
  
### <a name="interface-ilscevent2"></a><span data-ttu-id="b0332-610">接口 ILSCEvent2</span><span class="sxs-lookup"><span data-stu-id="b0332-610">Interface ILSCEvent2</span></span>

<span data-ttu-id="b0332-611">此接口保存有关同步事件的其他信息。</span><span class="sxs-lookup"><span data-stu-id="b0332-611">This interface holds additional information about a synchronizing event.</span></span>
  
<span data-ttu-id="b0332-612">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0332-612">**Public member functions**</span></span>

#### <a name="ilscevent2geterrorchain"></a><span data-ttu-id="b0332-613">ILSCEvent2:: GetErrorChain</span><span class="sxs-lookup"><span data-stu-id="b0332-613">ILSCEvent2::GetErrorChain</span></span>

<span data-ttu-id="b0332-614">获取有关同步事件的错误链信息。</span><span class="sxs-lookup"><span data-stu-id="b0332-614">Gets the error chain information about a synchronizing event.</span></span>
  
`HRESULT ILSCEvent2::GetErrorChain ([out] BSTR * pbstrErrorChain)`

##### <a name="parameters"></a><span data-ttu-id="b0332-615">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-615">Parameters</span></span>

 <span data-ttu-id="b0332-616">_pbstrErrorChain_</span><span class="sxs-lookup"><span data-stu-id="b0332-616">_pbstrErrorChain_</span></span>
  
<span data-ttu-id="b0332-617">一个用于保存错误链信息的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0332-617">A string to hold the error chain information.</span></span> <span data-ttu-id="b0332-618">不得为 null。</span><span class="sxs-lookup"><span data-stu-id="b0332-618">Must not be null.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-619">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-619">Return values</span></span>

|<span data-ttu-id="b0332-620">值</span><span class="sxs-lookup"><span data-stu-id="b0332-620">Value</span></span>|<span data-ttu-id="b0332-621">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-621">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-622">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="b0332-622">E_NOTIMPL</span></span>  <br/> |<span data-ttu-id="b0332-623">安装的 Office 版本不支持此接口</span><span class="sxs-lookup"><span data-stu-id="b0332-623">The installed version of Office does not support this interface</span></span>  <br/> |
|<span data-ttu-id="b0332-624">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b0332-624">E_INVALIDARG</span></span>  <br/> |<span data-ttu-id="b0332-625">一个或多个参数值无效。</span><span class="sxs-lookup"><span data-stu-id="b0332-625">One or more of the parameter values are invalid.</span></span>  <br/> |
|<span data-ttu-id="b0332-626">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0332-626">E_FAIL</span></span>  <br/> |<span data-ttu-id="b0332-627">错误链信息不可用。</span><span class="sxs-lookup"><span data-stu-id="b0332-627">The error chain information is not available.</span></span>  <br/> |
|<span data-ttu-id="b0332-628">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0332-628">S_OK</span></span>  <br/> |<span data-ttu-id="b0332-629">调用成功。</span><span class="sxs-lookup"><span data-stu-id="b0332-629">The call was successful.</span></span>  <br/> |
   
### <a name="interface-ipartneractivitycallback"></a><span data-ttu-id="b0332-630">接口 IPartnerActivityCallback</span><span class="sxs-lookup"><span data-stu-id="b0332-630">Interface IPartnerActivityCallback</span></span>

<span data-ttu-id="b0332-631">此接口提供对 CSISyncClient COM 对象的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b0332-631">This interface provides a callback function to the CSISyncClient COM object.</span></span>
  
<span data-ttu-id="b0332-632">**公共成员函数**</span><span class="sxs-lookup"><span data-stu-id="b0332-632">**Public member functions**</span></span>

#### <a name="ipartneractivitycallbackeventoccurred"></a><span data-ttu-id="b0332-633">IPartnerActivityCallback:: EventOccurred</span><span class="sxs-lookup"><span data-stu-id="b0332-633">IPartnerActivityCallback::EventOccurred</span></span>

<span data-ttu-id="b0332-634">这是给定给 CsiSyncClient COM 对象的对象上的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b0332-634">This is a callback function on the object given to the CsiSyncClient COM object.</span></span> <span data-ttu-id="b0332-635">当事件发生时 (请参阅[Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid 事件类型), CsiSyncClient COM 对象将调用此方法, 以信令使用者。</span><span class="sxs-lookup"><span data-stu-id="b0332-635">It's expected that when an Event occurs (see [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid event types), the CsiSyncClient COM object will call this method, signalling the consumer.</span></span> 
  
`HRESULT IPartnerActivityCallback::EventOccurred ([in] LSCEventTypeOccurred eEventTypeOccurred)`

##### <a name="parameters"></a><span data-ttu-id="b0332-636">参数</span><span class="sxs-lookup"><span data-stu-id="b0332-636">Parameters</span></span>

 <span data-ttu-id="b0332-637">_eEventTypeOccurred_</span><span class="sxs-lookup"><span data-stu-id="b0332-637">_eEventTypeOccurred_</span></span>
  
<span data-ttu-id="b0332-638">此事件的事件类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-638">The event type of this event.</span></span> <span data-ttu-id="b0332-639">有关有效值, 请参阅[Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) 。</span><span class="sxs-lookup"><span data-stu-id="b0332-639">See [Enum LSCEventTypeOccurred](using-csisyncclient-to-control-the-office-document-cache-odc.md#Enum_LSCEventTypeOccurred) for valid values.</span></span> 
  
##### <a name="return-values"></a><span data-ttu-id="b0332-640">返回值</span><span class="sxs-lookup"><span data-stu-id="b0332-640">Return values</span></span>

<span data-ttu-id="b0332-641">始终返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="b0332-641">Always returns S_OK.</span></span>
  
## <a name="enumerations"></a><span data-ttu-id="b0332-642">枚举</span><span class="sxs-lookup"><span data-stu-id="b0332-642">Enumerations</span></span>

<span data-ttu-id="b0332-643">CSISyncClient 使用以下枚举。</span><span class="sxs-lookup"><span data-stu-id="b0332-643">CSISyncClient uses the following enumerations.</span></span>
  
### <a name="enum-lsceventsyncerrortype"></a><span data-ttu-id="b0332-644">枚举 LSCEventSyncErrorType</span><span class="sxs-lookup"><span data-stu-id="b0332-644">Enum LSCEventSyncErrorType</span></span>
<span data-ttu-id="b0332-645"><a name="Enum_LSCEventSyncErrorType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-645"></span></span>

<span data-ttu-id="b0332-646">此枚举指定同步文件时可能发生的错误类别。</span><span class="sxs-lookup"><span data-stu-id="b0332-646">This enumeration specifies the categories of errors that can occur while synchronizing a file.</span></span>
  
|<span data-ttu-id="b0332-647">枚举器重</span><span class="sxs-lookup"><span data-stu-id="b0332-647">Enumerator</span></span>|<span data-ttu-id="b0332-648">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-648">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span><span class="sxs-lookup"><span data-stu-id="b0332-649">LSCEventSyncErrorType_UserInterventionRequiredUnexpected</span></span>  <br/> |<span data-ttu-id="b0332-650">此事件的同步错误是意外的, 可能需要特别注意。</span><span class="sxs-lookup"><span data-stu-id="b0332-650">The synchronizing error of this event was unexpected, and may require special consideration.</span></span> <span data-ttu-id="b0332-651">默认情况下, 用户可能需要干预。</span><span class="sxs-lookup"><span data-stu-id="b0332-651">By default, the user may have to intervene.</span></span>  <br/> |
|<span data-ttu-id="b0332-652">LSCEventSyncErrorType_NoInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0332-652">LSCEventSyncErrorType_NoInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0332-653">此事件的同步错误不需要特别考虑。</span><span class="sxs-lookup"><span data-stu-id="b0332-653">The synchronizing error of this event does not need special consideration.</span></span> <span data-ttu-id="b0332-654">Office 将自动处理它。</span><span class="sxs-lookup"><span data-stu-id="b0332-654">Office will handle it automatically.</span></span>  <br/> |
|<span data-ttu-id="b0332-655">LSCEventSyncErrorType_UserInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0332-655">LSCEventSyncErrorType_UserInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0332-656">此事件的同步错误要求用户对其进行解析。</span><span class="sxs-lookup"><span data-stu-id="b0332-656">The synchronizing error of this event requires a user to resolve it.</span></span> <span data-ttu-id="b0332-657">例如, 合并冲突错误要求用户打开并合并文档。</span><span class="sxs-lookup"><span data-stu-id="b0332-657">For example, merge conflict error requires a user to open the document and merge it.</span></span>  <br/> |
|<span data-ttu-id="b0332-658">LSCEventSyncErrorType_WaitingOnClient</span><span class="sxs-lookup"><span data-stu-id="b0332-658">LSCEventSyncErrorType_WaitingOnClient</span></span>  <br/> |<span data-ttu-id="b0332-659">此事件的同步错误需要使用者干预, 但用户不需要特别注意。</span><span class="sxs-lookup"><span data-stu-id="b0332-659">The synchronizing error of this event requires the consumer to intervene, but should not require special consideration by the user.</span></span>  <br/> |
|<span data-ttu-id="b0332-660">LSCEventSyncErrorType_ClientInterventionRequired</span><span class="sxs-lookup"><span data-stu-id="b0332-660">LSCEventSyncErrorType_ClientInterventionRequired</span></span>  <br/> |<span data-ttu-id="b0332-661">此事件的同步错误要求使用者干预为特殊情况。</span><span class="sxs-lookup"><span data-stu-id="b0332-661">The synchronizing error of this event requires the consumer to intervene as a special case.</span></span>  <br/> |
|<span data-ttu-id="b0332-662">LSCEventSyncErrorType_Max</span><span class="sxs-lookup"><span data-stu-id="b0332-662">LSCEventSyncErrorType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtype"></a><span data-ttu-id="b0332-663">枚举 LSCEventType</span><span class="sxs-lookup"><span data-stu-id="b0332-663">Enum LSCEventType</span></span>
<span data-ttu-id="b0332-664"><a name="Enum_LSCEventType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-664"></span></span>

<span data-ttu-id="b0332-665">此枚举指定可对特定文件发生的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-665">This enumeration specifies the type of events that can occur for a particular file.</span></span>
  
|<span data-ttu-id="b0332-666">枚举器重</span><span class="sxs-lookup"><span data-stu-id="b0332-666">Enumerator</span></span>|<span data-ttu-id="b0332-667">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-667">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-668">LSCEventType_None</span><span class="sxs-lookup"><span data-stu-id="b0332-668">LSCEventType_None</span></span>  <br/> ||
|<span data-ttu-id="b0332-669">LSCEventType_OnLocalChanges</span><span class="sxs-lookup"><span data-stu-id="b0332-669">LSCEventType_OnLocalChanges</span></span>  <br/> |<span data-ttu-id="b0332-670">对本地文件进行了更改。</span><span class="sxs-lookup"><span data-stu-id="b0332-670">Changes were made to a local file.</span></span>  <br/> |
|<span data-ttu-id="b0332-671">LSCEventType_OnOpenedByUser</span><span class="sxs-lookup"><span data-stu-id="b0332-671">LSCEventType_OnOpenedByUser</span></span>  <br/> |<span data-ttu-id="b0332-672">用户打开了文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-672">A user opened a file.</span></span>  <br/> |
|<span data-ttu-id="b0332-673">LSCEventType_OnServerChangesDownloaded</span><span class="sxs-lookup"><span data-stu-id="b0332-673">LSCEventType_OnServerChangesDownloaded</span></span>  <br/> |<span data-ttu-id="b0332-674">从服务器下载文件更改已完成。</span><span class="sxs-lookup"><span data-stu-id="b0332-674">Finished downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="b0332-675">LSCEventType_OnLocalChangesUploaded</span><span class="sxs-lookup"><span data-stu-id="b0332-675">LSCEventType_OnLocalChangesUploaded</span></span>  <br/> |<span data-ttu-id="b0332-676">完成将文件更改上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="b0332-676">Finished uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="b0332-677">LSCEventType_OnLocalConflictStateChanged</span><span class="sxs-lookup"><span data-stu-id="b0332-677">LSCEventType_OnLocalConflictStateChanged</span></span>  <br/> |<span data-ttu-id="b0332-678">文件的合并冲突状态已更改。</span><span class="sxs-lookup"><span data-stu-id="b0332-678">The merge conflict state of a file has changed.</span></span>  <br/> |
|<span data-ttu-id="b0332-679">LSCEventType_OnFileAdded</span><span class="sxs-lookup"><span data-stu-id="b0332-679">LSCEventType_OnFileAdded</span></span>  <br/> |<span data-ttu-id="b0332-680">添加了一个文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-680">A file was added.</span></span>  <br/> |
|<span data-ttu-id="b0332-681">LSCEventType_OnFileDeleted</span><span class="sxs-lookup"><span data-stu-id="b0332-681">LSCEventType_OnFileDeleted</span></span>  <br/> |<span data-ttu-id="b0332-682">删除了一个文件。</span><span class="sxs-lookup"><span data-stu-id="b0332-682">A file was deleted.</span></span>  <br/> |
|<span data-ttu-id="b0332-683">LSCEventType_OnSyncEnabled</span><span class="sxs-lookup"><span data-stu-id="b0332-683">LSCEventType_OnSyncEnabled</span></span>  <br/> |<span data-ttu-id="b0332-684">对用户文件启用了同步。</span><span class="sxs-lookup"><span data-stu-id="b0332-684">Synchronizing was enabled for a user's files.</span></span>  <br/> |
|<span data-ttu-id="b0332-685">LSCEventType_OnServerChangesDownloadStarted</span><span class="sxs-lookup"><span data-stu-id="b0332-685">LSCEventType_OnServerChangesDownloadStarted</span></span>  <br/> |<span data-ttu-id="b0332-686">已开始从服务器下载文件更改。</span><span class="sxs-lookup"><span data-stu-id="b0332-686">Started downloading file changes from the server.</span></span>  <br/> |
|<span data-ttu-id="b0332-687">LSCEventType_OnLocalChangesUploadStarted</span><span class="sxs-lookup"><span data-stu-id="b0332-687">LSCEventType_OnLocalChangesUploadStarted</span></span>  <br/> |<span data-ttu-id="b0332-688">已开始将文件更改上载到服务器。</span><span class="sxs-lookup"><span data-stu-id="b0332-688">Started uploading file changes to the server.</span></span>  <br/> |
|<span data-ttu-id="b0332-689">LSCEventType_OnFilePathConflict</span><span class="sxs-lookup"><span data-stu-id="b0332-689">LSCEventType_OnFilePathConflict</span></span>  <br/> |<span data-ttu-id="b0332-690">当调用[ILSCLocalSyncClient:: LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange)、 [ILSCLocalSyncClient:: ServerFileChange](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange)或[ILSCLocalSyncClient:: RenameFile](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile)导致 Web 路径或本地路径与另一个文件中的其他文件发生冲突时, 会生成此事件。Office 文件缓存。</span><span class="sxs-lookup"><span data-stu-id="b0332-690">This event is generated when a call to [ILSCLocalSyncClient::LocalFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_LocalFileChange), [ILSCLocalSyncClient::ServerFileChange ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_ServerFileChange), or [ILSCLocalSyncClient::RenameFile ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_RenameFile) causes a Web Path or Local Path collision with another file in the Office file cache.</span></span>  <br/> |
|<span data-ttu-id="b0332-691">LSCEventType_OnFileForked</span><span class="sxs-lookup"><span data-stu-id="b0332-691">LSCEventType_OnFileForked</span></span>  <br/> ||
|<span data-ttu-id="b0332-692">LSCEventType_Max</span><span class="sxs-lookup"><span data-stu-id="b0332-692">LSCEventType_Max</span></span>  <br/> ||
   
### <a name="enum-lsceventtypeoccurred"></a><span data-ttu-id="b0332-693">枚举 LSCEventTypeOccurred</span><span class="sxs-lookup"><span data-stu-id="b0332-693">Enum LSCEventTypeOccurred</span></span>
<span data-ttu-id="b0332-694"><a name="Enum_LSCEventTypeOccurred"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-694"></span></span>

<span data-ttu-id="b0332-695">此枚举指定可能发生的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="b0332-695">This enumeration specifies the type of events that can occur.</span></span> <span data-ttu-id="b0332-696">使用者需要根据事件类型调用特定的 ILSCLocalSyncClient 函数。</span><span class="sxs-lookup"><span data-stu-id="b0332-696">The consumer needs to call specific ILSCLocalSyncClient functions based on the event type.</span></span>
  
|<span data-ttu-id="b0332-697">枚举器重</span><span class="sxs-lookup"><span data-stu-id="b0332-697">Enumerator</span></span>|<span data-ttu-id="b0332-698">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-698">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-699">LSCEventTypeOccurred_GetChanges</span><span class="sxs-lookup"><span data-stu-id="b0332-699">LSCEventTypeOccurred_GetChanges</span></span>  <br/> |<span data-ttu-id="b0332-700">发生了 ILSCEvent。</span><span class="sxs-lookup"><span data-stu-id="b0332-700">An ILSCEvent has occurred.</span></span> <span data-ttu-id="b0332-701">使用者应调用[ILSCLocalSyncClient:: GetChanges](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges)以检索数据。</span><span class="sxs-lookup"><span data-stu-id="b0332-701">The consumer should call [ILSCLocalSyncClient::GetChanges ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetChanges) to retrieve the data.</span></span>  <br/> |
|<span data-ttu-id="b0332-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span><span class="sxs-lookup"><span data-stu-id="b0332-702">LSCEventTypeOccurred_GetSupportedFileExtensions</span></span>  <br/> |<span data-ttu-id="b0332-703">支持的文件扩展名已更改。</span><span class="sxs-lookup"><span data-stu-id="b0332-703">The supported file extensions have changed.</span></span> <span data-ttu-id="b0332-704">使用者应调用[ILSCLocalSyncClient:: GetSupportedFileExtensions](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions)以检索支持的扩展的新列表。</span><span class="sxs-lookup"><span data-stu-id="b0332-704">The consumer should call [ILSCLocalSyncClient::GetSupportedFileExtensions ](using-csisyncclient-to-control-the-office-document-cache-odc.md#ILSCLocalSyncClient_GetSupportedFileExtensions) to retrieve the new list of supported extensions.</span></span>  <br/> |
   
### <a name="enum-lscnetworksyncpermissiontype"></a><span data-ttu-id="b0332-705">枚举 LSCNetworkSyncPermissionType</span><span class="sxs-lookup"><span data-stu-id="b0332-705">Enum LSCNetworkSyncPermissionType</span></span>
<span data-ttu-id="b0332-706"><a name="Enum_LSCNetworkSyncPermissionType"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-706"></span></span>

<span data-ttu-id="b0332-707">此枚举指定用于网络成本启发式的标志。</span><span class="sxs-lookup"><span data-stu-id="b0332-707">This enumeration specifies the flags used for a network cost heuristic.</span></span> 

|<span data-ttu-id="b0332-708">枚举器重</span><span class="sxs-lookup"><span data-stu-id="b0332-708">Enumerator</span></span>|<span data-ttu-id="b0332-709">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-709">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-710">LSCNetworkSyncPermissionType_HighCost</span><span class="sxs-lookup"><span data-stu-id="b0332-710">LSCNetworkSyncPermissionType_HighCost</span></span>  <br/> |<span data-ttu-id="b0332-711">如此如果重写昂贵网络 (如 3g) 的成本试探法。</span><span class="sxs-lookup"><span data-stu-id="b0332-711">True if the cost heuristic for expensive networks (such as 3G) is overridden.</span></span>  <br/> |
|<span data-ttu-id="b0332-712">LSCNetworkSyncPermissionType_HighPowerUsage</span><span class="sxs-lookup"><span data-stu-id="b0332-712">LSCNetworkSyncPermissionType_HighPowerUsage</span></span>  <br/> |<span data-ttu-id="b0332-713">如此如果重写了电源使用的成本试探法 (如电池)。</span><span class="sxs-lookup"><span data-stu-id="b0332-713">True if the cost heuristic for power usage (such as a battery) is overridden.</span></span>  <br/> |
   
### <a name="enum-lscstatusflag"></a><span data-ttu-id="b0332-714">枚举 LSCStatusFlag</span><span class="sxs-lookup"><span data-stu-id="b0332-714">Enum LSCStatusFlag</span></span>
<span data-ttu-id="b0332-715"><a name="Enum_LSCStatusFlag"> </a></span><span class="sxs-lookup"><span data-stu-id="b0332-715"></span></span>

<span data-ttu-id="b0332-716">此枚举用于表示文件的同步状态。</span><span class="sxs-lookup"><span data-stu-id="b0332-716">This enumeration is used to represent the synchronize status of a file.</span></span> 
  
|<span data-ttu-id="b0332-717">枚举器重</span><span class="sxs-lookup"><span data-stu-id="b0332-717">Enumerator</span></span>|<span data-ttu-id="b0332-718">说明</span><span class="sxs-lookup"><span data-stu-id="b0332-718">Description</span></span>|
|:-----|:-----|
|<span data-ttu-id="b0332-719">LCSStatusFlag_None</span><span class="sxs-lookup"><span data-stu-id="b0332-719">LCSStatusFlag_None</span></span>  <br/> ||
|<span data-ttu-id="b0332-720">LSCStatusFlag_UploadPending</span><span class="sxs-lookup"><span data-stu-id="b0332-720">LSCStatusFlag_UploadPending</span></span>  <br/> |<span data-ttu-id="b0332-721">如果有要发送到服务器文件的挂起数据, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="b0332-721">True if there is pending data to send to the server file.</span></span>  <br/> |
|<span data-ttu-id="b0332-722">LSCStatusFlag_DownloadPending</span><span class="sxs-lookup"><span data-stu-id="b0332-722">LSCStatusFlag_DownloadPending</span></span>  <br/> |<span data-ttu-id="b0332-723">如果有要从服务器文件中下载的挂起数据, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="b0332-723">True if there is pending data to download from the server file.</span></span>  <br/> |
|<span data-ttu-id="b0332-724">LSCStatusFlag_LocalFileUnchanged</span><span class="sxs-lookup"><span data-stu-id="b0332-724">LSCStatusFlag_LocalFileUnchanged</span></span>  <br/> |<span data-ttu-id="b0332-725">如此如果数据办公室的缓存中的文件是磁盘上的最新数据副本。</span><span class="sxs-lookup"><span data-stu-id="b0332-725">True if the data Office has on the file in its cache is the most recent copy of the data on disk.</span></span>  <br/> |
   

