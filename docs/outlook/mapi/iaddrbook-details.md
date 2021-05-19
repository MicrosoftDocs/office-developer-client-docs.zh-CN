---
title: IAddrBookDetails
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.Details
api_type:
- COM
ms.assetid: 4eee4382-98c3-4714-8920-8d72edef00b8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5fbd20a6b5d5598b8fa51f9c369eefac9a1ea2e9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424677"
---
# <a name="iaddrbookdetails"></a><span data-ttu-id="c73ec-103">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="c73ec-103">IAddrBook::Details</span></span>

  
  
<span data-ttu-id="c73ec-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c73ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c73ec-105">显示一个对话框，其中显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c73ec-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="c73ec-106">参数</span><span class="sxs-lookup"><span data-stu-id="c73ec-106">Parameters</span></span>

 <span data-ttu-id="c73ec-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="c73ec-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="c73ec-108">[in]指向对话框的父窗口句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="c73ec-108">[in] A pointer to a handle of the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="c73ec-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="c73ec-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="c73ec-110">[in]指向基于 [DISMISSMODELESS](dismissmodeless.md) 原型的函数的指针，或 NULL。</span><span class="sxs-lookup"><span data-stu-id="c73ec-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="c73ec-111">此成员仅适用于对话框的无模式版本，如要设置的 DIALOG_SDI 指示。</span><span class="sxs-lookup"><span data-stu-id="c73ec-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="c73ec-112">MAPI 在用户关闭无模式地址对话框时调用 **DISMISSMODELESS** 函数，并通知调用 **Details** 的客户端该对话框不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c73ec-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="c73ec-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="c73ec-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="c73ec-114">[in]指向要传递给 _lpfnDismiss_ 参数指向的 **DISMISSMODELESS** 函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="c73ec-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="c73ec-115">此参数仅在  _ulFlags_ 参数中包括 DIALOG_SDI 标志，仅适用于对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="c73ec-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="c73ec-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="c73ec-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="c73ec-117">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="c73ec-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="c73ec-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="c73ec-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="c73ec-119">[in]指向显示其详细信息的条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="c73ec-119">[in] A pointer to the entry identifier for the entry for which details are displayed.</span></span>
    
 <span data-ttu-id="c73ec-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="c73ec-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="c73ec-121">[in]指向基于 [LPFNBUTTON](lpfnbutton.md) 函数原型的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="c73ec-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="c73ec-122">**LPFNBUTTON** 函数将按钮添加到详细信息对话框中。</span><span class="sxs-lookup"><span data-stu-id="c73ec-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="c73ec-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="c73ec-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="c73ec-124">[in]指向用作  _lpfButtonCallback_ 参数所指定函数的参数的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="c73ec-124">[in] A pointer to data that was used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="c73ec-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="c73ec-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="c73ec-126">[in]指向包含要应用于所添加按钮的文本的字符串的指针（如果该按钮是可扩展的）。</span><span class="sxs-lookup"><span data-stu-id="c73ec-126">[in] A pointer to a string that contains text to be applied to the added button, if that button is extensible.</span></span> <span data-ttu-id="c73ec-127">如果  _不需要可扩展按钮，lpszButtonText_ 参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c73ec-127">The  _lpszButtonText_ parameter should be NULL if you do not need an extensible button.</span></span> 
    
 <span data-ttu-id="c73ec-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c73ec-128">_ulFlags_</span></span>
  
> <span data-ttu-id="c73ec-129">[in]控制  _lpszButtonText_ 参数的文本类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="c73ec-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="c73ec-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="c73ec-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="c73ec-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="c73ec-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="c73ec-132">指示 **详细信息返回** S_OK如果实际对地址进行了更改;否则 **，Details** 将S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="c73ec-132">Indicates that **Details** returns S_OK if changes are actually made to the address; otherwise, **Details** returns S_FALSE.</span></span> 
    
<span data-ttu-id="c73ec-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="c73ec-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="c73ec-134">显示常用地址对话框的模式版本，该对话框始终显示在非Outlook中。</span><span class="sxs-lookup"><span data-stu-id="c73ec-134">Display the modal version of the common address dialog box, which is always shown in non-Outlook clients.</span></span> <span data-ttu-id="c73ec-135">此标志与 DIALOG_SDI。</span><span class="sxs-lookup"><span data-stu-id="c73ec-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="c73ec-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="c73ec-136">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="c73ec-137">显示公用地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="c73ec-137">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="c73ec-138">对于非客户端，此Outlook忽略。</span><span class="sxs-lookup"><span data-stu-id="c73ec-138">This flag is ignored for non-Outlook clients.</span></span> 
    
<span data-ttu-id="c73ec-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="c73ec-139">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="c73ec-140">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="c73ec-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="c73ec-141">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="c73ec-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c73ec-142">返回值</span><span class="sxs-lookup"><span data-stu-id="c73ec-142">Return value</span></span>

<span data-ttu-id="c73ec-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="c73ec-143">S_OK</span></span> 
  
> <span data-ttu-id="c73ec-144">已成功显示通讯簿条目的详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="c73ec-144">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c73ec-145">备注</span><span class="sxs-lookup"><span data-stu-id="c73ec-145">Remarks</span></span>

<span data-ttu-id="c73ec-146">客户端应用程序调用 **Details** 方法以显示一个对话框，该对话框提供有关通讯簿中特定条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c73ec-146">Client applications call the **Details** method to display a dialog box that provides details about a particular entry in the address book.</span></span> <span data-ttu-id="c73ec-147">可以使用 _lpfButtonCallback、lpvButtonContext_ 和 _lpszButtonText_ 参数向对话框添加客户端定义的按钮。 </span><span class="sxs-lookup"><span data-stu-id="c73ec-147">You can use the  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="c73ec-148">单击按钮时，MAPI 将调用  _lpfButtonCallback_ 指向的回调函数，同时传递按钮的条目标识符和  _lpvButtonContext 中的数据_。</span><span class="sxs-lookup"><span data-stu-id="c73ec-148">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="c73ec-149">如果不需要可扩展按钮  _，lpszButtonText_ 应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c73ec-149">If you do not need an extensible button,  _lpszButtonText_ should be NULL.</span></span> 
  
 <span data-ttu-id="c73ec-150">**详细信息** 支持 Unicode 字符字符串;Unicode 字符串在详细信息对话框中显示之前 (MBCS) 格式转换为多字节字符串。</span><span class="sxs-lookup"><span data-stu-id="c73ec-150">**Details** supports Unicode character strings; Unicode strings are converted to the multibyte character string (MBCS) format before they are displayed in the details dialog box.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c73ec-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c73ec-151">MFCMAPI reference</span></span>

<span data-ttu-id="c73ec-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c73ec-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c73ec-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="c73ec-153">**File**</span></span>|<span data-ttu-id="c73ec-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="c73ec-154">**Function**</span></span>|<span data-ttu-id="c73ec-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="c73ec-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c73ec-156">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="c73ec-156">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="c73ec-157">CBaseDialog：：OnOpenEntryID</span><span class="sxs-lookup"><span data-stu-id="c73ec-157">CBaseDialog::OnOpenEntryID</span></span>  <br/> |<span data-ttu-id="c73ec-158">MFCMAPI 使用 **Details** 方法显示一个对话框，该对话框显示通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c73ec-158">MFCMAPI uses the **Details** method to display a dialog box that shows the details for an address book entry.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c73ec-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c73ec-159">See also</span></span>



[<span data-ttu-id="c73ec-160">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="c73ec-160">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="c73ec-161">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="c73ec-161">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="c73ec-162">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="c73ec-162">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="c73ec-163">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c73ec-163">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="c73ec-164">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c73ec-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

