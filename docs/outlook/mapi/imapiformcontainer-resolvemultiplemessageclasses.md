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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342180"
---
# <a name="imapiformcontainerresolvemultiplemessageclasses"></a><span data-ttu-id="a0fde-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="a0fde-103">IMAPIFormContainer::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="a0fde-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a0fde-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a0fde-105">将一组消息类解析为表单容器中的窗体, 并返回这些窗体的窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="a0fde-105">Resolves a group of message classes to their forms in a form container and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClassArray,
  ULONG ulFlags,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="a0fde-106">参数</span><span class="sxs-lookup"><span data-stu-id="a0fde-106">Parameters</span></span>

 <span data-ttu-id="a0fde-107">_pMsgClassArray_</span><span class="sxs-lookup"><span data-stu-id="a0fde-107">_pMsgClassArray_</span></span>
  
> <span data-ttu-id="a0fde-108">实时指向包含要解析的邮件类的名称的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="a0fde-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span> <span data-ttu-id="a0fde-109">邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a0fde-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="a0fde-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a0fde-110">_ulFlags_</span></span>
  
> <span data-ttu-id="a0fde-111">实时用于控制如何解析邮件类别的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a0fde-111">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="a0fde-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="a0fde-112">The following flag can be set:</span></span>
    
<span data-ttu-id="a0fde-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="a0fde-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="a0fde-114">应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="a0fde-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="a0fde-115">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="a0fde-115">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="a0fde-116">排除指向指向表单信息对象数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a0fde-116">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="a0fde-117">如果客户端应用程序在_pMsgClassArray_参数中传递了 NULL, 则_ppfrminfoarray_参数将包含容器中所有窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="a0fde-117">If a client application passes NULL in the  _pMsgClassArray_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a0fde-118">返回值</span><span class="sxs-lookup"><span data-stu-id="a0fde-118">Return value</span></span>

<span data-ttu-id="a0fde-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0fde-119">S_OK</span></span> 
  
> <span data-ttu-id="a0fde-120">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="a0fde-120">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a0fde-121">注解</span><span class="sxs-lookup"><span data-stu-id="a0fde-121">Remarks</span></span>

<span data-ttu-id="a0fde-122">客户端应用程序调用**IMAPIFormContainer:: ResolveMultipleMessageClasses**方法将一组邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="a0fde-122">Client applications call the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="a0fde-123">_ppfrminfoarray_参数中返回的窗体信息对象的数组提供了对每个窗体属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="a0fde-123">The array of form information objects returned in the  _ppfrminfoarray_ parameter provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="a0fde-124">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="a0fde-124">Notes to callers</span></span>

<span data-ttu-id="a0fde-125">若要将一组邮件类解析为表单, 请传入要解析的邮件类名称的数组。</span><span class="sxs-lookup"><span data-stu-id="a0fde-125">To resolve a group of message classes to forms, pass in an array of message class names to be resolved.</span></span> <span data-ttu-id="a0fde-126">若要强制解决是精确的 (即, 若要防止解析邮件类的基类), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="a0fde-126">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="a0fde-127">如果无法将邮件类别解析为表单, 则在表单信息数组中返回该邮件类别的 NULL。</span><span class="sxs-lookup"><span data-stu-id="a0fde-127">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="a0fde-128">因此, 即使方法返回 S_OK, 也不要假定已成功解决所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="a0fde-128">Therefore, even if the method returns S_OK, do not assume that all message classes have been successfully resolved.</span></span> <span data-ttu-id="a0fde-129">而是检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="a0fde-129">Instead, check the values in the returned array.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="a0fde-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a0fde-130">MFCMAPI reference</span></span>

<span data-ttu-id="a0fde-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a0fde-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a0fde-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="a0fde-132">**File**</span></span>|<span data-ttu-id="a0fde-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="a0fde-133">**Function**</span></span>|<span data-ttu-id="a0fde-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="a0fde-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0fde-135">FormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="a0fde-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="a0fde-136">CFormContainerDlg:: OnResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="a0fde-136">CFormContainerDlg::OnResolveMultipleMessageClasses</span></span>  <br/> |<span data-ttu-id="a0fde-137">MFCMAPI 使用**IMAPIFormContainer:: ResolveMultipleMessageClasses**方法来查找与一组邮件类关联的窗体。</span><span class="sxs-lookup"><span data-stu-id="a0fde-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMultipleMessageClasses** method to locate a form that is associated with a set of message classes.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a0fde-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0fde-138">See also</span></span>



[<span data-ttu-id="a0fde-139">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="a0fde-139">IMAPIFormContainer::ResolveMessageClass</span></span>](imapiformcontainer-resolvemessageclass.md)
  
[<span data-ttu-id="a0fde-140">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a0fde-140">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)


[<span data-ttu-id="a0fde-141">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="a0fde-141">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

