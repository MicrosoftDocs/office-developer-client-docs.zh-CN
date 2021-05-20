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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431510"
---
# <a name="lpfnbutton"></a><span data-ttu-id="88c8e-103">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="88c8e-103">LPFNBUTTON</span></span>

  
  
<span data-ttu-id="88c8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="88c8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="88c8e-105">定义 MAPI 调用的回调函数，以激活通讯簿对话框中的可选按钮控件。</span><span class="sxs-lookup"><span data-stu-id="88c8e-105">Defines a callback function that MAPI calls to activate an optional button control in an address book dialog box.</span></span> <span data-ttu-id="88c8e-106">此按钮通常为"详细信息 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="88c8e-106">This button is typically a **Details** button.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="88c8e-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="88c8e-107">Header file:</span></span>  <br/> |<span data-ttu-id="88c8e-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="88c8e-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="88c8e-109">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="88c8e-109">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="88c8e-110">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="88c8e-110">Service providers</span></span>  <br/> |
|<span data-ttu-id="88c8e-111">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="88c8e-111">Defined function called by:</span></span>  <br/> |<span data-ttu-id="88c8e-112">MAPI</span><span class="sxs-lookup"><span data-stu-id="88c8e-112">MAPI</span></span>  <br/> |
   
```cpp
SCODE (STDMETHODCALLTYPE FAR * LPFNBUTTON)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext,
  ULONG cbEntryID,
  LPENTRYID lpSelection,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="88c8e-113">参数</span><span class="sxs-lookup"><span data-stu-id="88c8e-113">Parameters</span></span>

 <span data-ttu-id="88c8e-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="88c8e-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="88c8e-115">[in]此函数显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="88c8e-115">[in] Handle of the parent windows for any dialog boxes or windows this function displays.</span></span>
    
 <span data-ttu-id="88c8e-116">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="88c8e-116">_lpvContext_</span></span>
  
> <span data-ttu-id="88c8e-117">[in]指向 MAPI 调用回调函数时传递给回调函数的任意值的指针。</span><span class="sxs-lookup"><span data-stu-id="88c8e-117">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="88c8e-118">此值可以表示对客户端应用程序有意义的地址。</span><span class="sxs-lookup"><span data-stu-id="88c8e-118">This value can represent an address of significance to the client application.</span></span> <span data-ttu-id="88c8e-119">通常，对于 C++ 代码  _，lpvContext_ 表示指向 C++ 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="88c8e-119">Typically, for C++ code,  _lpvContext_ represents a pointer to a C++ object.</span></span> 
    
 <span data-ttu-id="88c8e-120">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="88c8e-120">_cbEntryID_</span></span>
  
> <span data-ttu-id="88c8e-121">[in]  _lpSelection_ 参数指向的条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="88c8e-121">[in] Size, in bytes, of the entry identifier pointed to by the  _lpSelection_ parameter.</span></span> 
    
 <span data-ttu-id="88c8e-122">_lpSelection_</span><span class="sxs-lookup"><span data-stu-id="88c8e-122">_lpSelection_</span></span>
  
> <span data-ttu-id="88c8e-123">[in]指向定义对话框中选定内容项的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="88c8e-123">[in] Pointer to the entry identifier defining the selection in the dialog box.</span></span>
    
 <span data-ttu-id="88c8e-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="88c8e-124">_ulFlags_</span></span>
  
> <span data-ttu-id="88c8e-125">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="88c8e-125">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="88c8e-126">返回值</span><span class="sxs-lookup"><span data-stu-id="88c8e-126">Return value</span></span>

<span data-ttu-id="88c8e-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="88c8e-127">S_OK</span></span> 
  
> <span data-ttu-id="88c8e-128">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="88c8e-128">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="88c8e-129">备注</span><span class="sxs-lookup"><span data-stu-id="88c8e-129">Remarks</span></span>

<span data-ttu-id="88c8e-130">客户端应用程序基于 **LPFNBUTTON** 原型调用回调函数，以定义详细信息对话框中的按钮。</span><span class="sxs-lookup"><span data-stu-id="88c8e-130">Client applications call a callback function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="88c8e-131">客户端在调用 [IAddrBook：:D etails 方法时传递指向回调函数的](iaddrbook-details.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="88c8e-131">The client passes a pointer to the callback function in calls to the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
  
<span data-ttu-id="88c8e-132">服务提供商基于 **LPFNBUTTON** 原型调用挂钩函数，以定义详细信息对话框中的按钮。</span><span class="sxs-lookup"><span data-stu-id="88c8e-132">Service providers call a hook function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="88c8e-133">提供程序在调用 [IMAPISupport：:D etails](imapisupport-details.md) 方法时传递指向此挂钩函数的指针。</span><span class="sxs-lookup"><span data-stu-id="88c8e-133">The provider passes a pointer to this hook function in calls to the [IMAPISupport::Details](imapisupport-details.md) method.</span></span> 
  
<span data-ttu-id="88c8e-134">在这两种情况下，当对话框显示并且用户选择定义的按钮时，MAPI 调用 **LPFNBUTTON**。</span><span class="sxs-lookup"><span data-stu-id="88c8e-134">In both cases, when the dialog box is displayed and the user chooses the defined button, MAPI calls **LPFNBUTTON**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="88c8e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88c8e-135">See also</span></span>



[<span data-ttu-id="88c8e-136">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="88c8e-136">BuildDisplayTable</span></span>](builddisplaytable.md)

