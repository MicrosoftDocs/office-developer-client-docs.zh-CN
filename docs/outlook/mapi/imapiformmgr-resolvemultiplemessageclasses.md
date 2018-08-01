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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ad2014d1d003a4d80646ed1b679f0d3827341c1b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775427"
---
# <a name="imapiformmgrresolvemultiplemessageclasses"></a><span data-ttu-id="47bbd-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="47bbd-103">IMAPIFormMgr::ResolveMultipleMessageClasses</span></span>

  
  
<span data-ttu-id="47bbd-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="47bbd-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="47bbd-105">将一组的邮件类解析为其的窗体中的窗体容器中，并返回这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="47bbd-105">Resolves a group of message classes to their forms within a form container, and returns an array of form information objects for those forms.</span></span>
  
```cpp
HRESULT ResolveMultipleMessageClasses(
  LPSMESSAGECLASSARRAY pMsgClasses,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPSMAPIFORMINFOARRAY FAR * ppfrminfoarray
);
```

## <a name="parameters"></a><span data-ttu-id="47bbd-106">参数</span><span class="sxs-lookup"><span data-stu-id="47bbd-106">Parameters</span></span>

 <span data-ttu-id="47bbd-107">_pMsgClasses_</span><span class="sxs-lookup"><span data-stu-id="47bbd-107">_pMsgClasses_</span></span>
  
> <span data-ttu-id="47bbd-108">[in]一个指向数组，其中包含的邮件类来解析名称。</span><span class="sxs-lookup"><span data-stu-id="47bbd-108">[in] A pointer to an array that contains the names of the message classes to resolve.</span></span>
    
 <span data-ttu-id="47bbd-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="47bbd-109">_ulFlags_</span></span>
  
> <span data-ttu-id="47bbd-110">[in]位掩码的标志的控制解析的邮件类的方式。</span><span class="sxs-lookup"><span data-stu-id="47bbd-110">[in] A bitmask of flags that controls how the message classes are resolved.</span></span> <span data-ttu-id="47bbd-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="47bbd-111">The following flag can be set:</span></span>
    
<span data-ttu-id="47bbd-112">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="47bbd-112">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="47bbd-113">应解决仅邮件类的字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="47bbd-113">Only message class strings that are an exact match should be resolved.</span></span>
    
<span data-ttu-id="47bbd-114">MAPIFORM_LOCALONLY</span><span class="sxs-lookup"><span data-stu-id="47bbd-114">MAPIFORM_LOCALONLY</span></span>
  
> <span data-ttu-id="47bbd-115">不包括缓存窗体。</span><span class="sxs-lookup"><span data-stu-id="47bbd-115">Do not include cached forms.</span></span>
    
 <span data-ttu-id="47bbd-116">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="47bbd-116">_pFolderFocus_</span></span>
  
> <span data-ttu-id="47bbd-117">[in]一个指向包含正在解析其邮件类的窗体的文件夹。</span><span class="sxs-lookup"><span data-stu-id="47bbd-117">[in] A pointer to the folder that contains the form whose message class is being resolved.</span></span> <span data-ttu-id="47bbd-118">_PFolderFocus_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="47bbd-118">The  _pFolderFocus_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="47bbd-119">_ppfrminfoarray_</span><span class="sxs-lookup"><span data-stu-id="47bbd-119">_ppfrminfoarray_</span></span>
  
> <span data-ttu-id="47bbd-120">[输出]指向为数组表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="47bbd-120">[out] A pointer to a pointer to an array of form information objects.</span></span> <span data-ttu-id="47bbd-121">如果表单查看器中_pMsgClasses_参数传递 NULL， _ppfrminfoarray_参数包含容器中的所有窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="47bbd-121">If a form viewer passes NULL in the  _pMsgClasses_ parameter, the  _ppfrminfoarray_ parameter contains form information objects for all forms in the container.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="47bbd-122">返回值</span><span class="sxs-lookup"><span data-stu-id="47bbd-122">Return value</span></span>

<span data-ttu-id="47bbd-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="47bbd-123">S_OK</span></span> 
  
> <span data-ttu-id="47bbd-124">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="47bbd-124">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="47bbd-125">说明</span><span class="sxs-lookup"><span data-stu-id="47bbd-125">Remarks</span></span>

<span data-ttu-id="47bbd-126">表单查看器调用**IMAPIFormMgr::ResolveMultipleMessageClasses**方法解析为窗体容器内的窗体的邮件类的组。</span><span class="sxs-lookup"><span data-stu-id="47bbd-126">Form viewers call the **IMAPIFormMgr::ResolveMultipleMessageClasses** method to resolve a group of message classes to forms within a form container.</span></span> <span data-ttu-id="47bbd-127">窗体信息对象_ppfrminfoarray_中返回的数组进一步提供对每个窗体的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="47bbd-127">The array of form information objects returned in  _ppfrminfoarray_ provides further access to each of the forms' properties.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="47bbd-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="47bbd-128">Notes to callers</span></span>

<span data-ttu-id="47bbd-129">若要解决窗体的邮件类的组，表单查看器将传递数组中的邮件类名称解析。</span><span class="sxs-lookup"><span data-stu-id="47bbd-129">To resolve a group of message classes to forms, a form viewer passes in an array of message class names to be resolved.</span></span> <span data-ttu-id="47bbd-130">若要强制为完全的分辨率 （即，以防止解决方案时完全匹配的窗体的邮件类的基类服务器不可用） 可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="47bbd-130">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class when an exactly matching form server is not available) the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="47bbd-131">邮件类名称始终都是 ANSI 字符串，从不 Unicode。</span><span class="sxs-lookup"><span data-stu-id="47bbd-131">Message class names are always ANSI strings, never Unicode.</span></span>
  
<span data-ttu-id="47bbd-132">如果邮件类无法解析到窗体，窗体信息数组中的邮件类将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="47bbd-132">If a message class cannot be resolved to a form, NULL is returned for that message class in the form information array.</span></span> <span data-ttu-id="47bbd-133">因此，即使该方法返回 S_OK，表单查看器应不工作假定已成功解析的所有邮件类。</span><span class="sxs-lookup"><span data-stu-id="47bbd-133">Therefore, even if the method returns S_OK, form viewers should not work on the assumption that all message classes have been successfully resolved.</span></span> <span data-ttu-id="47bbd-134">相反，表单查看器应检查返回的数组中的值。</span><span class="sxs-lookup"><span data-stu-id="47bbd-134">Instead, form viewers should check the values in the returned array.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47bbd-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47bbd-135">See also</span></span>



[<span data-ttu-id="47bbd-136">IMAPIFormMgr::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="47bbd-136">IMAPIFormMgr::ResolveMessageClass</span></span>](imapiformmgr-resolvemessageclass.md)
  
[<span data-ttu-id="47bbd-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="47bbd-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

