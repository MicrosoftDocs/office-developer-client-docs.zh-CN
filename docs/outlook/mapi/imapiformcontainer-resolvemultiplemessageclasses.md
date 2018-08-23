---
title: IMAPIFormContainerResolveMultipleMessageClasses
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.ResolveMultipleMessageCla
api_type:
- COM
ms.assetid: f18c2dd1-366f-48b4-b335-ebbc0651f467
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 002dbf3e898fc0388d535e3087d17ba37d63201e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577707"
---
# <a name="imapiformcontainerresolvemultiplemessageclasses"></a><span data-ttu-id="c28a3-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="c28a3-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="c28a3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c28a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c28a3-105">解析为其在窗体容器中的窗体的邮件类的一组，并返回这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="c28a3-105">Resolves a group of message classes to their forms in a form container and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClassArray,
  ULONG ulFlags,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="c28a3-106">参数</span><span class="sxs-lookup"><span data-stu-id="c28a3-106">Parameters</span></span>

 <span data-ttu-id="c28a3-107">_pMsgClassArray_</span><span class="sxs-lookup"><span data-stu-id="c28a3-107">_pMsgClassArray_</span></span>
  
> <span data-ttu-id="c28a3-108">[in]一个指向数组，其中包含的邮件类来解析名称。</span><span class="sxs-lookup"><span data-stu-id="c28a3-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span> <span data-ttu-id="c28a3-109">邮件类名称始终都是 ANSI 字符串，从不 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c28a3-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="c28a3-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c28a3-110">_ulFlags_</span></span>
  
> <span data-ttu-id="c28a3-111">[in]位掩码的标志的控制解析的邮件类的方式。</span><span class="sxs-lookup"><span data-stu-id="c28a3-111">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="c28a3-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="c28a3-112">The following flag can be set:</span></span>
    
<span data-ttu-id="c28a3-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="c28a3-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="c28a3-114">应解决仅邮件类的字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="c28a3-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="c28a3-115">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="c28a3-115">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="c28a3-116">[输出]指向为数组表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c28a3-116">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="c28a3-117">如果客户端应用程序中的_pMsgClassArray_参数传递 NULL，则_ppfrminfoarray_参数包含容器中的所有窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="c28a3-117">If a client application passes NULL in the  _pMsgClassArray_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c28a3-118">返回值</span><span class="sxs-lookup"><span data-stu-id="c28a3-118">Return value</span></span>

<span data-ttu-id="c28a3-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="c28a3-119">S_OK</span></span> 
  
> <span data-ttu-id="c28a3-120">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="c28a3-120">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c28a3-121">注解</span><span class="sxs-lookup"><span data-stu-id="c28a3-121">Remarks</span></span>

<span data-ttu-id="c28a3-122">客户端应用程序调用**IMAPIFormContainer::ResolveMultipleMessageClasses**方法解析为窗体容器内的窗体的邮件类的组。</span><span class="sxs-lookup"><span data-stu-id="c28a3-122">Client applications call the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="c28a3-123">返回_ppfrminfoarray_参数中的窗体信息对象的数组进一步提供对每个窗体的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="c28a3-123">The array of form information objects returned in the  _ppfrminfoarray_ parameter provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c28a3-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c28a3-124">Notes to callers</span></span>

<span data-ttu-id="c28a3-125">若要解决窗体的邮件类的组，传递数组中的邮件类名称解析。</span><span class="sxs-lookup"><span data-stu-id="c28a3-125">To resolve a group of message classes to forms, pass in an array of message class names to be resolved.</span></span> <span data-ttu-id="c28a3-126">强制为完全的分辨率 (即，以防止对的邮件类的基类的分辨率)，可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="c28a3-126">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="c28a3-127">如果邮件类无法解析到窗体，窗体信息数组中的邮件类将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="c28a3-127">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="c28a3-128">因此，即使该方法返回 S_OK，不要假定已成功解析的所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="c28a3-128">Therefore, even if the method returns S_OK, do not assume that all message classes have been successfully resolved.</span></span> <span data-ttu-id="c28a3-129">相反，检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="c28a3-129">Instead, check the values in the returned array.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c28a3-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c28a3-130">MFCMAPI reference</span></span>

<span data-ttu-id="c28a3-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c28a3-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c28a3-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="c28a3-132">**File**</span></span>|<span data-ttu-id="c28a3-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="c28a3-133">**Function**</span></span>|<span data-ttu-id="c28a3-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c28a3-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c28a3-135">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="c28a3-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="c28a3-136">CFormContainerDlg::OnResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="c28a3-136">CFormContainerDlg::OnResolveMultipleMessageClasses</span></span>  <br/> |<span data-ttu-id="c28a3-137">MFCMAPI 使用**IMAPIFormContainer::ResolveMultipleMessageClasses**方法查找与一组的邮件类关联的表单。</span><span class="sxs-lookup"><span data-stu-id="c28a3-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to locate a form that is associated with a set of message classes.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c28a3-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c28a3-138">See also</span></span>



[<span data-ttu-id="c28a3-139">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="c28a3-139">IMAPIFormContainer::ResolveMessageClass</span></span>](imapiformcontainer-resolvemessageclass.md)
  
[<span data-ttu-id="c28a3-140">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c28a3-140">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="c28a3-141">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c28a3-141">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

