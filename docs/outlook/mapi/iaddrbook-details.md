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
ms.openlocfilehash: fbe7f02555f76532896c951f50648c528c250a58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775259"
---
# <a name="iaddrbookdetails"></a><span data-ttu-id="23268-103">IAddrBook::Details</span><span class="sxs-lookup"><span data-stu-id="23268-103">IAddrBook::Details</span></span>

  
  
<span data-ttu-id="23268-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="23268-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="23268-105">显示一个对话框，显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="23268-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="23268-106">参数</span><span class="sxs-lookup"><span data-stu-id="23268-106">Parameters</span></span>

 <span data-ttu-id="23268-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="23268-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="23268-108">[in]指向对话框中的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="23268-108">[in] A pointer to a handle of the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="23268-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="23268-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="23268-110">[in]一个指向基于[DISMISSMODELESS](dismissmodeless.md)原型或为空的一个函数指针。</span><span class="sxs-lookup"><span data-stu-id="23268-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="23268-111">此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="23268-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="23268-112">MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫**详细信息**对话框中不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="23268-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="23268-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="23268-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="23268-114">[in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="23268-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="23268-115">此参数仅适用于无模式版本的对话框中，通过_ulFlags_参数中包括 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="23268-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="23268-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="23268-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="23268-117">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="23268-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="23268-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="23268-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="23268-119">[in]指向要显示其详细信息的条目的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="23268-119">[in] A pointer to the entry identifier for the entry for which details are displayed.</span></span>
    
 <span data-ttu-id="23268-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="23268-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="23268-121">[in]基于[LPFNBUTTON](lpfnbutton.md)函数原型函数指针。</span><span class="sxs-lookup"><span data-stu-id="23268-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="23268-122">**LPFNBUTTON**函数将按钮添加到详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="23268-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="23268-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="23268-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="23268-124">[in]指向作为参数指定由_lpfButtonCallback_参数的函数使用的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="23268-124">[in] A pointer to data that was used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="23268-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="23268-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="23268-126">[in]指向一个字符串，包含要应用于添加按钮，文本是否可扩展该按钮的指针。</span><span class="sxs-lookup"><span data-stu-id="23268-126">[in] A pointer to a string that contains text to be applied to the added button, if that button is extensible.</span></span> <span data-ttu-id="23268-127">_LpszButtonText_参数应为 NULL，如果您不需要的可扩展的按钮。</span><span class="sxs-lookup"><span data-stu-id="23268-127">The  _lpszButtonText_ parameter should be NULL if you do not need an extensible button.</span></span> 
    
 <span data-ttu-id="23268-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="23268-128">_ulFlags_</span></span>
  
> <span data-ttu-id="23268-129">[in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="23268-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="23268-130">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="23268-130">The following flags can be set:</span></span> 
    
<span data-ttu-id="23268-131">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="23268-131">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="23268-132">指示的**详细信息**，则返回 S_OK 如果进行了更改实际的地址;否则，**详细信息**返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="23268-132">Indicates that **Details** returns S_OK if changes are actually made to the address; otherwise, **Details** returns S_FALSE.</span></span> 
    
<span data-ttu-id="23268-133">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="23268-133">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="23268-134">显示通用的地址对话框，其中始终显示非 Outlook 客户端中的模式版本。</span><span class="sxs-lookup"><span data-stu-id="23268-134">Display the modal version of the common address dialog box, which is always shown in non-Outlook clients.</span></span> <span data-ttu-id="23268-135">此标志是与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="23268-135">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="23268-136">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="23268-136">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="23268-137">显示通用的地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="23268-137">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="23268-138">非 Outlook 客户端，则忽略此标志。</span><span class="sxs-lookup"><span data-stu-id="23268-138">This flag is ignored for non-Outlook clients.</span></span> 
    
<span data-ttu-id="23268-139">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="23268-139">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="23268-140">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="23268-140">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="23268-141">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="23268-141">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="23268-142">返回值</span><span class="sxs-lookup"><span data-stu-id="23268-142">Return value</span></span>

<span data-ttu-id="23268-143">S_OK</span><span class="sxs-lookup"><span data-stu-id="23268-143">S_OK</span></span> 
  
> <span data-ttu-id="23268-144">成功的通讯簿条目显示详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="23268-144">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="23268-145">说明</span><span class="sxs-lookup"><span data-stu-id="23268-145">Remarks</span></span>

<span data-ttu-id="23268-146">客户端应用程序调用以显示一个对话框，提供了有关在通讯簿中的特定条目的详细信息， **Details**方法。</span><span class="sxs-lookup"><span data-stu-id="23268-146">Client applications call the **Details** method to display a dialog box that provides details about a particular entry in the address book.</span></span> <span data-ttu-id="23268-147">_LpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数用于将客户端定义按钮添加到对话框。</span><span class="sxs-lookup"><span data-stu-id="23268-147">You can use the  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="23268-148">单击按钮时，MAPI 调用的回调函数所指的_lpfButtonCallback_， _lpvButtonContext_中传递按钮和数据的项标识符。</span><span class="sxs-lookup"><span data-stu-id="23268-148">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="23268-149">如果您不需要的可扩展的按钮， _lpszButtonText_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="23268-149">If you do not need an extensible button,  _lpszButtonText_ should be NULL.</span></span> 
  
 <span data-ttu-id="23268-150">**详细信息**支持 Unicode 字符的字符串;Unicode 字符串转换为多字节字符的字符串 (MBCS) 格式显示在详细信息对话框之前。</span><span class="sxs-lookup"><span data-stu-id="23268-150">**Details** supports Unicode character strings; Unicode strings are converted to the multibyte character string (MBCS) format before they are displayed in the details dialog box.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="23268-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="23268-151">MFCMAPI reference</span></span>

<span data-ttu-id="23268-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="23268-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="23268-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="23268-153">**File**</span></span>|<span data-ttu-id="23268-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="23268-154">**Function**</span></span>|<span data-ttu-id="23268-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="23268-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="23268-156">BaseDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="23268-156">BaseDialog.cpp</span></span>  <br/> |<span data-ttu-id="23268-157">CBaseDialog::OnOpenEntryID</span><span class="sxs-lookup"><span data-stu-id="23268-157">CBaseDialog::OnOpenEntryID</span></span>  <br/> |<span data-ttu-id="23268-158">MFCMAPI 使用， **Details**方法显示一个对话框，显示的通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="23268-158">MFCMAPI uses the **Details** method to display a dialog box that shows the details for an address book entry.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="23268-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23268-159">See also</span></span>



[<span data-ttu-id="23268-160">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="23268-160">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="23268-161">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="23268-161">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="23268-162">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="23268-162">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="23268-163">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="23268-163">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)


[<span data-ttu-id="23268-164">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="23268-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

