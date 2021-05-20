---
title: IMAPIFormMgrResolveMultipleMessageClasses
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.ResolveMultipleMessageClasses
api_type:
- COM
ms.assetid: d3cc6658-e46d-42dd-b1ac-65c88cfef8ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 515061c6c208008c4752e5ff2f23933a4c259c00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428016"
---
# <a name="imapiformmgrresolvemultiplemessageclasses"></a><span data-ttu-id="0246c-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="0246c-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="0246c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0246c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0246c-105">将一组邮件类解析为表单容器中的窗体，并返回这些表单的表单信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="0246c-105">Resolves a group of message classes to their forms within a form container, and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClasses,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="0246c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0246c-106">Parameters</span></span>

 <span data-ttu-id="0246c-107">_pMsgClasses_</span><span class="sxs-lookup"><span data-stu-id="0246c-107">_pMsgClasses_</span></span>
  
> <span data-ttu-id="0246c-108">[in]指向包含要解析的邮件类的名称的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="0246c-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span>
    
 <span data-ttu-id="0246c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="0246c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="0246c-110">[in]控制邮件类解析方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0246c-110">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="0246c-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="0246c-111">The following flag can be set:</span></span>
    
<span data-ttu-id="0246c-112">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="0246c-112">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="0246c-113">仅应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="0246c-113">Only message class strings that are an exact match should be resolved.</span></span>
    
<span data-ttu-id="0246c-114">MAPIFORM_LOCALONLY</span><span class="sxs-lookup"><span data-stu-id="0246c-114">MAPIFORM_LOCALONLY</span></span>
  
> <span data-ttu-id="0246c-115">不包括缓存的表单。</span><span class="sxs-lookup"><span data-stu-id="0246c-115">Do not include cached forms.</span></span>
    
 <span data-ttu-id="0246c-116">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="0246c-116">_pFolderFocus_</span></span>
  
> <span data-ttu-id="0246c-117">[in]指向包含正在解析其邮件类的窗体的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="0246c-117">[in] A pointer to the folder that contains the form whose message class is being resolved.</span></span> <span data-ttu-id="0246c-118">_pFolderFocus_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="0246c-118">The  _pFolderFocus_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="0246c-119">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="0246c-119">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="0246c-120">[out]指向指向表单信息对象数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="0246c-120">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="0246c-121">如果表单查看器在  _pMsgClasses_ 参数中传递 NULL，  _则 ppfrminfoarray_ 参数包含容器中所有表单的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="0246c-121">If a form viewer passes NULL in the  _pMsgClasses_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="0246c-122">返回值</span><span class="sxs-lookup"><span data-stu-id="0246c-122">Return value</span></span>

<span data-ttu-id="0246c-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="0246c-123">S_OK</span></span> 
  
> <span data-ttu-id="0246c-124">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="0246c-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0246c-125">备注</span><span class="sxs-lookup"><span data-stu-id="0246c-125">Remarks</span></span>

<span data-ttu-id="0246c-126">表单查看器调用 **IMAPIFormMgr：：ResolveMultipleMessageClasses** 方法，将一组邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="0246c-126">Form viewers call the **IMAPIFormMgr::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="0246c-127">_ppfrminfoarray_ 中返回的表单信息对象数组提供对每个表单属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="0246c-127">The array of form information objects returned in  _ppfrminfoarray_ provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="0246c-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="0246c-128">Notes to callers</span></span>

<span data-ttu-id="0246c-129">若要将一组邮件类解析为表单，表单查看器会传递要解析的邮件类名称数组。</span><span class="sxs-lookup"><span data-stu-id="0246c-129">To resolve a group of message classes to forms, a form viewer passes in an array of message class names to be resolved.</span></span> <span data-ttu-id="0246c-130">若要强制使解析准确 (即当完全匹配的表单服务器不可用时，阻止解析到邮件类的基类) 可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="0246c-130">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class when an exactly matching form server is not available) the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="0246c-131">邮件类名称始终是 ANSI 字符串，从不为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0246c-131">Message class names are always ANSI strings, never Unicode.</span></span>
  
<span data-ttu-id="0246c-132">如果无法将邮件类解析为窗体，将在窗体信息数组中为邮件类返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="0246c-132">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="0246c-133">因此，即使此方法返回 S_OK，表单查看者也不应假定已成功解析所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="0246c-133">Therefore, even if the method returns S_OK, form viewers should not work on the assumption that all message classes have been successfully resolved.</span></span> <span data-ttu-id="0246c-134">相反，表单查看者应检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="0246c-134">Instead, form viewers should check the values in the returned array.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0246c-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0246c-135">See also</span></span>



[<span data-ttu-id="0246c-136">IMAPIFormMgr::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="0246c-136">IMAPIFormMgr::ResolveMessageClass</span></span>](imapiformmgr-resolvemessageclass.md)
  
[<span data-ttu-id="0246c-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0246c-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

