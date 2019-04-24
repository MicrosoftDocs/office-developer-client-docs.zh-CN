---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 创建一个客户端可以以首选字符格式访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317603"
---
# <a name="hrcreatenewwrappedobject"></a><span data-ttu-id="4b69e-103">HrCreateNewWrappedObject</span><span class="sxs-lookup"><span data-stu-id="4b69e-103">HrCreateNewWrappedObject</span></span>

<span data-ttu-id="4b69e-104">创建一个客户端可以以首选字符格式访问的对象。</span><span class="sxs-lookup"><span data-stu-id="4b69e-104">Creates an object that a client can access in a preferred character format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="4b69e-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="4b69e-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="4b69e-106">导出者:</span><span class="sxs-lookup"><span data-stu-id="4b69e-106">Exported by:</span></span>  <br/> |<span data-ttu-id="4b69e-107">msmapi32</span><span class="sxs-lookup"><span data-stu-id="4b69e-107">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="4b69e-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="4b69e-108">Called by:</span></span>  <br/> |<span data-ttu-id="4b69e-109">客户端</span><span class="sxs-lookup"><span data-stu-id="4b69e-109">Client</span></span>  <br/> |
|<span data-ttu-id="4b69e-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="4b69e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4b69e-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="4b69e-111">Outlook</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="4b69e-112">参数</span><span class="sxs-lookup"><span data-stu-id="4b69e-112">Parameters</span></span>

<span data-ttu-id="4b69e-113">_pvUnwrapped_</span><span class="sxs-lookup"><span data-stu-id="4b69e-113">_pvUnwrapped_</span></span>
  
> <span data-ttu-id="4b69e-114">实时初始的已解包的 Outlook 对象。</span><span class="sxs-lookup"><span data-stu-id="4b69e-114">[in] The initial unwrapped Outlook object.</span></span> <span data-ttu-id="4b69e-115">必须实现以下接口之一:</span><span class="sxs-lookup"><span data-stu-id="4b69e-115">Must implement one of the following interfaces:</span></span>
    
   - <span data-ttu-id="4b69e-116">[IMailUser: IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder: IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage: IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore: IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon: IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), 或[IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4b69e-116">[IMailUser : IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder : IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage : IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore : IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon : IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), or [IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).</span></span>
    
<span data-ttu-id="4b69e-117">_ulUnwrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="4b69e-117">_ulUnwrappedFlags_</span></span>
  
> <span data-ttu-id="4b69e-118">实时用于表征已解开初始对象的标志。</span><span class="sxs-lookup"><span data-stu-id="4b69e-118">[in] Flags that characterize the unwrapped initial object.</span></span> <span data-ttu-id="4b69e-119">必须是下列值中的一个或多个:</span><span class="sxs-lookup"><span data-stu-id="4b69e-119">Must be one or more of the following values:</span></span>
    
   - <span data-ttu-id="4b69e-120">DDLWRAP_FLAG_ANSI —解包的对象是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="4b69e-120">DDLWRAP_FLAG_ANSI—Unwrapped object is ANSI.</span></span>
    
   - <span data-ttu-id="4b69e-121">DDLWRAP_FLAG_UNICODE —解包的对象是 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="4b69e-121">DDLWRAP_FLAG_UNICODE—Unwrapped object is UNICODE.</span></span>
    
<span data-ttu-id="4b69e-122">_ulWrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="4b69e-122">_ulWrappedFlags_</span></span>
  
>  <span data-ttu-id="4b69e-123">实时首选字符格式的标志。</span><span class="sxs-lookup"><span data-stu-id="4b69e-123">[in] Flags for the preferred character format.</span></span> <span data-ttu-id="4b69e-124">必须是下列值中的一个或多个:</span><span class="sxs-lookup"><span data-stu-id="4b69e-124">Must be one or more of the following values:</span></span> 
    
   - <span data-ttu-id="4b69e-125">DDLWRAP_FLAG_ANSI —包装的对象将作为 ANSI 公开。</span><span class="sxs-lookup"><span data-stu-id="4b69e-125">DDLWRAP_FLAG_ANSI—Wrapped object will be exposed as ANSI.</span></span>
    
   - <span data-ttu-id="4b69e-126">DDLWRAP_FLAG_UNICODE —包装的对象将作为 UNICODE 公开。</span><span class="sxs-lookup"><span data-stu-id="4b69e-126">DDLWRAP_FLAG_UNICODE—Wrapped object will be exposed as UNICODE.</span></span>
    
<span data-ttu-id="4b69e-127">_pIID_</span><span class="sxs-lookup"><span data-stu-id="4b69e-127">_pIID_</span></span>
  
>  <span data-ttu-id="4b69e-128">实时已被解开的对象支持的接口的标识符;如果这是未知的, 则将其设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4b69e-128">[in] The identifier of the interface supported by the unwrapped object; set it to NULL if this is unknown.</span></span> 
    
<span data-ttu-id="4b69e-129">_pulReserved_</span><span class="sxs-lookup"><span data-stu-id="4b69e-129">_pulReserved_</span></span>
  
>  <span data-ttu-id="4b69e-130">实时不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="4b69e-130">[in] This parameter is not used.</span></span> <span data-ttu-id="4b69e-131">它必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4b69e-131">It must be NULL.</span></span> 
    
<span data-ttu-id="4b69e-132">_fCheckWrap_</span><span class="sxs-lookup"><span data-stu-id="4b69e-132">_fCheckWrap_</span></span>
  
>  <span data-ttu-id="4b69e-133">实时如果在换行之前应检查_pvUnwrapped_的格式, 则将此参数设置为**true** ;如果不进行检查, 则将该对象设置为**false** 。</span><span class="sxs-lookup"><span data-stu-id="4b69e-133">[in] Set this parameter to **true** if  _pvUnwrapped_ should be checked for its format before wrapping; set it to **false** if the object should be wrapped without checking.</span></span> 
    
<span data-ttu-id="4b69e-134">_ppvWrapped_</span><span class="sxs-lookup"><span data-stu-id="4b69e-134">_ppvWrapped_</span></span>
  
>  <span data-ttu-id="4b69e-135">排除指向请求的对象的指针, 以请求的字符格式封装。</span><span class="sxs-lookup"><span data-stu-id="4b69e-135">[out] A pointer to the requested object, wrapped in the requested character format.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="4b69e-136">返回值</span><span class="sxs-lookup"><span data-stu-id="4b69e-136">Return values</span></span>

<span data-ttu-id="4b69e-137">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="4b69e-137">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4b69e-138">注解</span><span class="sxs-lookup"><span data-stu-id="4b69e-138">Remarks</span></span>

<span data-ttu-id="4b69e-139">如果将_fCheckWrap_设置为**true** , 则传递给已包装的对象将生成一个已解包的对象。</span><span class="sxs-lookup"><span data-stu-id="4b69e-139">Passing in a wrapped object with  _fCheckWrap_ set to **true** will result in an unwrapped object.</span></span> <span data-ttu-id="4b69e-140">无论返回的对象是否被包装, 客户端都要负责释放对返回的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="4b69e-140">Regardless of whether or not the returned object is wrapped, the client is responsible for releasing the reference on the returned object.</span></span> 
  
<span data-ttu-id="4b69e-141">使用**GetProcAddress**在 msmapi32 中查找此函数的地址时, 请指定**HrCreateNewWrappedObject @ 28**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="4b69e-141">When using **GetProcAddress** to look for the address of this function in msmapi32.dll, specify **HrCreateNewWrappedObject@28** as the procedure name.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4b69e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b69e-142">See also</span></span>

- [<span data-ttu-id="4b69e-143">有关数据下降层 API</span><span class="sxs-lookup"><span data-stu-id="4b69e-143">About the Data Degradation Layer API</span></span>](about-the-data-degradation-layer-api.md)
- [<span data-ttu-id="4b69e-144">常量 (数据降级层 API)</span><span class="sxs-lookup"><span data-stu-id="4b69e-144">Constants (Data degradation layer API)</span></span>](constants-data-degradation-layer-api.md)

