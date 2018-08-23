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
ms.openlocfilehash: 3b302de68f27e85c67430f82bd3e2c33009600e9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591350"
---
# <a name="lpfnbutton"></a><span data-ttu-id="518eb-103">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="518eb-103">LPFNBUTTON</span></span>

  
  
<span data-ttu-id="518eb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="518eb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="518eb-105">定义一个 MAPI 调用激活通讯簿对话框中的一个可选的按钮控件的回调函数。</span><span class="sxs-lookup"><span data-stu-id="518eb-105">Defines a callback function that MAPI calls to activate an optional button control in an address book dialog box.</span></span> <span data-ttu-id="518eb-106">此按钮通常是一个**详细信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="518eb-106">This button is typically a **Details** button.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="518eb-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="518eb-107">Header file:</span></span>  <br/> |<span data-ttu-id="518eb-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="518eb-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="518eb-109">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="518eb-109">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="518eb-110">服务提供商</span><span class="sxs-lookup"><span data-stu-id="518eb-110">Service providers</span></span>  <br/> |
|<span data-ttu-id="518eb-111">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="518eb-111">Defined function called by:</span></span>  <br/> |<span data-ttu-id="518eb-112">MAPI</span><span class="sxs-lookup"><span data-stu-id="518eb-112">MAPI</span></span>  <br/> |
   
```cpp
SCODE (STDMETHODCALLTYPE FAR * LPFNBUTTON)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext,
  ULONG cbEntryID,
  LPENTRYID lpSelection,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="518eb-113">参数</span><span class="sxs-lookup"><span data-stu-id="518eb-113">Parameters</span></span>

 <span data-ttu-id="518eb-114">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="518eb-114">_ulUIParam_</span></span>
  
> <span data-ttu-id="518eb-115">[in]任何对话框的父窗口或该函数将显示的窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="518eb-115">[in] Handle of the parent windows for any dialog boxes or windows this function displays.</span></span>
    
 <span data-ttu-id="518eb-116">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="518eb-116">_lpvContext_</span></span>
  
> <span data-ttu-id="518eb-117">[in]MAPI 调用它时，为任意值的指针传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="518eb-117">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="518eb-118">此值可表示的客户端应用程序的有效位倍数的地址。</span><span class="sxs-lookup"><span data-stu-id="518eb-118">This value can represent an address of significance to the client application.</span></span> <span data-ttu-id="518eb-119">通常，c + + 代码_lpvContext_对 c + + 对象表示的指针。</span><span class="sxs-lookup"><span data-stu-id="518eb-119">Typically, for C++ code,  _lpvContext_ represents a pointer to a C++ object.</span></span> 
    
 <span data-ttu-id="518eb-120">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="518eb-120">_cbEntryID_</span></span>
  
> <span data-ttu-id="518eb-121">[in]大小，以字节为单位_lpSelection_参数指向的项标识符。</span><span class="sxs-lookup"><span data-stu-id="518eb-121">[in] Size, in bytes, of the entry identifier pointed to by the  _lpSelection_ parameter.</span></span> 
    
 <span data-ttu-id="518eb-122">_lpSelection_</span><span class="sxs-lookup"><span data-stu-id="518eb-122">_lpSelection_</span></span>
  
> <span data-ttu-id="518eb-123">[in]在对话框中定义所选内容的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="518eb-123">[in] Pointer to the entry identifier defining the selection in the dialog box.</span></span>
    
 <span data-ttu-id="518eb-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="518eb-124">_ulFlags_</span></span>
  
> <span data-ttu-id="518eb-125">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="518eb-125">[in] Reserved; must be zero.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="518eb-126">返回值</span><span class="sxs-lookup"><span data-stu-id="518eb-126">Return value</span></span>

<span data-ttu-id="518eb-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="518eb-127">S_OK</span></span> 
  
> <span data-ttu-id="518eb-128">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="518eb-128">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="518eb-129">注解</span><span class="sxs-lookup"><span data-stu-id="518eb-129">Remarks</span></span>

<span data-ttu-id="518eb-130">客户端应用程序调用基于**LPFNBUTTON**原型，用于定义按钮，在详细信息对话框的回调函数。</span><span class="sxs-lookup"><span data-stu-id="518eb-130">Client applications call a callback function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="518eb-131">客户端将指针传递给回调函数中调用[IAddrBook::Details](iaddrbook-details.md)方法。</span><span class="sxs-lookup"><span data-stu-id="518eb-131">The client passes a pointer to the callback function in calls to the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
  
<span data-ttu-id="518eb-132">服务提供商调用挂接函数基于**LPFNBUTTON**原型，用于定义在详细信息对话框中的按钮。</span><span class="sxs-lookup"><span data-stu-id="518eb-132">Service providers call a hook function based on the **LPFNBUTTON** prototype to define a button in a details dialog box.</span></span> <span data-ttu-id="518eb-133">提供程序将指针传递给此挂接函数中调用[IMAPISupport::Details](imapisupport-details.md)方法。</span><span class="sxs-lookup"><span data-stu-id="518eb-133">The provider passes a pointer to this hook function in calls to the [IMAPISupport::Details](imapisupport-details.md) method.</span></span> 
  
<span data-ttu-id="518eb-134">在这两种情况下，当显示对话框，用户选择定义按钮，MAPI 调用**LPFNBUTTON**。</span><span class="sxs-lookup"><span data-stu-id="518eb-134">In both cases, when the dialog box is displayed and the user chooses the defined button, MAPI calls **LPFNBUTTON**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="518eb-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="518eb-135">See also</span></span>



[<span data-ttu-id="518eb-136">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="518eb-136">BuildDisplayTable</span></span>](builddisplaytable.md)

