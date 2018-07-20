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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 9923813d821e2b34497e3b498c19ce22ceda2eb0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775597"
---
# <a name="imapisupportdetails"></a><span data-ttu-id="b6032-103">IMAPISupport::Details</span><span class="sxs-lookup"><span data-stu-id="b6032-103">IMAPISupport::Details</span></span>

  
  
<span data-ttu-id="b6032-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b6032-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b6032-105">显示一个对话框，显示有关特定通讯簿条目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6032-105">Displays a dialog box that shows details about a particular address book entry.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="b6032-106">参数</span><span class="sxs-lookup"><span data-stu-id="b6032-106">Parameters</span></span>

 <span data-ttu-id="b6032-107">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b6032-107">_lpulUIParam_</span></span>
  
> <span data-ttu-id="b6032-108">[输出]指向返回对话框的父窗口的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-108">[out] A pointer to the handle to the parent window of the returned dialog box.</span></span>
    
 <span data-ttu-id="b6032-109">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="b6032-109">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="b6032-110">[in]一个指向基于[DISMISSMODELESS](dismissmodeless.md)原型或为空的一个函数指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-110">[in] A pointer to a function based on the [DISMISSMODELESS](dismissmodeless.md) prototype, or NULL.</span></span> <span data-ttu-id="b6032-111">此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="b6032-111">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="b6032-112">MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫**IMAPISupport::Details**对话框中不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b6032-112">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling **IMAPISupport::Details** that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="b6032-113">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="b6032-113">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="b6032-114">[in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-114">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="b6032-115">此参数仅适用于无模式版本的对话框中，通过_ulFlags_参数中包括 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="b6032-115">This parameter applies only to the modeless version of the dialog box, by including the DIALOG_SDI flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b6032-116">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b6032-116">_cbEntryID_</span></span>
  
> <span data-ttu-id="b6032-117">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="b6032-117">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b6032-118">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b6032-118">_lpEntryID_</span></span>
  
> <span data-ttu-id="b6032-119">[in]指向要显示其详细信息的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-119">[in] A pointer to the entry identifier for which details are displayed.</span></span>
    
 <span data-ttu-id="b6032-120">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="b6032-120">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="b6032-121">[in]基于[LPFNBUTTON](lpfnbutton.md)函数原型函数指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-121">[in] A pointer to a function based on the [LPFNBUTTON](lpfnbutton.md) function prototype.</span></span> <span data-ttu-id="b6032-122">**LPFNBUTTON**函数将按钮添加到详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="b6032-122">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="b6032-123">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="b6032-123">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="b6032-124">[in]指向作为参数用于指定_lpfButtonCallback_参数的函数的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="b6032-124">[in] A pointer to data used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="b6032-125">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="b6032-125">_lpszButtonText_</span></span>
  
> <span data-ttu-id="b6032-126">[in]一个指向一个字符串，包含文本可扩展该按钮时要应用于添加按钮。</span><span class="sxs-lookup"><span data-stu-id="b6032-126">[in] A pointer to a string that contains text to be applied to the added button if that button is extensible.</span></span> <span data-ttu-id="b6032-127">_LpszButtonText_参数应为 NULL，如果不需要的可扩展的按钮。</span><span class="sxs-lookup"><span data-stu-id="b6032-127">The  _lpszButtonText_ parameter should be NULL if an extensible button is not needed.</span></span> 
    
 <span data-ttu-id="b6032-128">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b6032-128">_ulFlags_</span></span>
  
> <span data-ttu-id="b6032-129">[in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="b6032-129">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="b6032-130">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b6032-130">The following flag can be set:</span></span> 
    
<span data-ttu-id="b6032-131">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="b6032-131">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="b6032-132">显示通用的地址对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="b6032-132">Display the modal version of the common address dialog box.</span></span> <span data-ttu-id="b6032-133">此标志是与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="b6032-133">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="b6032-134">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="b6032-134">DIALOG_SDI</span></span>
  
>  <span data-ttu-id="b6032-135">显示通用的地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="b6032-135">Display the modeless version of the common address dialog box.</span></span> <span data-ttu-id="b6032-136">此标志是与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="b6032-136">This flag is mutually exclusive with DIALOG_MODAL.</span></span> 
    
<span data-ttu-id="b6032-137">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b6032-137">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b6032-138">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b6032-138">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="b6032-139">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b6032-139">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b6032-140">返回值</span><span class="sxs-lookup"><span data-stu-id="b6032-140">Return value</span></span>

<span data-ttu-id="b6032-141">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6032-141">S_OK</span></span> 
  
> <span data-ttu-id="b6032-142">成功的通讯簿条目显示详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="b6032-142">The details dialog box was successfully displayed for the address book entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b6032-143">备注</span><span class="sxs-lookup"><span data-stu-id="b6032-143">Remarks</span></span>

<span data-ttu-id="b6032-144">对于通讯簿提供程序支持对象实现**IMAPISupport::Details**方法。</span><span class="sxs-lookup"><span data-stu-id="b6032-144">The **IMAPISupport::Details** method is implemented for address book provider support objects.</span></span> <span data-ttu-id="b6032-145">通讯簿提供程序呼叫**详细信息**，以显示一个对话框，提供有关在通讯簿中的特定条目详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6032-145">Address book providers call **Details** to display a dialog box that gives details on a particular entry in the address book.</span></span> <span data-ttu-id="b6032-146">_LpfButtonCallback_、 _lpvButtonContext_和_lpszButtonText_参数可用于将客户端定义按钮添加到对话框。</span><span class="sxs-lookup"><span data-stu-id="b6032-146">The  _lpfButtonCallback_,  _lpvButtonContext_, and  _lpszButtonText_ parameters can be used to add a client-defined button to the dialog box.</span></span> <span data-ttu-id="b6032-147">单击按钮时，MAPI 调用的回调函数所指的_lpfButtonCallback_， _lpvButtonContext_中传递按钮和数据的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b6032-147">When the button is clicked, MAPI calls the callback function pointed to by  _lpfButtonCallback_, passing both the entry identifier of the button and the data in  _lpvButtonContext_.</span></span> <span data-ttu-id="b6032-148">如果不需要的可扩展的按钮， _lpszButtonText_应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b6032-148">If an extensible button is not needed,  _lpszButtonText_ should be NULL.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b6032-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6032-149">See also</span></span>



[<span data-ttu-id="b6032-150">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="b6032-150">ADRPARM</span></span>](adrparm.md)
  
[<span data-ttu-id="b6032-151">IMAPISupport::Address</span><span class="sxs-lookup"><span data-stu-id="b6032-151">IMAPISupport::Address</span></span>](imapisupport-address.md)
  
[<span data-ttu-id="b6032-152">LPFNBUTTON</span><span class="sxs-lookup"><span data-stu-id="b6032-152">LPFNBUTTON</span></span>](lpfnbutton.md)
  
[<span data-ttu-id="b6032-153">IMAPISupport: IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6032-153">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
