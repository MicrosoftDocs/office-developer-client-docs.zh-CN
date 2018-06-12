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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a84698ccc132c750cbd071c05160117c40e352a4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775456"
---
# <a name="imapiformmgrresolvemessageclass"></a><span data-ttu-id="34654-103">IMAPIFormMgr::ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="34654-103">IMAPIFormMgr::ResolveMessageClass</span></span>

  
  
<span data-ttu-id="34654-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="34654-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="34654-105">将邮件类解析为其表单中的窗体容器中，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="34654-105">Resolves a message class to its form within a form container, and returns a form information object for that form.</span></span>
  
```cpp
HRESULT ResolveMessageClass(
  LPCSTR szMsgClass,
  ULONG ulFlags,
  LPMAPIFOLDER pFolderFocus,
  LPMAPIFORMINFO FAR * ppResult
);
```

## <a name="parameters"></a><span data-ttu-id="34654-106">参数</span><span class="sxs-lookup"><span data-stu-id="34654-106">Parameters</span></span>

 <span data-ttu-id="34654-107">_szMsgClass_</span><span class="sxs-lookup"><span data-stu-id="34654-107">_szMsgClass_</span></span>
  
> <span data-ttu-id="34654-108">[in]命名正在解析的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="34654-108">[in] A string that names the message class being resolved.</span></span>
    
 <span data-ttu-id="34654-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="34654-109">_ulFlags_</span></span>
  
> <span data-ttu-id="34654-110">[in]位掩码的标志控制如何消息类已解决的。</span><span class="sxs-lookup"><span data-stu-id="34654-110">[in] A bitmask of flags that controls how the message class is resolved.</span></span> <span data-ttu-id="34654-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="34654-111">The following flag can be set:</span></span>
    
<span data-ttu-id="34654-112">MAPIFORM_EXACTMATCH</span><span class="sxs-lookup"><span data-stu-id="34654-112">MAPIFORM_EXACTMATCH</span></span> 
  
> <span data-ttu-id="34654-113">应解决仅邮件类的字符串完全匹配。</span><span class="sxs-lookup"><span data-stu-id="34654-113">Only message class strings that are an exact match should be resolved.</span></span>
    
 <span data-ttu-id="34654-114">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="34654-114">_pFolderFocus_</span></span>
  
> <span data-ttu-id="34654-115">[in]一个指向的文件夹，包含要解析的消息。</span><span class="sxs-lookup"><span data-stu-id="34654-115">[in] A pointer to the folder that contains the message being resolved.</span></span> <span data-ttu-id="34654-116">_PFolderFocus_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="34654-116">The  _pFolderFocus_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="34654-117">_ppResult_</span><span class="sxs-lookup"><span data-stu-id="34654-117">_ppResult_</span></span>
  
> <span data-ttu-id="34654-118">[输出]指向返回窗体信息对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="34654-118">[out] A pointer to a pointer to a returned form information object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="34654-119">返回值</span><span class="sxs-lookup"><span data-stu-id="34654-119">Return value</span></span>

<span data-ttu-id="34654-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="34654-120">S_OK</span></span> 
  
> <span data-ttu-id="34654-121">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="34654-121">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="34654-122">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="34654-122">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="34654-123">_SzMsgClass_参数中传递的邮件类不匹配的邮件类的窗体库中的任何表单。</span><span class="sxs-lookup"><span data-stu-id="34654-123">The message class passed in the  _szMsgClass_ parameter does not match the message class for any form in the form library.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="34654-124">备注</span><span class="sxs-lookup"><span data-stu-id="34654-124">Remarks</span></span>

<span data-ttu-id="34654-125">表单查看器调用**IMAPIFormMgr::ResolveMessageClass**方法解析为其表单窗体容器内的邮件类。</span><span class="sxs-lookup"><span data-stu-id="34654-125">Form viewers call the **IMAPIFormMgr::ResolveMessageClass** method to resolve a message class to its form within a form container.</span></span> <span data-ttu-id="34654-126">返回_ppResult_参数中的窗体信息对象提供了进一步访问具有给定的邮件类的窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="34654-126">The form information object returned in the  _ppResult_ parameter provides further access to the properties of the form that has the given message class.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="34654-127">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="34654-127">Notes to callers</span></span>

<span data-ttu-id="34654-128">若要解决向窗体的邮件类，表单查看器，将传递名称解析，如的邮件类" `IPM.HelpDesk.Software`"。</span><span class="sxs-lookup"><span data-stu-id="34654-128">To resolve a message class to a form, a form viewer passes in the name of the message class to be resolved, such as " `IPM.HelpDesk.Software`".</span></span> <span data-ttu-id="34654-129">若要强制为完全的分辨率 （即，以防止解决方案时完全匹配的窗体的邮件类的基类服务器不可用），可以在_ulFlags_参数中传递 MAPIFORM_EXACTMATCH 标志。</span><span class="sxs-lookup"><span data-stu-id="34654-129">To force the resolution to be exact (that is, to prevent resolution to a base class of the message class when an exactly matching form server is not available), the MAPIFORM_EXACTMATCH flag can be passed in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="34654-130">如果_pFolderFocus_参数为 NULL，则邮件类解析过程不搜索的文件夹的容器。</span><span class="sxs-lookup"><span data-stu-id="34654-130">If the  _pFolderFocus_ parameter is NULL, the message-class resolution process does not search a folder container.</span></span> 
  
<span data-ttu-id="34654-131">搜索的容器的顺序取决于窗体库提供程序的实现。</span><span class="sxs-lookup"><span data-stu-id="34654-131">The order of the containers searched depends on the implementation of the form library provider.</span></span> <span data-ttu-id="34654-132">默认窗体库提供程序先搜索本地的容器，然后为传入的文件夹，个人窗体容器和组织容器，最后，文件夹容器。</span><span class="sxs-lookup"><span data-stu-id="34654-132">The default form library provider searches first the local container, then the folder container for the passed-in folder, the personal form container and, finally, the organization container.</span></span>
  
<span data-ttu-id="34654-133">邮件类名称始终都是 ANSI 字符串，从不 Unicode。</span><span class="sxs-lookup"><span data-stu-id="34654-133">Message class names are always ANSI strings, never Unicode.</span></span>
  
<span data-ttu-id="34654-134">解析的邮件类的类标识符返回窗体信息对象的一部分。</span><span class="sxs-lookup"><span data-stu-id="34654-134">The class identifier for the resolved message class is returned as part of the form information object.</span></span> <span data-ttu-id="34654-135">假定 OLE 库之前中存在的类标识符的表单查看器具有调用[IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md)方法或[IMAPIFormMgr::CreateForm](imapiformmgr-createform.md)方法后，表单查看器应不起作用。</span><span class="sxs-lookup"><span data-stu-id="34654-135">A form viewer should not work on the assumption that the class identifier exists in the OLE library until after the form viewer has called either the [IMAPIFormMgr::PrepareForm](imapiformmgr-prepareform.md) method or the [IMAPIFormMgr::CreateForm](imapiformmgr-createform.md) method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="34654-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34654-136">See also</span></span>



[<span data-ttu-id="34654-137">IMAPIFormInfo: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="34654-137">IMAPIFormInfo : IMAPIProp</span></span>](imapiforminfoimapiprop.md)
  
[<span data-ttu-id="34654-138">IMAPIFormMgr::CreateForm</span><span class="sxs-lookup"><span data-stu-id="34654-138">IMAPIFormMgr::CreateForm</span></span>](imapiformmgr-createform.md)
  
[<span data-ttu-id="34654-139">IMAPIFormMgr::PrepareForm</span><span class="sxs-lookup"><span data-stu-id="34654-139">IMAPIFormMgr::PrepareForm</span></span>](imapiformmgr-prepareform.md)
  
[<span data-ttu-id="34654-140">IMAPIFormMgr: IUnknown</span><span class="sxs-lookup"><span data-stu-id="34654-140">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

