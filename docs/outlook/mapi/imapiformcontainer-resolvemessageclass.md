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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 713a177d5ceddf5fd4d97a0e35d87b2250748faf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775398"
---
# <a name="imapiformcontainerresolvemessageclass"></a><span data-ttu-id="1fb72-103">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="1fb72-103">IMAPIFormContainer::ResolveMessageClass</span></span>

  
  
<span data-ttu-id="1fb72-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1fb72-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1fb72-105">解析为其窗体的窗体容器中的邮件类，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="1fb72-105">Resolves a message class to its form in a form container and returns a form information object for that form.</span></span>
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMessageClass,
  ULONG ulFlags,
  LPMAPIFORMINFO FAR * ppforminfo
);
```

## <a name="parameters"></a><span data-ttu-id="1fb72-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fb72-106">Parameters</span></span>

 <span data-ttu-id="1fb72-107">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="1fb72-107">_szMessageClass_</span></span>
  
> <span data-ttu-id="1fb72-108">[in]命名正在解析的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="1fb72-108">[in] A string that names the message class being resolved.</span></span> <span data-ttu-id="1fb72-109">邮件类名称始终都是 ANSI 字符串，从不 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1fb72-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="1fb72-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1fb72-110">_ulFlags_</span></span>
  
> <span data-ttu-id="1fb72-111">[in]位掩码的标志控制如何消息类已解决的。</span><span class="sxs-lookup"><span data-stu-id="1fb72-111">[in] A bitmask of flags that controls how the message class is resolved.</span></span> <span data-ttu-id="1fb72-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="1fb72-112">The following flag can be set:</span></span>
    
<span data-ttu-id="1fb72-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="1fb72-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="1fb72-114">应解决仅邮件类的字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="1fb72-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="1fb72-115">_ppforminfo_</span><span class="sxs-lookup"><span data-stu-id="1fb72-115">_ppforminfo_</span></span>
  
> <span data-ttu-id="1fb72-116">[输出]指向返回窗体信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1fb72-116">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1fb72-117">返回值</span><span class="sxs-lookup"><span data-stu-id="1fb72-117">Return value</span></span>

<span data-ttu-id="1fb72-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fb72-118">S_OK</span></span> 
  
> <span data-ttu-id="1fb72-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="1fb72-119">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="1fb72-120">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="1fb72-120">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="1fb72-121">_SzMessageClass_参数中传递的邮件类不匹配窗体容器中的任何窗体的邮件类。</span><span class="sxs-lookup"><span data-stu-id="1fb72-121">The message class passed in the  _szMessageClass_ parameter does not match the message class for any form in the form container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1fb72-122">备注</span><span class="sxs-lookup"><span data-stu-id="1fb72-122">Remarks</span></span>

<span data-ttu-id="1fb72-123">客户端应用程序调用**IMAPIFormContainer::ResolveMessageClass**方法解析为窗体容器内的窗体的邮件类。</span><span class="sxs-lookup"><span data-stu-id="1fb72-123">Client applications call the **IMAPIFormContainer::ResolveMessageClass** method to resolve a message class to a form within a form container.</span></span> <span data-ttu-id="1fb72-124">返回_ppforminfo_参数中的窗体信息对象提供了进一步访问具有给定的邮件类的窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="1fb72-124">The form information object returned in the  _ppforminfo_ parameter provides further access to the properties of the form with the given message class.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1fb72-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1fb72-125">Notes to callers</span></span>

<span data-ttu-id="1fb72-126">若要解决向窗体的邮件类，传递解析的邮件类的名称 (例如， `IPM.HelpDesk.Software`)。</span><span class="sxs-lookup"><span data-stu-id="1fb72-126">To resolve a message class to a form, pass in the name of the message class to be resolved (for example,  `IPM.HelpDesk.Software`).</span></span> <span data-ttu-id="1fb72-127">强制为完全的分辨率 (即，以防止对的邮件类的基类的分辨率)，可以_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="1fb72-127">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="1fb72-128">解析的邮件类的类标识符返回窗体信息对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="1fb72-128">The class identifier for the resolved message class is returned as part of the form information object.</span></span> <span data-ttu-id="1fb72-129">不要假设您调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)或[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)方法之后的类标识符存在之前 OLE 库中。</span><span class="sxs-lookup"><span data-stu-id="1fb72-129">Do not assume that the class identifier exists in the OLE library until after you call either the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) or [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1fb72-130">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1fb72-130">MFCMAPI reference</span></span>

<span data-ttu-id="1fb72-131">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1fb72-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1fb72-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="1fb72-132">**File**</span></span>|<span data-ttu-id="1fb72-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="1fb72-133">**Function**</span></span>|<span data-ttu-id="1fb72-134">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1fb72-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1fb72-135">FormContainerDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="1fb72-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="1fb72-136">CFormContainerDlg::OnResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="1fb72-136">CFormContainerDlg::OnResolveMessageClass</span></span>  <br/> |<span data-ttu-id="1fb72-137">MFCMAPI 使用**IMAPIFormContainer::ResolveMessageClass**方法查找与邮件类关联的表单。</span><span class="sxs-lookup"><span data-stu-id="1fb72-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMessageClass** method to locate a form that is associated with a message class.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1fb72-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fb72-138">See also</span></span>



[<span data-ttu-id="1fb72-139">IMAPIFormInfo: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1fb72-139">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)
  
[<span data-ttu-id="1fb72-140">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="1fb72-140">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="1fb72-141">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="1fb72-141">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="1fb72-142">IMAPIFormContainer: IUnknown</span><span class="sxs-lookup"><span data-stu-id="1fb72-142">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

