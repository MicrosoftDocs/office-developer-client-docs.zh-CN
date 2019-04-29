---
title: IMAPISupportDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.Details
api_type:
- COM
ms.assetid: 1a62efa2-dd6b-4acb-a760-defa601c20c9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bdc57a6e951e54640fe3c638977c6a5f16986e68
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426777"
---
# <a name="imapisupportdetails"></a><span data-ttu-id="4d783-103">IMAPISupport::Details</span><span class="sxs-lookup"><span data-stu-id="4d783-103">IMAPISupport::Details</span></span>

  
  
<span data-ttu-id="4d783-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4d783-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4d783-105">显示一个对话框, 显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d783-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
```cpp
HRESULT Details(
  ULONG_PTR FAR * lpulUIParam,
  LPFNDISMISS lpfnDismiss,
  LPVOID lpvDismissContext,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPFNBUTTON lpfButtonCallback,
  LPVOID lpvButtonContext,
  LPSTR lpszButtonText,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="4d783-106">参数</span><span class="sxs-lookup"><span data-stu-id="4d783-106">Parameters</span></span>

 <span data-ttu-id="4d783-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="4d783-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="4d783-108">排除指向返回的对话框的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="4d783-108">[out] A pointer to the handle to the parent window of the returned dialog box.</span></span>
    
 <span data-ttu-id="4d783-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="4d783-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="4d783-110">实时指向基于[DISMISSMODELESS](dismissmodeless.md)原型的函数的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="4d783-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="4d783-111">此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="4d783-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="4d783-112">MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 通知客户端正在调用**IMAPISupport::D etails**该对话框不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="4d783-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **IMAPISupport::Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="4d783-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="4d783-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="4d783-114">实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="4d783-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="4d783-115">此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="4d783-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="4d783-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="4d783-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="4d783-117">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="4d783-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="4d783-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="4d783-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="4d783-119">实时指向显示其详细信息的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="4d783-119">[in] A pointer to the entry identifier for which details are displayed.</span></span>
    
 <span data-ttu-id="4d783-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="4d783-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="4d783-121">实时指向基于[LPFNBUTTON](lpfnbutton.md)函数原型的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="4d783-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="4d783-122">**LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。</span><span class="sxs-lookup"><span data-stu-id="4d783-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="4d783-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="4d783-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="4d783-124">实时指向用作参数的数据的指针, 该函数由_lpfButtonCallback_参数指定。</span><span class="sxs-lookup"><span data-stu-id="4d783-124">[in] A pointer to data used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="4d783-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="4d783-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="4d783-126">实时指向包含要应用于已添加按钮的文本的字符串的指针 (如果该按钮是可扩展的)。</span><span class="sxs-lookup"><span data-stu-id="4d783-126">[in] A pointer to a string that contains text to be applied to the added button if that button is extensible.</span></span> <span data-ttu-id="4d783-127">如果不需要可扩展按钮, 则_lpszButtonText_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4d783-127">The  _lpszButtonText_ parameter should be NULL if an extensible button is not needed.</span></span> 
    
 <span data-ttu-id="4d783-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="4d783-128">_ulFlags_</span></span>
  
> <span data-ttu-id="4d783-129">实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="4d783-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="4d783-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="4d783-130">The following flag can be set:</span></span> 
    
<span data-ttu-id="4d783-131">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="4d783-131">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="4d783-132">显示 "常用地址" 对话框的 "模式" 版本。</span><span class="sxs-lookup"><span data-stu-id="4d783-132">Display the modal version of the common address dialog box.</span></span> <span data-ttu-id="4d783-133">此标志与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="4d783-133">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="4d783-134">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="4d783-134">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="4d783-135">显示 "常用地址" 对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="4d783-135">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="4d783-136">此标志与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="4d783-136">This flag is mutually exclusive with DIALOG_MODAL.</span></span> 
    
<span data-ttu-id="4d783-137">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4d783-137">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="4d783-138">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="4d783-138">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="4d783-139">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="4d783-139">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="4d783-140">返回值</span><span class="sxs-lookup"><span data-stu-id="4d783-140">Return value</span></span>

<span data-ttu-id="4d783-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d783-141">S_OK</span></span> 
  
> <span data-ttu-id="4d783-142">已成功显示通讯簿条目的 "详细信息" 对话框。</span><span class="sxs-lookup"><span data-stu-id="4d783-142">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4d783-143">说明</span><span class="sxs-lookup"><span data-stu-id="4d783-143">Remarks</span></span>

<span data-ttu-id="4d783-144">**IMAPISupport::D etails**方法是为通讯簿提供程序支持对象而实现的。</span><span class="sxs-lookup"><span data-stu-id="4d783-144">The **IMAPISupport::Details** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="4d783-145">通讯簿提供程序调用**详细信息**以显示一个对话框, 该对话框提供有关通讯簿中的特定条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d783-145">Address book providers call **Details** to display a dialog box that gives details on a particular entry in the address book.</span></span> <span data-ttu-id="4d783-146">_lpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数可用于将客户端定义的按钮添加到对话框中。</span><span class="sxs-lookup"><span data-stu-id="4d783-146">The  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters can be used to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="4d783-147">单击该按钮时, MAPI 将调用_lpfButtonCallback_指向的回调函数, 同时传递按钮的条目标识符和_lpvButtonContext_中的数据。</span><span class="sxs-lookup"><span data-stu-id="4d783-147">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="4d783-148">如果不需要可扩展按钮, _lpszButtonText_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4d783-148">If an extensible button is not needed,  _lpszButtonText_ should be NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d783-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d783-149">See also</span></span>



[<span data-ttu-id="4d783-150">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="4d783-150">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="4d783-151">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="4d783-151">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="4d783-152">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="4d783-152">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="4d783-153">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d783-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

