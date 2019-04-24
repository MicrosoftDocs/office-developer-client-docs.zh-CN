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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341718"
---
# <a name="iaddrbookdetails"></a><span data-ttu-id="2c4e7-103">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="2c4e7-103">IAddrBook::Details</span></span>

  
  
<span data-ttu-id="2c4e7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c4e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c4e7-105">显示一个对话框, 显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="2c4e7-106">参数</span><span class="sxs-lookup"><span data-stu-id="2c4e7-106">Parameters</span></span>

 <span data-ttu-id="2c4e7-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="2c4e7-108">实时指向对话框父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-108">[in] A pointer to a handle of the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="2c4e7-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="2c4e7-110">实时指向基于[DISMISSMODELESS](dismissmodeless.md)原型的函数的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="2c4e7-111">此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="2c4e7-112">MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 告知客户端正在调用对话框中不再处于活动状态的**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="2c4e7-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="2c4e7-114">实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="2c4e7-115">此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="2c4e7-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="2c4e7-117">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="2c4e7-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="2c4e7-119">实时指向显示其详细信息的条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-119">[in] A pointer to the entry identifier for the entry for which details are displayed.</span></span>
    
 <span data-ttu-id="2c4e7-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="2c4e7-121">实时指向基于[LPFNBUTTON](lpfnbutton.md)函数原型的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="2c4e7-122">**LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="2c4e7-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="2c4e7-124">实时指向用作_lpfButtonCallback_参数所指定函数的参数的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-124">[in] A pointer to data that was used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="2c4e7-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="2c4e7-126">实时指向一个字符串的指针, 该字符串包含要应用于已添加按钮的文本 (如果该按钮是可扩展的)。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-126">[in] A pointer to a string that contains text to be applied to the added button, if that button is extensible.</span></span> <span data-ttu-id="2c4e7-127">如果不需要可扩展按钮, 则_lpszButtonText_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-127">The  _lpszButtonText_ parameter should be NULL if you do not need an extensible button.</span></span> 
    
 <span data-ttu-id="2c4e7-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2c4e7-128">_ulFlags_</span></span>
  
> <span data-ttu-id="2c4e7-129">实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="2c4e7-130">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2c4e7-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="2c4e7-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="2c4e7-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="2c4e7-132">指示如果实际对地址进行了更改, 则**详细信息**返回 S_OK; 否则返回 false。否则,**详细信息**将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-132">Indicates that **Details** returns S_OK if changes are actually made to the address; otherwise, **Details** returns S_FALSE.</span></span> 
    
<span data-ttu-id="2c4e7-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="2c4e7-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="2c4e7-134">显示 "常用地址" 对话框的模式版本, 该对话框始终显示在非 Outlook 客户端中。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-134">Display the modal version of the common address dialog box, which is always shown in non-Outlook clients.</span></span> <span data-ttu-id="2c4e7-135">此标志与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="2c4e7-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="2c4e7-136">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="2c4e7-137">显示 "常用地址" 对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-137">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="2c4e7-138">对于非 Outlook 客户端, 此标志将被忽略。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-138">This flag is ignored for non-Outlook clients.</span></span> 
    
<span data-ttu-id="2c4e7-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2c4e7-139">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2c4e7-140">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="2c4e7-141">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2c4e7-142">返回值</span><span class="sxs-lookup"><span data-stu-id="2c4e7-142">Return value</span></span>

<span data-ttu-id="2c4e7-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c4e7-143">S_OK</span></span> 
  
> <span data-ttu-id="2c4e7-144">已成功显示通讯簿条目的 "详细信息" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-144">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2c4e7-145">注解</span><span class="sxs-lookup"><span data-stu-id="2c4e7-145">Remarks</span></span>

<span data-ttu-id="2c4e7-146">客户端应用程序调用**详细信息**方法以显示一个对话框, 该对话框提供有关通讯簿中的特定条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-146">Client applications call the **Details** method to display a dialog box that provides details about a particular entry in the address book.</span></span> <span data-ttu-id="2c4e7-147">您可以使用_lpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数将客户端定义的按钮添加到对话框中。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-147">You can use the  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="2c4e7-148">单击该按钮时, MAPI 将调用_lpfButtonCallback_指向的回调函数, 同时传递按钮的条目标识符和_lpvButtonContext_中的数据。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-148">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="2c4e7-149">如果不需要可扩展按钮, _lpszButtonText_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-149">If you do not need an extensible button,  _lpszButtonText_ should be NULL.</span></span> 
  
 <span data-ttu-id="2c4e7-150">**详细信息**支持 Unicode 字符字符串;在将 Unicode 字符串显示在 "详细信息" 对话框中之前, 它们将转换为多字节字符字符串 (MBCS) 格式。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-150">**Details** supports Unicode character strings; Unicode strings are converted to the multibyte character string (MBCS) format before they are displayed in the details dialog box.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2c4e7-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2c4e7-151">MFCMAPI reference</span></span>

<span data-ttu-id="2c4e7-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2c4e7-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="2c4e7-153">**File**</span></span>|<span data-ttu-id="2c4e7-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="2c4e7-154">**Function**</span></span>|<span data-ttu-id="2c4e7-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="2c4e7-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c4e7-156">BaseDialog</span><span class="sxs-lookup"><span data-stu-id="2c4e7-156">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="2c4e7-157">CBaseDialog:: OnOpenEntryID</span><span class="sxs-lookup"><span data-stu-id="2c4e7-157">CBaseDialog::OnOpenEntryID</span></span>  <br/> |<span data-ttu-id="2c4e7-158">MFCMAPI 使用**详细信息**方法显示一个对话框, 其中显示了通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2c4e7-158">MFCMAPI uses the **Details** method to display a dialog box that shows the details for an address book entry.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2c4e7-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c4e7-159">See also</span></span>



[<span data-ttu-id="2c4e7-160">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="2c4e7-160">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="2c4e7-161">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="2c4e7-161">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="2c4e7-162">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="2c4e7-162">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="2c4e7-163">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2c4e7-163">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="2c4e7-164">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2c4e7-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

