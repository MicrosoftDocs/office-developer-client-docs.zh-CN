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
# <a name="imapiformmgrresolvemultiplemessageclasses"></a><span data-ttu-id="c4008-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="c4008-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="c4008-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4008-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4008-105">将一组消息类解析为表单容器中的表单, 并返回这些表单的表单信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="c4008-105">Resolves a group of message classes to their forms within a form container, and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClasses,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="c4008-106">参数</span><span class="sxs-lookup"><span data-stu-id="c4008-106">Parameters</span></span>

 <span data-ttu-id="c4008-107">_pMsgClasses_</span><span class="sxs-lookup"><span data-stu-id="c4008-107">_pMsgClasses_</span></span>
  
> <span data-ttu-id="c4008-108">实时指向包含要解析的邮件类的名称的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="c4008-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span>
    
 <span data-ttu-id="c4008-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c4008-109">_ulFlags_</span></span>
  
> <span data-ttu-id="c4008-110">实时用于控制如何解析邮件类别的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c4008-110">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="c4008-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="c4008-111">The following flag can be set:</span></span>
    
<span data-ttu-id="c4008-112">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="c4008-112">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="c4008-113">应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="c4008-113">Only message class strings that are an exact match should be resolved.</span></span>
    
<span data-ttu-id="c4008-114">MAPIFORM_LOCALONLY</span><span class="sxs-lookup"><span data-stu-id="c4008-114">MAPIFORM_LOCALONLY</span></span>
  
> <span data-ttu-id="c4008-115">不包含缓存的窗体。</span><span class="sxs-lookup"><span data-stu-id="c4008-115">Do not include cached forms.</span></span>
    
 <span data-ttu-id="c4008-116">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="c4008-116">_pFolderFocus_</span></span>
  
> <span data-ttu-id="c4008-117">实时指向文件夹的指针, 该文件夹包含要解析其邮件类的窗体。</span><span class="sxs-lookup"><span data-stu-id="c4008-117">[in] A pointer to the folder that contains the form whose message class is being resolved.</span></span> <span data-ttu-id="c4008-118">_pFolderFocus_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c4008-118">The  _pFolderFocus_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="c4008-119">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="c4008-119">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="c4008-120">排除指向指向表单信息对象数组的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c4008-120">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="c4008-121">如果表单查看器在_pMsgClasses_参数中传递了 NULL, 则_ppfrminfoarray_参数将包含容器中所有表单的表单信息对象。</span><span class="sxs-lookup"><span data-stu-id="c4008-121">If a form viewer passes NULL in the  _pMsgClasses_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="c4008-122">返回值</span><span class="sxs-lookup"><span data-stu-id="c4008-122">Return value</span></span>

<span data-ttu-id="c4008-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="c4008-123">S_OK</span></span> 
  
> <span data-ttu-id="c4008-124">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="c4008-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c4008-125">说明</span><span class="sxs-lookup"><span data-stu-id="c4008-125">Remarks</span></span>

<span data-ttu-id="c4008-126">表单查看者调用**IMAPIFormMgr:: ResolveMultipleMessageClasses**方法将一组邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="c4008-126">Form viewers call the **IMAPIFormMgr::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="c4008-127">_ppfrminfoarray_中返回的表单信息对象的数组提供了对每个表单属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="c4008-127">The array of form information objects returned in  _ppfrminfoarray_ provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c4008-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c4008-128">Notes to callers</span></span>

<span data-ttu-id="c4008-129">若要将一组邮件类解析为表单, 表单查看器将传入要解析的邮件类名称的数组。</span><span class="sxs-lookup"><span data-stu-id="c4008-129">To resolve a group of message classes to forms, a form viewer passes in an array of message class names to be resolved.</span></span> <span data-ttu-id="c4008-130">若要强制解决方法是否完全 (即, 若要在完全匹配的窗体服务器不可用时防止解析为邮件类的基类), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="c4008-130">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class when an exactly matching form server is not available) the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="c4008-131">邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c4008-131">Message class names are always ANSI strings, never Unicode.</span></span>
  
<span data-ttu-id="c4008-132">如果无法将邮件类别解析为表单, 则在表单信息数组中返回该邮件类别的 NULL。</span><span class="sxs-lookup"><span data-stu-id="c4008-132">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="c4008-133">因此, 即使该方法返回 S_OK, 表单查看器也不应假设已成功解决所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="c4008-133">Therefore, even if the method returns S_OK, form viewers should not work on the assumption that all message classes have been successfully resolved.</span></span> <span data-ttu-id="c4008-134">相反, 表单查看器应检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="c4008-134">Instead, form viewers should check the values in the returned array.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4008-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4008-135">See also</span></span>



[<span data-ttu-id="c4008-136">IMAPIFormMgr::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="c4008-136">IMAPIFormMgr::ResolveMessageClass</span></span>](imapiformmgr-resolvemessageclass.md)
  
[<span data-ttu-id="c4008-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c4008-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

