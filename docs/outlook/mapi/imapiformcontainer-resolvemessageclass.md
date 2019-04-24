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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342159"
---
# <a name="imapiformcontainerresolvemessageclass"></a><span data-ttu-id="c04b5-103">IMAPIFormContainer::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="c04b5-103">IMAPIFormContainer::ResolveMessageClass</span></span>

  
  
<span data-ttu-id="c04b5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c04b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c04b5-105">将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="c04b5-105">Resolves a message class to its form in a form container and returns a form information object for that form.</span></span>
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMessageClass,
  ULONG ulFlags,
  LPMAPIFORMINFO FAR * ppforminfo
);
```

## <a name="parameters"></a><span data-ttu-id="c04b5-106">参数</span><span class="sxs-lookup"><span data-stu-id="c04b5-106">Parameters</span></span>

 <span data-ttu-id="c04b5-107">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="c04b5-107">_szMessageClass_</span></span>
  
> <span data-ttu-id="c04b5-108">实时一个为要解析的邮件类别命名的字符串。</span><span class="sxs-lookup"><span data-stu-id="c04b5-108">[in] A string that names the message class being resolved.</span></span> <span data-ttu-id="c04b5-109">邮件类名称始终为 ANSI 字符串, 决不能为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c04b5-109">Message class names are always ANSI strings, never Unicode.</span></span>
    
 <span data-ttu-id="c04b5-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c04b5-110">_ulFlags_</span></span>
  
> <span data-ttu-id="c04b5-111">实时用于控制如何解析邮件类别的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c04b5-111">[in] A bitmask of flags that controls how the message class is resolved.</span></span> <span data-ttu-id="c04b5-112">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="c04b5-112">The following flag can be set:</span></span>
    
<span data-ttu-id="c04b5-113">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="c04b5-113">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="c04b5-114">应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="c04b5-114">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="c04b5-115">_ppforminfo_</span><span class="sxs-lookup"><span data-stu-id="c04b5-115">_ppforminfo_</span></span>
  
> <span data-ttu-id="c04b5-116">排除指向指向返回的表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="c04b5-116">[out] A pointer to a pointer to the returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c04b5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c04b5-117">Return value</span></span>

<span data-ttu-id="c04b5-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c04b5-118">S_OK</span></span> 
  
> <span data-ttu-id="c04b5-119">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="c04b5-119">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="c04b5-120">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c04b5-120">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="c04b5-121">在_szMessageClass_参数中传递的邮件类与表单容器中任何表单的邮件类都不匹配。</span><span class="sxs-lookup"><span data-stu-id="c04b5-121">The message class passed in the  _szMessageClass_ parameter does not match the message class for any form in the form container.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c04b5-122">注解</span><span class="sxs-lookup"><span data-stu-id="c04b5-122">Remarks</span></span>

<span data-ttu-id="c04b5-123">客户端应用程序调用**IMAPIFormContainer:: ResolveMessageClass**方法将邮件类别解析为表单容器内的窗体。</span><span class="sxs-lookup"><span data-stu-id="c04b5-123">Client applications call the **IMAPIFormContainer::ResolveMessageClass** method to resolve a message class to a form within a form container.</span></span> <span data-ttu-id="c04b5-124">_ppforminfo_参数中返回的 form 信息对象提供了对具有给定邮件类的表单属性的进一步访问权限。</span><span class="sxs-lookup"><span data-stu-id="c04b5-124">The form information object returned in the  _ppforminfo_ parameter provides further access to the properties of the form with the given message class.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="c04b5-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="c04b5-125">Notes to callers</span></span>

<span data-ttu-id="c04b5-126">若要将邮件类别解析为表单, 请传入要解析的邮件类的名称 (例如, `IPM.HelpDesk.Software`)。</span><span class="sxs-lookup"><span data-stu-id="c04b5-126">To resolve a message class to a form, pass in the name of the message class to be resolved (for example,  `IPM.HelpDesk.Software`).</span></span> <span data-ttu-id="c04b5-127">若要强制解决是精确的 (即, 若要防止解析邮件类的基类), 可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="c04b5-127">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> 
  
<span data-ttu-id="c04b5-128">解析的邮件类的类标识符作为表单信息对象的一部分返回。</span><span class="sxs-lookup"><span data-stu-id="c04b5-128">The class identifier for the resolved message class is returned as part of the form information object.</span></span> <span data-ttu-id="c04b5-129">在调用[IMAPIFormMgr::P repareform](imapiformmgr-prepareform.md)或[IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md)方法之后, 不要假定该类标识符存在于 OLE 库中。</span><span class="sxs-lookup"><span data-stu-id="c04b5-129">Do not assume that the class identifier exists in the OLE library until after you call either the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) or [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) method.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="c04b5-130">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="c04b5-130">MFCMAPI reference</span></span>

<span data-ttu-id="c04b5-131">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c04b5-131">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c04b5-132">**文件**</span><span class="sxs-lookup"><span data-stu-id="c04b5-132">**File**</span></span>|<span data-ttu-id="c04b5-133">**函数**</span><span class="sxs-lookup"><span data-stu-id="c04b5-133">**Function**</span></span>|<span data-ttu-id="c04b5-134">**备注**</span><span class="sxs-lookup"><span data-stu-id="c04b5-134">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c04b5-135">FormContainerDlg</span><span class="sxs-lookup"><span data-stu-id="c04b5-135">FormContainerDlg.cpp</span></span>  <br/> |<span data-ttu-id="c04b5-136">CFormContainerDlg:: OnResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="c04b5-136">CFormContainerDlg::OnResolveMessageClass</span></span>  <br/> |<span data-ttu-id="c04b5-137">MFCMAPI 使用**IMAPIFormContainer:: ResolveMessageClass**方法来查找与邮件类关联的窗体。</span><span class="sxs-lookup"><span data-stu-id="c04b5-137">MFCMAPI uses the **IMAPIFormContainer::ResolveMessageClass** method to locate a form that is associated with a message class.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c04b5-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c04b5-138">See also</span></span>



[<span data-ttu-id="c04b5-139">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c04b5-139">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)
  
[<span data-ttu-id="c04b5-140">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="c04b5-140">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="c04b5-141">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="c04b5-141">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="c04b5-142">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c04b5-142">IMAPIFormContainer : IUnknown</span></span>](imapiformcontaineriunknown.md)

