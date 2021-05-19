---
title: HrOpenOfflineObj
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- HrOpenOfflineObj
api_type:
- HeaderDef
ms.assetid: cee1a940-fe01-d364-5d7c-c9e9dfeb8979
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ef929bf778fabc4350f553d185838dd5cb2cf0b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32347745"
---
# <a name="hropenofflineobj"></a><span data-ttu-id="d416d-103">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="d416d-103">HrOpenOfflineObj</span></span>

  
  
<span data-ttu-id="d416d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d416d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d416d-105">打开基于给定配置文件的脱机对象。</span><span class="sxs-lookup"><span data-stu-id="d416d-105">Opens an offline object based on a given profile.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="d416d-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="d416d-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="d416d-107">导出者：</span><span class="sxs-lookup"><span data-stu-id="d416d-107">Exported by:</span></span>  <br/> |<span data-ttu-id="d416d-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="d416d-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="d416d-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="d416d-109">Called by:</span></span>  <br/> |<span data-ttu-id="d416d-110">客户端</span><span class="sxs-lookup"><span data-stu-id="d416d-110">Client</span></span>  <br/> |
|<span data-ttu-id="d416d-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="d416d-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="d416d-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="d416d-112">Outlook</span></span>  <br/> |
   
```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
      ULONG ulReserved, 
      LPCWSTR pwszProfileNameIn, 
      const GUID* pGUID, 
      const GUID* pReserved, 
      IMAPIOfflineMgr** ppOfflineObj); 

```

## <a name="parameters"></a><span data-ttu-id="d416d-113">参数</span><span class="sxs-lookup"><span data-stu-id="d416d-113">Parameters</span></span>

 <span data-ttu-id="d416d-114">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="d416d-114">_ulReserved_</span></span>
  
> <span data-ttu-id="d416d-115">[in]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="d416d-115">[in] This parameter is not used.</span></span> <span data-ttu-id="d416d-116">它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="d416d-116">It must be 0.</span></span>
    
 <span data-ttu-id="d416d-117">_pwszProfileNameIn_</span><span class="sxs-lookup"><span data-stu-id="d416d-117">_pwszProfileNameIn_</span></span>
  
> <span data-ttu-id="d416d-118">[in]脱机对象所针对的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d416d-118">[in] The name of the profile that the offline object is for.</span></span> <span data-ttu-id="d416d-119">它必须用 Unicode 表示。</span><span class="sxs-lookup"><span data-stu-id="d416d-119">It must be expressed in Unicode.</span></span> 
    
 <span data-ttu-id="d416d-120">_pGUID_</span><span class="sxs-lookup"><span data-stu-id="d416d-120">_pGUID_</span></span>
  
> <span data-ttu-id="d416d-121">[in]指向可用于从其他脱机对象唯一标识此对象的 GUID 的指针。</span><span class="sxs-lookup"><span data-stu-id="d416d-121">[in] Pointer to a GUID which can be used to uniquely identify this object from other offline objects.</span></span> <span data-ttu-id="d416d-122">它必须是 **GUID_GlobalState**。</span><span class="sxs-lookup"><span data-stu-id="d416d-122">It must be **GUID_GlobalState**.</span></span>
    
 <span data-ttu-id="d416d-123">_pReserved_</span><span class="sxs-lookup"><span data-stu-id="d416d-123">_pReserved_</span></span>
  
> <span data-ttu-id="d416d-124">[in]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="d416d-124">[in] This parameter is not used.</span></span> <span data-ttu-id="d416d-125">它必须为 **null**。</span><span class="sxs-lookup"><span data-stu-id="d416d-125">It must be **null**.</span></span>
    
 <span data-ttu-id="d416d-126">_ppOfflineObj_</span><span class="sxs-lookup"><span data-stu-id="d416d-126">_ppOfflineObj_</span></span>
  
> <span data-ttu-id="d416d-127">[out]指向请求的脱机对象的指针。</span><span class="sxs-lookup"><span data-stu-id="d416d-127">[out] A pointer to the requested offline object.</span></span> <span data-ttu-id="d416d-128">调用方可以使用此指针访问 [IMAPIOfflineMgr ： IMAPIOffline](imapiofflinemgrimapioffline.md) 接口，以查找此对象支持的回调并设置其回调。</span><span class="sxs-lookup"><span data-stu-id="d416d-128">The caller can use this pointer to access the [IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md) interface to find the callbacks that this object supports and to set up callbacks for it.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="d416d-129">返回值</span><span class="sxs-lookup"><span data-stu-id="d416d-129">Return values</span></span>

<span data-ttu-id="d416d-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="d416d-130">S_OK</span></span> 
  
- <span data-ttu-id="d416d-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d416d-131">The function call is successful.</span></span>
    
<span data-ttu-id="d416d-132">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="d416d-132">MAPI_E_NOT_FOUND</span></span>
  
- <span data-ttu-id="d416d-133">函数调用失败。</span><span class="sxs-lookup"><span data-stu-id="d416d-133">The function call failed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d416d-134">备注</span><span class="sxs-lookup"><span data-stu-id="d416d-134">Remarks</span></span>

<span data-ttu-id="d416d-135">这是客户端在客户端希望收到给定配置文件的任何连接状态更改通知时进行的第一个调用。</span><span class="sxs-lookup"><span data-stu-id="d416d-135">This is the first call that a client makes when the client wants to be notified of any connection state changes for a given profile.</span></span> <span data-ttu-id="d416d-136">调用 **HrOpenOfflineObj** 时，客户端获取支持 **IMAPIOfflineMgr** 的脱机对象。</span><span class="sxs-lookup"><span data-stu-id="d416d-136">Upon calling **HrOpenOfflineObj**, the client obtains an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="d416d-137">客户端可以使用 [IMAPIOffline：：GetCapabilities](imapioffline-getcapabilities.md)) 检查对象 (支持的回调类型，然后使用 [IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)) 为 (设置回调。</span><span class="sxs-lookup"><span data-stu-id="d416d-137">The client can check for the kinds of callbacks supported by the object (by using [IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)), and then set up callbacks for it (by using [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)).</span></span>
  
<span data-ttu-id="d416d-138">使用 [GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx) 在 msmapi32.dll 中查找此函数的地址时，HrOpenOfflineObj@20 **指定为过程** 名称。</span><span class="sxs-lookup"><span data-stu-id="d416d-138">When using [GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx) to look for the address of this function in msmapi32.dll, specify **HrOpenOfflineObj@20** as the procedure name.</span></span> 
  
 <span data-ttu-id="d416d-139">**HrOpenOfflineObj** 仅适用于 MAPI 提供程序、COM 加载项和 Exchange 进程内运行的客户端扩展Outlook客户端。</span><span class="sxs-lookup"><span data-stu-id="d416d-139">**HrOpenOfflineObj** only works for clients that are MAPI providers, COM Add-Ins, and Exchange Client Extensions running inside the Outlook process.</span></span> <span data-ttu-id="d416d-140">否则 **，HrOpenOfflineObj 将** 返回 **MAPI_E_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="d416d-140">Otherwise, **HrOpenOfflineObj** returns **MAPI_E_NOT_FOUND**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d416d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d416d-141">See also</span></span>



[<span data-ttu-id="d416d-142">IMAPIOffline : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d416d-142">IMAPIOffline : IUnknown</span></span>](imapiofflineiunknown.md)
  
[<span data-ttu-id="d416d-143">IMAPIOfflineMgr : IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="d416d-143">IMAPIOfflineMgr : IMAPIOffline</span></span>](imapiofflinemgrimapioffline.md)


[<span data-ttu-id="d416d-144">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="d416d-144">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="d416d-145">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="d416d-145">MAPI Constants</span></span>](mapi-constants.md)

