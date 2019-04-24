---
title: LPFNBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.LPFNBUTTON
api_type:
- COM
ms.assetid: cb91ae1d-1ea8-4f02-a1f1-f2a356a71477
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 804bd23a148b942fd4580d1e3465fc1f65ff5978
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357440"
---
# <a name="lpfnbutton"></a><span data-ttu-id="c8e43-103">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="c8e43-103">LPFNBUTTON</span></span>

  
  
<span data-ttu-id="c8e43-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c8e43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c8e43-105">定义用于在通讯簿对话框中激活可选按钮控件的 MAPI 调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="c8e43-105">Defines a callback function that MAPI calls to activate an optional button control in an address book dialog box.</span></span> <span data-ttu-id="c8e43-106">此按钮通常为 "**详细信息**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c8e43-106">This button is typically a **Details** button.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c8e43-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c8e43-107">Header file:</span></span>  <br/> |<span data-ttu-id="c8e43-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c8e43-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c8e43-109">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="c8e43-109">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="c8e43-110">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="c8e43-110">Service providers</span></span>  <br/> |
|<span data-ttu-id="c8e43-111">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="c8e43-111">Defined function called by:</span></span>  <br/> |<span data-ttu-id="c8e43-112">MAPI</span><span class="sxs-lookup"><span data-stu-id="c8e43-112">MAPI</span></span>  <br/> |
   
```cpp
SCODE (STDMETHODCALLTYPE FAR * LPFNBUTTON)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext,
  ULONG cbEntryID,
  LPENTRYID lpSelection,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="c8e43-113">参数</span><span class="sxs-lookup"><span data-stu-id="c8e43-113">Parameters</span></span>

 <span data-ttu-id="c8e43-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="c8e43-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="c8e43-115">实时此函数显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="c8e43-115">[in] Handle of the parent windows for any dialog boxes or windows this function displays.</span></span>
    
 <span data-ttu-id="c8e43-116">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="c8e43-116">_lpvContext_</span></span>
  
> <span data-ttu-id="c8e43-117">实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e43-117">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="c8e43-118">此值可以表示对客户端应用程序的重要性的地址。</span><span class="sxs-lookup"><span data-stu-id="c8e43-118">This value can represent an address of significance to the client application.</span></span> <span data-ttu-id="c8e43-119">通常, 对于 c + + 代码, _lpvContext_表示指向 c + + 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e43-119">Typically, for C++ code,  _lpvContext_ represents a pointer to a C++ object.</span></span> 
    
 <span data-ttu-id="c8e43-120">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c8e43-120">_cbEntryID_</span></span>
  
> <span data-ttu-id="c8e43-121">实时由_lpSelection_参数指向的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="c8e43-121">[in] Size, in bytes, of the entry identifier pointed to by the  _lpSelection_ parameter.</span></span> 
    
 <span data-ttu-id="c8e43-122">_lpSelection_</span><span class="sxs-lookup"><span data-stu-id="c8e43-122">_lpSelection_</span></span>
  
> <span data-ttu-id="c8e43-123">实时指向定义对话框中所选内容的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e43-123">[in] Pointer to the entry identifier defining the selection in the dialog box.</span></span>
    
 <span data-ttu-id="c8e43-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c8e43-124">_ulFlags_</span></span>
  
> <span data-ttu-id="c8e43-125">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="c8e43-125">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c8e43-126">返回值</span><span class="sxs-lookup"><span data-stu-id="c8e43-126">Return value</span></span>

<span data-ttu-id="c8e43-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8e43-127">S_OK</span></span> 
  
> <span data-ttu-id="c8e43-128">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="c8e43-128">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c8e43-129">注解</span><span class="sxs-lookup"><span data-stu-id="c8e43-129">Remarks</span></span>

<span data-ttu-id="c8e43-130">客户端应用程序调用基于**LPFNBUTTON**原型的回调函数, 以在 "详细信息" 对话框中定义按钮。</span><span class="sxs-lookup"><span data-stu-id="c8e43-130">Client applications call a callback function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="c8e43-131">客户端在对[IAddrBook::D etails](iaddrbook-details.md)方法的调用中传递指向回调函数的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e43-131">The client passes a pointer to the callback function in calls to the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
  
<span data-ttu-id="c8e43-132">服务提供程序调用基于**LPFNBUTTON**原型的挂钩函数, 以在 "详细信息" 对话框中定义按钮。</span><span class="sxs-lookup"><span data-stu-id="c8e43-132">Service providers call a hook function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="c8e43-133">提供程序在对[IMAPISupport::D etails](imapisupport-details.md)方法的调用中传递指向此挂接函数的指针。</span><span class="sxs-lookup"><span data-stu-id="c8e43-133">The provider passes a pointer to this hook function in calls to the [IMAPISupport::Details](imapisupport-details.md) method.</span></span> 
  
<span data-ttu-id="c8e43-134">在这两种情况下, 当显示对话框且用户选择已定义的按钮时, MAPI 将调用**LPFNBUTTON**。</span><span class="sxs-lookup"><span data-stu-id="c8e43-134">In both cases, when the dialog box is displayed and the user chooses the defined button, MAPI calls **LPFNBUTTON**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c8e43-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8e43-135">See also</span></span>



[<span data-ttu-id="c8e43-136">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="c8e43-136">BuildDisplayTable</span></span>](builddisplaytable.md)

