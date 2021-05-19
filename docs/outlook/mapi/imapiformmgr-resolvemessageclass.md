---
title: IMAPIFormMgrResolveMessageClass
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.ResolveMessageClass
api_type:
- COM
ms.assetid: c2af7516-3a97-4422-874d-b1e3a0d4f316
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e99cff77fe872018722395c53c605e4d8fabfdde
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426392"
---
# <a name="imapiformmgrresolvemessageclass"></a><span data-ttu-id="f0ea8-103">IMAPIFormMgr::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="f0ea8-103">IMAPIFormMgr::ResolveMessageClass</span></span>

  
  
<span data-ttu-id="f0ea8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f0ea8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f0ea8-105">将邮件类解析为窗体容器内的窗体，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-105">Resolves a message class to its form within a form container, and returns a form information object for that form.</span></span>
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMsgClass,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPMAPIFORMINFO FAR * ppResult
);
```

## <a name="parameters"></a><span data-ttu-id="f0ea8-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0ea8-106">Parameters</span></span>

 <span data-ttu-id="f0ea8-107">_szMsgClass_</span><span class="sxs-lookup"><span data-stu-id="f0ea8-107">_szMsgClass_</span></span>
  
> <span data-ttu-id="f0ea8-108">[in]一个字符串，用于命名要解析的邮件类。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-108">[in] A string that names the message class being resolved.</span></span>
    
 <span data-ttu-id="f0ea8-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f0ea8-109">_ulFlags_</span></span>
  
> <span data-ttu-id="f0ea8-110">[in]控制如何解析邮件类的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-110">[in] A bitmask of flags that controls how the message class is resolved.</span></span> <span data-ttu-id="f0ea8-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="f0ea8-111">The following flag can be set:</span></span>
    
<span data-ttu-id="f0ea8-112">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="f0ea8-112">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="f0ea8-113">仅应解析完全匹配的邮件类字符串。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-113">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="f0ea8-114">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="f0ea8-114">_pFolderFocus_</span></span>
  
> <span data-ttu-id="f0ea8-115">[in]指向包含要解析的邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-115">[in] A pointer to the folder that contains the message being resolved.</span></span> <span data-ttu-id="f0ea8-116">_pFolderFocus_ 参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-116">The  _pFolderFocus_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="f0ea8-117">_ppResult_</span><span class="sxs-lookup"><span data-stu-id="f0ea8-117">_ppResult_</span></span>
  
> <span data-ttu-id="f0ea8-118">[out]指向返回的表单信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-118">[out] A pointer to a pointer to a returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f0ea8-119">返回值</span><span class="sxs-lookup"><span data-stu-id="f0ea8-119">Return value</span></span>

<span data-ttu-id="f0ea8-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="f0ea8-120">S_OK</span></span> 
  
> <span data-ttu-id="f0ea8-121">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-121">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="f0ea8-122">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="f0ea8-122">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="f0ea8-123">_在 szMsgClass_ 参数中传递的邮件类与表单库中任何窗体的邮件类不匹配。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-123">The message class passed in the  _szMsgClass_ parameter does not match the message class for any form in the form library.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f0ea8-124">备注</span><span class="sxs-lookup"><span data-stu-id="f0ea8-124">Remarks</span></span>

<span data-ttu-id="f0ea8-125">表单查看器调用 **IMAPIFormMgr：：ResolveMessageClass** 方法，将邮件类解析为表单容器中的表单。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-125">Form viewers call the **IMAPIFormMgr::ResolveMessageClass** method to resolve a message class to its form within a form container.</span></span> <span data-ttu-id="f0ea8-126">_ppResult_ 参数中返回的表单信息对象提供对具有给定邮件类的表单属性的进一步访问。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-126">The form information object returned in the  _ppResult_ parameter provides further access to the properties of the form that has the given message class.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f0ea8-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f0ea8-127">Notes to callers</span></span>

<span data-ttu-id="f0ea8-128">若要将邮件类解析为窗体，窗体查看器会传递要解析的邮件类的名称，例如" `IPM.HelpDesk.Software` "。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-128">To resolve a message class to a form, a form viewer passes in the name of the message class to be resolved, such as " `IPM.HelpDesk.Software`".</span></span> <span data-ttu-id="f0ea8-129">若要强制使解析准确 (即当完全匹配的表单服务器不可用时，阻止解析到邮件类的基类) ，可以在  _ulFlags_ 参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-129">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class when an exactly matching form server is not available), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="f0ea8-130">如果  _pFolderFocus_ 参数为 NULL，则邮件类解析过程不会搜索文件夹容器。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-130">If the  _pFolderFocus_ parameter is NULL, the message-class resolution process does not search a folder container.</span></span> 
  
<span data-ttu-id="f0ea8-131">搜索的容器的顺序取决于表单库提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-131">The order of the containers searched depends on the implementation of the form library provider.</span></span> <span data-ttu-id="f0ea8-132">默认表单库提供程序首先搜索本地容器，然后搜索传入文件夹的文件夹容器、个人表单容器，最后搜索组织容器。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-132">The default form library provider searches first the local container, then the folder container for the passed-in folder, the personal form container and, finally, the organization container.</span></span>
  
<span data-ttu-id="f0ea8-133">邮件类名称始终是 ANSI 字符串，从不为 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-133">Message class names are always ANSI strings, never Unicode.</span></span>
  
<span data-ttu-id="f0ea8-134">已解析的邮件类的类标识符作为表单信息对象的一部分返回。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-134">The class identifier for the resolved message class is returned as part of the form information object.</span></span> <span data-ttu-id="f0ea8-135">在表单查看器调用 [IMAPIFormMgr：:P repareForm](imapiformmgr-prepareform.md) 方法或 [IMAPIFormMgr：：CreateForm](imapiformmgr-createform.md) 方法之前，表单查看器不应在 OLE 库中存在类标识符的假设下工作。</span><span class="sxs-lookup"><span data-stu-id="f0ea8-135">A form viewer should not work on the assumption that the class identifier exists in the OLE library until after the form viewer has called either the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) method or the [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f0ea8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0ea8-136">See also</span></span>



[<span data-ttu-id="f0ea8-137">IMAPIFormInfo : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f0ea8-137">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)
  
[<span data-ttu-id="f0ea8-138">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="f0ea8-138">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="f0ea8-139">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="f0ea8-139">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="f0ea8-140">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f0ea8-140">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

