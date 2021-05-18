---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 创建客户端可以使用首选字符格式访问的对象。
ms.openlocfilehash: 3f68e0f275bcc5df065b3113d3322d6957f76df0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317603"
---
# <a name="hrcreatenewwrappedobject"></a><span data-ttu-id="9b574-103">HrCreateNewWrappedObject</span><span class="sxs-lookup"><span data-stu-id="9b574-103">HrCreateNewWrappedObject</span></span>

<span data-ttu-id="9b574-104">创建客户端可以使用首选字符格式访问的对象。</span><span class="sxs-lookup"><span data-stu-id="9b574-104">Creates an object that a client can access in a preferred character format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="9b574-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="9b574-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9b574-106">导出者：</span><span class="sxs-lookup"><span data-stu-id="9b574-106">Exported by:</span></span>  <br/> |<span data-ttu-id="9b574-107">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="9b574-107">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="9b574-108">调用者：</span><span class="sxs-lookup"><span data-stu-id="9b574-108">Called by:</span></span>  <br/> |<span data-ttu-id="9b574-109">客户端</span><span class="sxs-lookup"><span data-stu-id="9b574-109">Client</span></span>  <br/> |
|<span data-ttu-id="9b574-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="9b574-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="9b574-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="9b574-111">Outlook</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="9b574-112">参数</span><span class="sxs-lookup"><span data-stu-id="9b574-112">Parameters</span></span>

<span data-ttu-id="9b574-113">_pvUnwrapped_</span><span class="sxs-lookup"><span data-stu-id="9b574-113">_pvUnwrapped_</span></span>
  
> <span data-ttu-id="9b574-114">[in]初始未包Outlook对象。</span><span class="sxs-lookup"><span data-stu-id="9b574-114">[in] The initial unwrapped Outlook object.</span></span> <span data-ttu-id="9b574-115">必须实现以下接口之一：</span><span class="sxs-lookup"><span data-stu-id="9b574-115">Must implement one of the following interfaces:</span></span>
    
   - <span data-ttu-id="9b574-116">[IMailUser ： IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx)， [IMAPIFolder ： IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx)， [IMessage ： IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx)， [IMsgStore ： IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx)， [IMSLogon ： IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx)， or [IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="9b574-116">[IMailUser : IMAPIProp](https://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder : IMAPIContainer](https://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage : IMAPIProp](https://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore : IMAPIProp](https://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon : IUnknown](https://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), or [IOSTX](https://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).</span></span>
    
<span data-ttu-id="9b574-117">_ulUnwrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="9b574-117">_ulUnwrappedFlags_</span></span>
  
> <span data-ttu-id="9b574-118">[in]表示未包装的初始对象特征的标志。</span><span class="sxs-lookup"><span data-stu-id="9b574-118">[in] Flags that characterize the unwrapped initial object.</span></span> <span data-ttu-id="9b574-119">必须为以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="9b574-119">Must be one or more of the following values:</span></span>
    
   - <span data-ttu-id="9b574-120">DDLWRAP_FLAG_ANSI —Unwrapped 对象是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="9b574-120">DDLWRAP_FLAG_ANSI—Unwrapped object is ANSI.</span></span>
    
   - <span data-ttu-id="9b574-121">DDLWRAP_FLAG_UNICODE —Unwrapped 对象是 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="9b574-121">DDLWRAP_FLAG_UNICODE—Unwrapped object is UNICODE.</span></span>
    
<span data-ttu-id="9b574-122">_ulWrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="9b574-122">_ulWrappedFlags_</span></span>
  
>  <span data-ttu-id="9b574-123">[in]首选字符格式的标志。</span><span class="sxs-lookup"><span data-stu-id="9b574-123">[in] Flags for the preferred character format.</span></span> <span data-ttu-id="9b574-124">必须为以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="9b574-124">Must be one or more of the following values:</span></span> 
    
   - <span data-ttu-id="9b574-125">DDLWRAP_FLAG_ANSI封装对象将公开为 ANSI。</span><span class="sxs-lookup"><span data-stu-id="9b574-125">DDLWRAP_FLAG_ANSI—Wrapped object will be exposed as ANSI.</span></span>
    
   - <span data-ttu-id="9b574-126">DDLWRAP_FLAG_UNICODE封装对象将公开为 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="9b574-126">DDLWRAP_FLAG_UNICODE—Wrapped object will be exposed as UNICODE.</span></span>
    
<span data-ttu-id="9b574-127">_pIID_</span><span class="sxs-lookup"><span data-stu-id="9b574-127">_pIID_</span></span>
  
>  <span data-ttu-id="9b574-128">[in]未包对象支持的接口的标识符;如果未知，则设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9b574-128">[in] The identifier of the interface supported by the unwrapped object; set it to NULL if this is unknown.</span></span> 
    
<span data-ttu-id="9b574-129">_将保留_</span><span class="sxs-lookup"><span data-stu-id="9b574-129">_pulReserved_</span></span>
  
>  <span data-ttu-id="9b574-130">[in]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="9b574-130">[in] This parameter is not used.</span></span> <span data-ttu-id="9b574-131">它必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9b574-131">It must be NULL.</span></span> 
    
<span data-ttu-id="9b574-132">_fCheckWrap_</span><span class="sxs-lookup"><span data-stu-id="9b574-132">_fCheckWrap_</span></span>
  
>  <span data-ttu-id="9b574-133">[in]如果应在换行前检查 _pvUnwrapped_ 的格式，则此参数设置为 **true;** 如果应在不检查的情况下封装对象，则设置为 **false。**</span><span class="sxs-lookup"><span data-stu-id="9b574-133">[in] Set this parameter to **true** if  _pvUnwrapped_ should be checked for its format before wrapping; set it to **false** if the object should be wrapped without checking.</span></span> 
    
<span data-ttu-id="9b574-134">_ppvWrapped_</span><span class="sxs-lookup"><span data-stu-id="9b574-134">_ppvWrapped_</span></span>
  
>  <span data-ttu-id="9b574-135">[out]一个指向所请求对象的指针，包装在请求的字符格式中。</span><span class="sxs-lookup"><span data-stu-id="9b574-135">[out] A pointer to the requested object, wrapped in the requested character format.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="9b574-136">返回值</span><span class="sxs-lookup"><span data-stu-id="9b574-136">Return values</span></span>

<span data-ttu-id="9b574-137">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="9b574-137">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9b574-138">备注</span><span class="sxs-lookup"><span data-stu-id="9b574-138">Remarks</span></span>

<span data-ttu-id="9b574-139">在  _fCheckWrap_ 设置为 **true** 的封装对象中传递将导致未封装的对象。</span><span class="sxs-lookup"><span data-stu-id="9b574-139">Passing in a wrapped object with  _fCheckWrap_ set to **true** will result in an unwrapped object.</span></span> <span data-ttu-id="9b574-140">无论返回的对象是否被封装，客户端都负责释放对返回对象的引用。</span><span class="sxs-lookup"><span data-stu-id="9b574-140">Regardless of whether or not the returned object is wrapped, the client is responsible for releasing the reference on the returned object.</span></span> 
  
<span data-ttu-id="9b574-141">使用 **GetProcAddress** 在 msmapi32.dll 中查找此函数的地址时，HrCreateNewWrappedObject@28指定为 **过程** 名称。</span><span class="sxs-lookup"><span data-stu-id="9b574-141">When using **GetProcAddress** to look for the address of this function in msmapi32.dll, specify **HrCreateNewWrappedObject@28** as the procedure name.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9b574-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b574-142">See also</span></span>

- [<span data-ttu-id="9b574-143">有关数据下降层 API</span><span class="sxs-lookup"><span data-stu-id="9b574-143">About the Data Degradation Layer API</span></span>](about-the-data-degradation-layer-api.md)
- [<span data-ttu-id="9b574-144">数据 (层 API) </span><span class="sxs-lookup"><span data-stu-id="9b574-144">Constants (Data degradation layer API)</span></span>](constants-data-degradation-layer-api.md)

