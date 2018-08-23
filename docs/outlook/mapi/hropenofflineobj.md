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
ms.openlocfilehash: cc71974d841005785932cc9017d44c3c0614687d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563385"
---
# <a name="hropenofflineobj"></a><span data-ttu-id="6d6ac-103">HrOpenOfflineObj</span><span class="sxs-lookup"><span data-stu-id="6d6ac-103">HrOpenOfflineObj</span></span>

  
  
<span data-ttu-id="6d6ac-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6d6ac-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6d6ac-105">打开基于给定配置文件的脱机对象。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-105">Opens an offline object based on a given profile.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="6d6ac-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="6d6ac-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="6d6ac-107">导出：</span><span class="sxs-lookup"><span data-stu-id="6d6ac-107">Exported by:</span></span>  <br/> |<span data-ttu-id="6d6ac-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="6d6ac-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="6d6ac-109">调用：</span><span class="sxs-lookup"><span data-stu-id="6d6ac-109">Called by:</span></span>  <br/> |<span data-ttu-id="6d6ac-110">客户端</span><span class="sxs-lookup"><span data-stu-id="6d6ac-110">Client</span></span>  <br/> |
|<span data-ttu-id="6d6ac-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="6d6ac-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="6d6ac-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="6d6ac-112">Outlook</span></span>  <br/> |
   
```cpp
typedef HRESULT (STDMETHODCALLTYPE HROPENOFFLINEOBJ)( 
      ULONG ulReserved, 
      LPCWSTR pwszProfileNameIn, 
      const GUID* pGUID, 
      const GUID* pReserved, 
      IMAPIOfflineMgr** ppOfflineObj); 

```

## <a name="parameters"></a><span data-ttu-id="6d6ac-113">参数</span><span class="sxs-lookup"><span data-stu-id="6d6ac-113">Parameters</span></span>

 <span data-ttu-id="6d6ac-114">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="6d6ac-114">_ulReserved_</span></span>
  
> <span data-ttu-id="6d6ac-115">[in]不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-115">[in] This parameter is not used.</span></span> <span data-ttu-id="6d6ac-116">它必须是 0。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-116">It must be 0.</span></span>
    
 <span data-ttu-id="6d6ac-117">_pwszProfileNameIn_</span><span class="sxs-lookup"><span data-stu-id="6d6ac-117">_pwszProfileNameIn_</span></span>
  
> <span data-ttu-id="6d6ac-118">[in]脱机对象为配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-118">[in] The name of the profile that the offline object is for.</span></span> <span data-ttu-id="6d6ac-119">它必须在 Unicode 中表示。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-119">It must be expressed in Unicode.</span></span> 
    
 <span data-ttu-id="6d6ac-120">_pGUID_</span><span class="sxs-lookup"><span data-stu-id="6d6ac-120">_pGUID_</span></span>
  
> <span data-ttu-id="6d6ac-121">[in]为 GUID 可用于唯一标识此对象从其他脱机对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-121">[in] Pointer to a GUID which can be used to uniquely identify this object from other offline objects.</span></span> <span data-ttu-id="6d6ac-122">它必须是**GUID_GlobalState**。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-122">It must be **GUID_GlobalState**.</span></span>
    
 <span data-ttu-id="6d6ac-123">_保留_</span><span class="sxs-lookup"><span data-stu-id="6d6ac-123">_pReserved_</span></span>
  
> <span data-ttu-id="6d6ac-124">[in]不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-124">[in] This parameter is not used.</span></span> <span data-ttu-id="6d6ac-125">它必须是**null**。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-125">It must be **null**.</span></span>
    
 <span data-ttu-id="6d6ac-126">_ppOfflineObj_</span><span class="sxs-lookup"><span data-stu-id="6d6ac-126">_ppOfflineObj_</span></span>
  
> <span data-ttu-id="6d6ac-127">[输出]指向所需的脱机对象的指针。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-127">[out] A pointer to the requested offline object.</span></span> <span data-ttu-id="6d6ac-128">呼叫者可以使用此指针访问[IMAPIOfflineMgr: IMAPIOffline](imapiofflinemgrimapioffline.md)找到此对象支持的回调并为其设置回调的接口。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-128">The caller can use this pointer to access the [IMAPIOfflineMgr : IMAPIOffline](imapiofflinemgrimapioffline.md) interface to find the callbacks that this object supports and to set up callbacks for it.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="6d6ac-129">返回值</span><span class="sxs-lookup"><span data-stu-id="6d6ac-129">Return values</span></span>

<span data-ttu-id="6d6ac-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="6d6ac-130">S_OK</span></span> 
  
- <span data-ttu-id="6d6ac-131">成功函数调用。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-131">The function call is successful.</span></span>
    
<span data-ttu-id="6d6ac-132">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6d6ac-132">MAPI_E_NOT_FOUND</span></span>
  
- <span data-ttu-id="6d6ac-133">函数调用失败。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-133">The function call failed.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6d6ac-134">注解</span><span class="sxs-lookup"><span data-stu-id="6d6ac-134">Remarks</span></span>

<span data-ttu-id="6d6ac-135">这是客户端发出时在客户端需要的任何给定配置文件的连接状态更改通知的第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-135">This is the first call that a client makes when the client wants to be notified of any connection state changes for a given profile.</span></span> <span data-ttu-id="6d6ac-136">时调用**HrOpenOfflineObj**，客户端获取脱机支持**IMAPIOfflineMgr**的对象。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-136">Upon calling **HrOpenOfflineObj**, the client obtains an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="6d6ac-137">客户端可以检查回调对象 （通过使用[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)） 支持的类型，然后设置回调 （通过使用[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)）。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-137">The client can check for the kinds of callbacks supported by the object (by using [IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)), and then set up callbacks for it (by using [IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)).</span></span>
  
<span data-ttu-id="6d6ac-138">当使用[GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx)查找 msmapi32.dll 中此函数的地址，指定**HrOpenOfflineObj@20**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-138">When using [GetProcAddress](http://msdn.microsoft.com/en-us/library/ms683212.aspx) to look for the address of this function in msmapi32.dll, specify **HrOpenOfflineObj@20** as the procedure name.</span></span> 
  
 <span data-ttu-id="6d6ac-139">**HrOpenOfflineObj**仅适用于客户端的 COM 加载项，并在 Outlook 进程内运行的 Exchange 客户端扩展 MAPI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-139">**HrOpenOfflineObj** only works for clients that are MAPI providers, COM Add-Ins, and Exchange Client Extensions running inside the Outlook process.</span></span> <span data-ttu-id="6d6ac-140">否则， **HrOpenOfflineObj**返回**MAPI_E_NOT_FOUND**。</span><span class="sxs-lookup"><span data-stu-id="6d6ac-140">Otherwise, **HrOpenOfflineObj** returns **MAPI_E_NOT_FOUND**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6d6ac-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d6ac-141">See also</span></span>



[<span data-ttu-id="6d6ac-142">IMAPIOffline : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6d6ac-142">IMAPIOffline : IUnknown</span></span>](imapiofflineiunknown.md)
  
[<span data-ttu-id="6d6ac-143">IMAPIOfflineMgr : IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="6d6ac-143">IMAPIOfflineMgr : IMAPIOffline</span></span>](imapiofflinemgrimapioffline.md)


[<span data-ttu-id="6d6ac-144">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="6d6ac-144">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="6d6ac-145">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6d6ac-145">MAPI Constants</span></span>](mapi-constants.md)

