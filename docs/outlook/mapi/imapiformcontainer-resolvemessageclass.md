---
title: IMAPIFormContainerResolveMessageClass
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer.ResolveMessageClass
api_type:
- COM
ms.assetid: 9ce13f11-5787-4ea5-a84f-b1e3824529ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c0954d6f8b14b4088ece2ac276b045b6c163ed98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408549"
---
# <a name="imapiformcontainerresolvemessageclass"></a><span data-ttu-id="b7d03-103">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="b7d03-103">IMAPIFormContainer::ResolveMessageClass</span></span>

  
  
<span data-ttu-id="b7d03-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b7d03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b7d03-105">将邮件类解析为窗体容器中的邮件类，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="b7d03-105">Resolves a message class to its form in a form container and returns a form information object for that form.</span></span>
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMessageClass,
  ULONG ulFlags,
  LPMAPIFORMINFO FAR * ppforminfo
);
```

## <a name="parameters"></a><span data-ttu-id="b7d03-106">参数</span><span class="sxs-lookup"><span data-stu-id="b7d03-106">Parameters</span></span>

 <span data-ttu-id="b7d03-107">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="b7d03-107">_szMessageClass_</span></span>
  
> <span data-ttu-id="b7d03-108">[in]一个字符串，用于命名要解析的邮件类。</span><span class="sxs-lookup"><span data-stu-id="b7d03-108">[in] A string that names the message class being resolved.</span></span> <span data-ttu-id="b7d03-109">邮件类名称始终是 ANSI 字符串，从不为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="b7d03-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="b7d03-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b7d03-110">_ulFlags_</span></span>
  
> <span data-ttu-id="b7d03-111">[in]控制如何解析邮件类的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b7d03-111">[in] A bitmask of flags that controls how the message class is resolved.</span></span> <span data-ttu-id="b7d03-112">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b7d03-112">The following flag can be set:</span></span>
    
<span data-ttu-id="b7d03-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="b7d03-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="b7d03-114">仅应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="b7d03-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="b7d03-115">_ppforminfo_</span><span class="sxs-lookup"><span data-stu-id="b7d03-115">_ppforminfo_</span></span>
  
> <span data-ttu-id="b7d03-116">[out]指向返回的表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b7d03-116">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b7d03-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b7d03-117">Return value</span></span>

<span data-ttu-id="b7d03-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7d03-118">S_OK</span></span> 
  
> <span data-ttu-id="b7d03-119">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="b7d03-119">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="b7d03-120">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="b7d03-120">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="b7d03-121">在  _szMessageClass_ 参数中传递的邮件类与表单容器中任何窗体的邮件类不匹配。</span><span class="sxs-lookup"><span data-stu-id="b7d03-121">The message class passed in the  _szMessageClass_ parameter does not match the message class for any form in the form container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b7d03-122">备注</span><span class="sxs-lookup"><span data-stu-id="b7d03-122">Remarks</span></span>

<span data-ttu-id="b7d03-123">客户端应用程序调用 **IMAPIFormContainer：：ResolveMessageClass** 方法将邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="b7d03-123">Client applications call the **IMAPIFormContainer::ResolveMessageClass** method to resolve a message class to a form within a form container.</span></span> <span data-ttu-id="b7d03-124">_ppforminfo_ 参数中返回的表单信息对象提供对具有给定邮件类的表单属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="b7d03-124">The form information object returned in the  _ppforminfo_ parameter provides further access to the properties of the form with the given message class.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b7d03-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b7d03-125">Notes to callers</span></span>

<span data-ttu-id="b7d03-126">若要将邮件类解析为窗体，请传递要解析的邮件类的名称 (例如  `IPM.HelpDesk.Software` ，) 。</span><span class="sxs-lookup"><span data-stu-id="b7d03-126">To resolve a message class to a form, pass in the name of the message class to be resolved (for example,  `IPM.HelpDesk.Software`).</span></span> <span data-ttu-id="b7d03-127">若要强制使解析准确 (即，若要阻止解析到邮件类) 的基类，可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="b7d03-127">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="b7d03-128">已解析的邮件类的类标识符作为表单信息对象的一部分返回。</span><span class="sxs-lookup"><span data-stu-id="b7d03-128">The class identifier for the resolved message class is returned as part of the form information object.</span></span> <span data-ttu-id="b7d03-129">在调用 [IMAPIFormMgr：:P repareForm](imapiformmgr-prepareform.md) 或 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 方法之前，不要假定类标识符存在于 OLE 库中。</span><span class="sxs-lookup"><span data-stu-id="b7d03-129">Do not assume that the class identifier exists in the OLE library until after you call either the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) or [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b7d03-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b7d03-130">MFCMAPI reference</span></span>

<span data-ttu-id="b7d03-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b7d03-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b7d03-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="b7d03-132">**File**</span></span>|<span data-ttu-id="b7d03-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="b7d03-133">**Function**</span></span>|<span data-ttu-id="b7d03-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="b7d03-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b7d03-135">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="b7d03-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="b7d03-136">CFormContainerDlg：：OnResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="b7d03-136">CFormContainerDlg::OnResolveMessageClass</span></span>  <br/> |<span data-ttu-id="b7d03-137">MFCMAPI 使用 **IMAPIFormContainer：：ResolveMessageClass** 方法来查找与邮件类关联的表单。</span><span class="sxs-lookup"><span data-stu-id="b7d03-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMessageClass** method to locate a form that is associated with a message class.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b7d03-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7d03-138">See also</span></span>



[<span data-ttu-id="b7d03-139">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b7d03-139">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)
  
[<span data-ttu-id="b7d03-140">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="b7d03-140">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="b7d03-141">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="b7d03-141">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="b7d03-142">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b7d03-142">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

