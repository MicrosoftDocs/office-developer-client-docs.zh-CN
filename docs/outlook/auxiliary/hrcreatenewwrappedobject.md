---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 在首选的字符格式中创建客户端可以访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384190"
---
# <a name="hrcreatenewwrappedobject"></a><span data-ttu-id="e7d91-103">HrCreateNewWrappedObject</span><span class="sxs-lookup"><span data-stu-id="e7d91-103">HrCreateNewWrappedObject</span></span>

<span data-ttu-id="e7d91-104">在首选的字符格式中创建客户端可以访问的对象。</span><span class="sxs-lookup"><span data-stu-id="e7d91-104">Creates an object that a client can access in a preferred character format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="e7d91-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="e7d91-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="e7d91-106">导出：</span><span class="sxs-lookup"><span data-stu-id="e7d91-106">Exported by:</span></span>  <br/> |<span data-ttu-id="e7d91-107">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="e7d91-107">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="e7d91-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="e7d91-108">Called by:</span></span>  <br/> |<span data-ttu-id="e7d91-109">客户端</span><span class="sxs-lookup"><span data-stu-id="e7d91-109">Client</span></span>  <br/> |
|<span data-ttu-id="e7d91-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="e7d91-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="e7d91-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="e7d91-111">Outlook</span></span>  <br/> |
   
```cpp
HRESULT HrCreateNewWrappedObject( 
    LPVOID        pvUnwrapped, 
    ULONG         ulUnwrappedFlags, 
    ULONG         ulWrappedFlags, 
    const IID     *pIID, 
    const ULONG   *pulReserved, 
    BOOL          fCheckWrap, 
    LPVOID       *ppvWrapped 
);

```

## <a name="parameters"></a><span data-ttu-id="e7d91-112">参数</span><span class="sxs-lookup"><span data-stu-id="e7d91-112">Parameters</span></span>

<span data-ttu-id="e7d91-113">_pvUnwrapped_</span><span class="sxs-lookup"><span data-stu-id="e7d91-113">_pvUnwrapped_</span></span>
  
> <span data-ttu-id="e7d91-114">[in]初始打开的 Outlook 对象。</span><span class="sxs-lookup"><span data-stu-id="e7d91-114">[in] The initial unwrapped Outlook object.</span></span> <span data-ttu-id="e7d91-115">必须实现以下接口之一：</span><span class="sxs-lookup"><span data-stu-id="e7d91-115">Must implement one of the following interfaces:</span></span>
    
   - <span data-ttu-id="e7d91-116">[IMailUser: IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx)， [IMAPIFolder: IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx)， [IMessage: IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx)， [IMsgStore: IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx)， [IMSLogon: IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx)，或[IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e7d91-116">[IMailUser : IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder : IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage : IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore : IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon : IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), or [IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).</span></span>
    
<span data-ttu-id="e7d91-117">_ulUnwrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="e7d91-117">_ulUnwrappedFlags_</span></span>
  
> <span data-ttu-id="e7d91-118">[in]代表已打开的初始对象的标志。</span><span class="sxs-lookup"><span data-stu-id="e7d91-118">[in] Flags that characterize the unwrapped initial object.</span></span> <span data-ttu-id="e7d91-119">必须是一个或多个下列值：</span><span class="sxs-lookup"><span data-stu-id="e7d91-119">Must be one or more of the following values:</span></span>
    
   - <span data-ttu-id="e7d91-120">DDLWRAP_FLAG_ANSI — Unwrapped 对象是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="e7d91-120">DDLWRAP_FLAG_ANSI—Unwrapped object is ANSI.</span></span>
    
   - <span data-ttu-id="e7d91-121">DDLWRAP_FLAG_UNICODE — Unwrapped 对象是 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="e7d91-121">DDLWRAP_FLAG_UNICODE—Unwrapped object is UNICODE.</span></span>
    
<span data-ttu-id="e7d91-122">_ulWrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="e7d91-122">_ulWrappedFlags_</span></span>
  
>  <span data-ttu-id="e7d91-123">[in]首选的字符格式的标志。</span><span class="sxs-lookup"><span data-stu-id="e7d91-123">[in] Flags for the preferred character format.</span></span> <span data-ttu-id="e7d91-124">必须是一个或多个下列值：</span><span class="sxs-lookup"><span data-stu-id="e7d91-124">Must be one or more of the following values:</span></span> 
    
   - <span data-ttu-id="e7d91-125">DDLWRAP_FLAG_ANSI — 将作为 ANSI 公开 Wrapped 对象。</span><span class="sxs-lookup"><span data-stu-id="e7d91-125">DDLWRAP_FLAG_ANSI—Wrapped object will be exposed as ANSI.</span></span>
    
   - <span data-ttu-id="e7d91-126">DDLWRAP_FLAG_UNICODE — Wrapped 对象将公开为 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="e7d91-126">DDLWRAP_FLAG_UNICODE—Wrapped object will be exposed as UNICODE.</span></span>
    
<span data-ttu-id="e7d91-127">_pIID_</span><span class="sxs-lookup"><span data-stu-id="e7d91-127">_pIID_</span></span>
  
>  <span data-ttu-id="e7d91-128">[in]已打开的对象; 所支持的接口的标识符将其设置为 NULL 如果这是未知。</span><span class="sxs-lookup"><span data-stu-id="e7d91-128">[in] The identifier of the interface supported by the unwrapped object; set it to NULL if this is unknown.</span></span> 
    
<span data-ttu-id="e7d91-129">_pulReserved_</span><span class="sxs-lookup"><span data-stu-id="e7d91-129">_pulReserved_</span></span>
  
>  <span data-ttu-id="e7d91-130">[in]不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="e7d91-130">[in] This parameter is not used.</span></span> <span data-ttu-id="e7d91-131">它必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e7d91-131">It must be NULL.</span></span> 
    
<span data-ttu-id="e7d91-132">_fCheckWrap_</span><span class="sxs-lookup"><span data-stu-id="e7d91-132">_fCheckWrap_</span></span>
  
>  <span data-ttu-id="e7d91-133">[in]将此参数设置为**true** ，如果_pvUnwrapped_应检查有之前换行; 其格式将其设置为**false**如果对象应自动换行不检查。</span><span class="sxs-lookup"><span data-stu-id="e7d91-133">[in] Set this parameter to **true** if  _pvUnwrapped_ should be checked for its format before wrapping; set it to **false** if the object should be wrapped without checking.</span></span> 
    
<span data-ttu-id="e7d91-134">_ppvWrapped_</span><span class="sxs-lookup"><span data-stu-id="e7d91-134">_ppvWrapped_</span></span>
  
>  <span data-ttu-id="e7d91-135">[输出]指向请求的对象，以请求的字符格式包装的指针。</span><span class="sxs-lookup"><span data-stu-id="e7d91-135">[out] A pointer to the requested object, wrapped in the requested character format.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="e7d91-136">返回值</span><span class="sxs-lookup"><span data-stu-id="e7d91-136">Return values</span></span>

<span data-ttu-id="e7d91-137">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="e7d91-137">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e7d91-138">注释</span><span class="sxs-lookup"><span data-stu-id="e7d91-138">Remarks</span></span>

<span data-ttu-id="e7d91-139">传入_fCheckWrap_将设置为**true**的被环绕对象将导致打开的对象。</span><span class="sxs-lookup"><span data-stu-id="e7d91-139">Passing in a wrapped object with  _fCheckWrap_ set to **true** will result in an unwrapped object.</span></span> <span data-ttu-id="e7d91-140">无论返回的对象自动换行，客户端负责释放在返回的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e7d91-140">Regardless of whether or not the returned object is wrapped, the client is responsible for releasing the reference on the returned object.</span></span> 
  
<span data-ttu-id="e7d91-141">当使用**GetProcAddress**查找 msmapi32.dll 中此函数的地址，指定**HrCreateNewWrappedObject@28**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="e7d91-141">When using **GetProcAddress** to look for the address of this function in msmapi32.dll, specify **HrCreateNewWrappedObject@28** as the procedure name.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e7d91-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7d91-142">See also</span></span>

- [<span data-ttu-id="e7d91-143">有关数据下降层 API</span><span class="sxs-lookup"><span data-stu-id="e7d91-143">About the Data Degradation Layer API</span></span>](about-the-data-degradation-layer-api.md)
- [<span data-ttu-id="e7d91-144">常量 （数据降级层 API）</span><span class="sxs-lookup"><span data-stu-id="e7d91-144">Constants (Data degradation layer API)</span></span>](constants-data-degradation-layer-api.md)

