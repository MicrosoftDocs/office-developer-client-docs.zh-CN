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
# <a name="imapisupportdetails"></a><span data-ttu-id="20678-103">IMAPISupport::Details</span><span class="sxs-lookup"><span data-stu-id="20678-103">IMAPISupport::Details</span></span>

  
  
<span data-ttu-id="20678-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20678-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20678-105">显示一个对话框，其中显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="20678-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="20678-106">参数</span><span class="sxs-lookup"><span data-stu-id="20678-106">Parameters</span></span>

 <span data-ttu-id="20678-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="20678-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="20678-108">[out]指向返回对话框的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="20678-108">[out] A pointer to the handle to the parent window of the returned dialog box.</span></span>
    
 <span data-ttu-id="20678-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="20678-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="20678-110">[in]指向基于 [DISMISSMODELESS](dismissmodeless.md) 原型的函数的指针，或 NULL。</span><span class="sxs-lookup"><span data-stu-id="20678-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="20678-111">此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。</span><span class="sxs-lookup"><span data-stu-id="20678-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="20678-112">当用户关闭无模式地址对话框时，MAPI 将调用 **DISMISSMODELESS** 函数，以通知调用 **IMAPISupport：:D的** 客户端该对话框不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="20678-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **IMAPISupport::Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="20678-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="20678-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="20678-114">[in]指向要传递给 _lpfnDismiss_ 参数指向的 **DISMISSMODELESS** 函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="20678-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="20678-115">此参数仅在  _ulFlags_ 参数中包括 DIALOG_SDI 标志，仅适用于对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="20678-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="20678-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="20678-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="20678-117">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="20678-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="20678-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="20678-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="20678-119">[in]指向显示其详细信息的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="20678-119">[in] A pointer to the entry identifier for which details are displayed.</span></span>
    
 <span data-ttu-id="20678-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="20678-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="20678-121">[in]指向基于 [LPFNBUTTON](lpfnbutton.md) 函数原型的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="20678-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="20678-122">**LPFNBUTTON** 函数将按钮添加到详细信息对话框中。</span><span class="sxs-lookup"><span data-stu-id="20678-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="20678-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="20678-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="20678-124">[in]指向用作  _lpfButtonCallback_ 参数所指定函数的参数的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="20678-124">[in] A pointer to data used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="20678-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="20678-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="20678-126">[in]指向包含要应用于所添加按钮的文本的字符串的指针（如果该按钮是可扩展的）。</span><span class="sxs-lookup"><span data-stu-id="20678-126">[in] A pointer to a string that contains text to be applied to the added button if that button is extensible.</span></span> <span data-ttu-id="20678-127">如果不需要可扩展按钮，则  _lpszButtonText_ 参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="20678-127">The  _lpszButtonText_ parameter should be NULL if an extensible button is not needed.</span></span> 
    
 <span data-ttu-id="20678-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="20678-128">_ulFlags_</span></span>
  
> <span data-ttu-id="20678-129">[in]控制  _lpszButtonText_ 参数的文本类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="20678-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="20678-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="20678-130">The following flag can be set:</span></span> 
    
<span data-ttu-id="20678-131">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="20678-131">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="20678-132">显示常用地址对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="20678-132">Display the modal version of the common address dialog box.</span></span> <span data-ttu-id="20678-133">此标志与 DIALOG_SDI。</span><span class="sxs-lookup"><span data-stu-id="20678-133">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="20678-134">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="20678-134">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="20678-135">显示公用地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="20678-135">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="20678-136">此标志与 DIALOG_MODAL。</span><span class="sxs-lookup"><span data-stu-id="20678-136">This flag is mutually exclusive with DIALOG_MODAL.</span></span> 
    
<span data-ttu-id="20678-137">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="20678-137">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="20678-138">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="20678-138">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="20678-139">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="20678-139">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="20678-140">返回值</span><span class="sxs-lookup"><span data-stu-id="20678-140">Return value</span></span>

<span data-ttu-id="20678-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="20678-141">S_OK</span></span> 
  
> <span data-ttu-id="20678-142">已成功显示通讯簿条目的详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="20678-142">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="20678-143">备注</span><span class="sxs-lookup"><span data-stu-id="20678-143">Remarks</span></span>

<span data-ttu-id="20678-144">为 **通讯簿提供程序支持对象:D IMAPISupport：:D etails** 方法。</span><span class="sxs-lookup"><span data-stu-id="20678-144">The **IMAPISupport::Details** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="20678-145">通讯簿提供程序调用 **Details** 可显示一个对话框，该对话框提供有关通讯簿中特定条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="20678-145">Address book providers call **Details** to display a dialog box that gives details on a particular entry in the address book.</span></span> <span data-ttu-id="20678-146">_lpfButtonCallback、lpvButtonContext_ 和 _lpszButtonText_ 参数可用于向对话框添加客户端定义的按钮。 </span><span class="sxs-lookup"><span data-stu-id="20678-146">The  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters can be used to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="20678-147">单击按钮时，MAPI 将调用  _lpfButtonCallback_ 指向的回调函数，同时传递按钮的条目标识符和  _lpvButtonContext 中的数据_。</span><span class="sxs-lookup"><span data-stu-id="20678-147">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="20678-148">如果不需要可扩展按钮  _，lpszButtonText_ 应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="20678-148">If an extensible button is not needed,  _lpszButtonText_ should be NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="20678-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20678-149">See also</span></span>



[<span data-ttu-id="20678-150">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="20678-150">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="20678-151">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="20678-151">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="20678-152">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="20678-152">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="20678-153">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="20678-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

