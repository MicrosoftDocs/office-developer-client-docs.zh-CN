---
title: HrCreateNewWrappedObject
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 780ade1c-88d0-04d2-ba7e-251c19c43438
description: 在首选的字符格式中创建客户端可以访问的对象。
ms.openlocfilehash: 187bcbce8fd1170e05f57c5c9147a8962669fea4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774188"
---
# <a name="hrcreatenewwrappedobject"></a><span data-ttu-id="24e45-103">HrCreateNewWrappedObject</span><span class="sxs-lookup"><span data-stu-id="24e45-103">HrCreateNewWrappedObject</span></span>

<span data-ttu-id="24e45-104">在首选的字符格式中创建客户端可以访问的对象。</span><span class="sxs-lookup"><span data-stu-id="24e45-104">Creates an object that a client can access in a preferred character format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="24e45-105">快速信息</span><span class="sxs-lookup"><span data-stu-id="24e45-105">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="24e45-106">导出：</span><span class="sxs-lookup"><span data-stu-id="24e45-106">Exported by:</span></span>  <br/> |<span data-ttu-id="24e45-107">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="24e45-107">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="24e45-108">调用：</span><span class="sxs-lookup"><span data-stu-id="24e45-108">Called by:</span></span>  <br/> |<span data-ttu-id="24e45-109">客户端</span><span class="sxs-lookup"><span data-stu-id="24e45-109">Client</span></span>  <br/> |
|<span data-ttu-id="24e45-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="24e45-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="24e45-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="24e45-111">Outlook</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="24e45-112">参数</span><span class="sxs-lookup"><span data-stu-id="24e45-112">Parameters</span></span>

<span data-ttu-id="24e45-113">_pvUnwrapped_</span><span class="sxs-lookup"><span data-stu-id="24e45-113">_pvUnwrapped_</span></span>
  
> <span data-ttu-id="24e45-114">[in]初始打开的 Outlook 对象。</span><span class="sxs-lookup"><span data-stu-id="24e45-114">[in] The initial unwrapped Outlook object.</span></span> <span data-ttu-id="24e45-115">必须实现以下接口之一：</span><span class="sxs-lookup"><span data-stu-id="24e45-115">Must implement one of the following interfaces:</span></span>
    
   - <span data-ttu-id="24e45-116">[IMailUser: IMAPIProp](http://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx)， [IMAPIFolder: IMAPIContainer](http://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx)， [IMessage: IMAPIProp](http://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx)， [IMsgStore: IMAPIProp](http://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx)， [IMSLogon: IUnknown](http://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx)，或[IOSTX](http://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="24e45-116">[IMailUser : IMAPIProp](http://msdn.microsoft.com/library/74c25870-62d9-484a-9a99-4dc35c52479e%28Office.15%29.aspx), [IMAPIFolder : IMAPIContainer](http://msdn.microsoft.com/library/bc2e8d17-7687-43c2-8f01-b677703f7288%28Office.15%29.aspx), [IMessage : IMAPIProp](http://msdn.microsoft.com/library/7e244d40-595e-432c-aa8c-f9f62ca3c138%28Office.15%29.aspx), [IMsgStore : IMAPIProp](http://msdn.microsoft.com/library/20090114-b183-4767-8971-a304a9aa47e6%28Office.15%29.aspx), [IMSLogon : IUnknown](http://msdn.microsoft.com/library/d87093dc-f705-465f-ab3c-944ca0cd3e54%28Office.15%29.aspx), or [IOSTX](http://msdn.microsoft.com/library/f374d8d9-be8e-2489-d5fe-8a92e0ecfc6f%28Office.15%29.aspx).</span></span>
    
<span data-ttu-id="24e45-117">_ulUnwrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="24e45-117">_ulUnwrappedFlags_</span></span>
  
> <span data-ttu-id="24e45-118">[in]代表已打开的初始对象的标志。</span><span class="sxs-lookup"><span data-stu-id="24e45-118">[in] Flags that characterize the unwrapped initial object.</span></span> <span data-ttu-id="24e45-119">必须是一个或多个下列值：</span><span class="sxs-lookup"><span data-stu-id="24e45-119">Must be one or more of the following values:</span></span>
    
   - <span data-ttu-id="24e45-120">DDLWRAP_FLAG_ANSI — Unwrapped 对象是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="24e45-120">DDLWRAP_FLAG_ANSI—Unwrapped object is ANSI.</span></span>
    
   - <span data-ttu-id="24e45-121">DDLWRAP_FLAG_UNICODE — Unwrapped 对象是 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="24e45-121">DDLWRAP_FLAG_UNICODE—Unwrapped object is UNICODE.</span></span>
    
<span data-ttu-id="24e45-122">_ulWrappedFlags_</span><span class="sxs-lookup"><span data-stu-id="24e45-122">_ulWrappedFlags_</span></span>
  
>  <span data-ttu-id="24e45-123">[in]首选的字符格式的标志。</span><span class="sxs-lookup"><span data-stu-id="24e45-123">[in] Flags for the preferred character format.</span></span> <span data-ttu-id="24e45-124">必须是一个或多个下列值：</span><span class="sxs-lookup"><span data-stu-id="24e45-124">Must be one or more of the following values:</span></span> 
    
   - <span data-ttu-id="24e45-125">DDLWRAP_FLAG_ANSI — 将作为 ANSI 公开 Wrapped 对象。</span><span class="sxs-lookup"><span data-stu-id="24e45-125">DDLWRAP_FLAG_ANSI—Wrapped object will be exposed as ANSI.</span></span>
    
   - <span data-ttu-id="24e45-126">DDLWRAP_FLAG_UNICODE — Wrapped 对象将公开为 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="24e45-126">DDLWRAP_FLAG_UNICODE—Wrapped object will be exposed as UNICODE.</span></span>
    
<span data-ttu-id="24e45-127">_pIID_</span><span class="sxs-lookup"><span data-stu-id="24e45-127">_pIID_</span></span>
  
>  <span data-ttu-id="24e45-128">[in]已打开的对象; 所支持的接口的标识符将其设置为 NULL 如果这是未知。</span><span class="sxs-lookup"><span data-stu-id="24e45-128">[in] The identifier of the interface supported by the unwrapped object; set it to NULL if this is unknown.</span></span> 
    
<span data-ttu-id="24e45-129">_pulReserved_</span><span class="sxs-lookup"><span data-stu-id="24e45-129">_pulReserved_</span></span>
  
>  <span data-ttu-id="24e45-130">[in]不使用此参数。</span><span class="sxs-lookup"><span data-stu-id="24e45-130">[in] This parameter is not used.</span></span> <span data-ttu-id="24e45-131">它必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="24e45-131">It must be NULL.</span></span> 
    
<span data-ttu-id="24e45-132">_fCheckWrap_</span><span class="sxs-lookup"><span data-stu-id="24e45-132">_fCheckWrap_</span></span>
  
>  <span data-ttu-id="24e45-133">[in]将此参数设置为**true** ，如果_pvUnwrapped_应检查有之前换行; 其格式将其设置为**false**如果对象应自动换行不检查。</span><span class="sxs-lookup"><span data-stu-id="24e45-133">[in] Set this parameter to **true** if  _pvUnwrapped_ should be checked for its format before wrapping; set it to **false** if the object should be wrapped without checking.</span></span> 
    
<span data-ttu-id="24e45-134">_ppvWrapped_</span><span class="sxs-lookup"><span data-stu-id="24e45-134">_ppvWrapped_</span></span>
  
>  <span data-ttu-id="24e45-135">[输出]指向请求的对象，以请求的字符格式包装的指针。</span><span class="sxs-lookup"><span data-stu-id="24e45-135">[out] A pointer to the requested object, wrapped in the requested character format.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="24e45-136">返回值</span><span class="sxs-lookup"><span data-stu-id="24e45-136">Return values</span></span>

<span data-ttu-id="24e45-137">如果该调用成功，则返回 S_OK否则为一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="24e45-137">S_OK if the call succeeded; otherwise, an error code.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="24e45-138">注释</span><span class="sxs-lookup"><span data-stu-id="24e45-138">Remarks</span></span>

<span data-ttu-id="24e45-139">传入_fCheckWrap_将设置为**true**的被环绕对象将导致打开的对象。</span><span class="sxs-lookup"><span data-stu-id="24e45-139">Passing in a wrapped object with  _fCheckWrap_ set to **true** will result in an unwrapped object.</span></span> <span data-ttu-id="24e45-140">无论返回的对象自动换行，客户端负责释放在返回的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="24e45-140">Regardless of whether or not the returned object is wrapped, the client is responsible for releasing the reference on the returned object.</span></span> 
  
<span data-ttu-id="24e45-141">当使用**GetProcAddress**查找 msmapi32.dll 中此函数的地址，指定**HrCreateNewWrappedObject@28**作为过程名称。</span><span class="sxs-lookup"><span data-stu-id="24e45-141">When using **GetProcAddress** to look for the address of this function in msmapi32.dll, specify **HrCreateNewWrappedObject@28** as the procedure name.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="24e45-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24e45-142">See also</span></span>

- [<span data-ttu-id="24e45-143">有关数据下降层 API</span><span class="sxs-lookup"><span data-stu-id="24e45-143">About the Data Degradation Layer API</span></span>](about-the-data-degradation-layer-api.md)
- [<span data-ttu-id="24e45-144">常量 （数据降级层 API）</span><span class="sxs-lookup"><span data-stu-id="24e45-144">Constants (Data degradation layer API)</span></span>](constants-data-degradation-layer-api.md)

