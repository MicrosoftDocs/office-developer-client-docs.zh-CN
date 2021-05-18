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
ms.openlocfilehash: 0730da9c3877985853e2cd0a55420e64fbd98e0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412539"
---
# <a name="imapiformcontainerresolvemultiplemessageclasses"></a><span data-ttu-id="17a06-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="17a06-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="17a06-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17a06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17a06-105">将一组邮件类解析为表单容器中的窗体，并返回这些表单的表单信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="17a06-105">Resolves a group of message classes to their forms in a form container and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClassArray,
  ULONG ulFlags,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="17a06-106">参数</span><span class="sxs-lookup"><span data-stu-id="17a06-106">Parameters</span></span>

 <span data-ttu-id="17a06-107">_pMsgClassArray_</span><span class="sxs-lookup"><span data-stu-id="17a06-107">_pMsgClassArray_</span></span>
  
> <span data-ttu-id="17a06-108">[in]指向包含要解析的邮件类的名称的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="17a06-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span> <span data-ttu-id="17a06-109">邮件类名称始终是 ANSI 字符串，从不为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="17a06-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="17a06-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="17a06-110">_ulFlags_</span></span>
  
> <span data-ttu-id="17a06-111">[in]控制邮件类解析方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="17a06-111">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="17a06-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="17a06-112">The following flag can be set:</span></span>
    
<span data-ttu-id="17a06-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="17a06-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="17a06-114">仅应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="17a06-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="17a06-115">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="17a06-115">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="17a06-116">[out]指向指向表单信息对象数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="17a06-116">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="17a06-117">如果客户端应用程序在  _pMsgClassArray_ 参数中传递 NULL，  _则 ppfrminfoarray_ 参数包含容器中所有表单的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="17a06-117">If a client application passes NULL in the  _pMsgClassArray_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="17a06-118">返回值</span><span class="sxs-lookup"><span data-stu-id="17a06-118">Return value</span></span>

<span data-ttu-id="17a06-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="17a06-119">S_OK</span></span> 
  
> <span data-ttu-id="17a06-120">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="17a06-120">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="17a06-121">备注</span><span class="sxs-lookup"><span data-stu-id="17a06-121">Remarks</span></span>

<span data-ttu-id="17a06-122">客户端应用程序调用 **IMAPIFormContainer：：ResolveMultipleMessageClasses** 方法，将一组邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="17a06-122">Client applications call the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="17a06-123">_ppfrminfoarray_ 参数中返回的表单信息对象数组提供对表单的每个属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="17a06-123">The array of form information objects returned in the  _ppfrminfoarray_ parameter provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="17a06-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="17a06-124">Notes to callers</span></span>

<span data-ttu-id="17a06-125">若要将一组邮件类解析为窗体，请传递要解析的邮件类名称数组。</span><span class="sxs-lookup"><span data-stu-id="17a06-125">To resolve a group of message classes to forms, pass in an array of message class names to be resolved.</span></span> <span data-ttu-id="17a06-126">若要强制使解析准确 (即，若要阻止解析到邮件类) 的基类，可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="17a06-126">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="17a06-127">如果无法将邮件类解析为窗体，将在窗体信息数组中为邮件类返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="17a06-127">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="17a06-128">因此，即使该方法返回 S_OK，也不要假定已成功解析所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="17a06-128">Therefore, even if the method returns S_OK, do not assume that all message classes have been successfully resolved.</span></span> <span data-ttu-id="17a06-129">相反，请检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="17a06-129">Instead, check the values in the returned array.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="17a06-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="17a06-130">MFCMAPI reference</span></span>

<span data-ttu-id="17a06-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="17a06-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="17a06-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="17a06-132">**File**</span></span>|<span data-ttu-id="17a06-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="17a06-133">**Function**</span></span>|<span data-ttu-id="17a06-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="17a06-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="17a06-135">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="17a06-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="17a06-136">CFormContainerDlg：：OnResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="17a06-136">CFormContainerDlg::OnResolveMultipleMessageClasses</span></span>  <br/> |<span data-ttu-id="17a06-137">MFCMAPI 使用 **IMAPIFormContainer：：ResolveMultipleMessageClasses** 方法来查找与一组邮件类关联的表单。</span><span class="sxs-lookup"><span data-stu-id="17a06-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to locate a form that is associated with a set of message classes.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="17a06-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17a06-138">See also</span></span>



[<span data-ttu-id="17a06-139">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="17a06-139">IMAPIFormContainer::ResolveMessageClass</span></span>](imapiformcontainer-resolvemessageclass.md)
  
[<span data-ttu-id="17a06-140">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="17a06-140">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="17a06-141">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="17a06-141">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

