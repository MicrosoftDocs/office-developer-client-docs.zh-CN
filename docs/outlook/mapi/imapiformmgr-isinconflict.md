---
title: IMAPIFormMgrIsInConflict
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgrIsInConflict
api_type:
- COM
ms.assetid: 5ca86ee8-1bf6-4ec8-95b3-575c22fbb170
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 87432d8982c5dc1f64396187739e97314edb385c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412882"
---
# <a name="imapiformmgrisinconflict"></a><span data-ttu-id="23752-103">IMAPIFormMgr::IsInConflict</span><span class="sxs-lookup"><span data-stu-id="23752-103">IMAPIFormMgr::IsInConflict</span></span>

  
  
<span data-ttu-id="23752-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="23752-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="23752-105">确定表单是否可以处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-105">Determines whether a form can handle its own message conflicts.</span></span> <span data-ttu-id="23752-106">如果有多个用户同时编辑邮件, 则邮件发生冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-106">A message is in conflict if it has been simultaneously edited by more than one user.</span></span> <span data-ttu-id="23752-107">公用文件夹中的邮件可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="23752-107">This can happen to messages in public folders.</span></span>
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a><span data-ttu-id="23752-108">参数</span><span class="sxs-lookup"><span data-stu-id="23752-108">Parameters</span></span>

 <span data-ttu-id="23752-109">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="23752-109">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="23752-110">实时指向从消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志位掩码的指针, 该消息指示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="23752-110">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of a message that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="23752-111">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="23752-111">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="23752-112">实时从邮件的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性中复制的客户端定义或提供程序定义的标志的位掩码, 它提供有关邮件状态的其他信息。</span><span class="sxs-lookup"><span data-stu-id="23752-112">[in] A bitmask of client-defined or provider-defined flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of a message that provides additional information about the state of the message.</span></span>
    
 <span data-ttu-id="23752-113">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="23752-113">_szMessageClass_</span></span>
  
> <span data-ttu-id="23752-114">实时一个用于命名邮件的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="23752-114">[in] A string that names the message's message class.</span></span>
    
 <span data-ttu-id="23752-115">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="23752-115">_pFolderFocus_</span></span>
  
> <span data-ttu-id="23752-116">实时指向包含邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="23752-116">[in] A pointer to the folder that contains the message.</span></span> <span data-ttu-id="23752-117">如果不存在这样的文件夹 (例如, 如果邮件嵌入在另一封邮件中), _pFolderFocus_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="23752-117">The  _pFolderFocus_ parameter can be NULL if such a folder does not exist (for example, if the message is embedded in another message).</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="23752-118">返回值</span><span class="sxs-lookup"><span data-stu-id="23752-118">Return value</span></span>

<span data-ttu-id="23752-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="23752-119">S_OK</span></span> 
  
> <span data-ttu-id="23752-120">表单不会处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-120">The form does not handle its own message conflicts.</span></span>
    
<span data-ttu-id="23752-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="23752-121">S_FALSE</span></span> 
  
> <span data-ttu-id="23752-122">该表单处理自己的邮件冲突, 或者信息传递的邮件未发生冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-122">The form handles its own message conflicts, or the message for which information was passed is not in conflict.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="23752-123">说明</span><span class="sxs-lookup"><span data-stu-id="23752-123">Remarks</span></span>

<span data-ttu-id="23752-124">表单查看者调用**IMAPIFormMgr:: IsInConflict**方法, 以发现特定表单是否未处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-124">Form viewers call the **IMAPIFormMgr::IsInConflict** method to discover whether a particular form does not handle its own message conflicts.</span></span> <span data-ttu-id="23752-125">**IsInConflict**检查_ulMessageFlags_和_ulMessageStatus_参数中的位掩码是否存在冲突标志。</span><span class="sxs-lookup"><span data-stu-id="23752-125">**IsInConflict** checks the bitmasks in the  _ulMessageFlags_ and  _ulMessageStatus_ parameters for the presence of a conflict flag.</span></span> <span data-ttu-id="23752-126">如果设置了冲突标志, **IsInConflict**将解析在_szMessageClass_参数中传递的邮件类, 如果窗体不处理自己的冲突, 则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="23752-126">If a conflict flag is set, **IsInConflict** resolves the message class passed in the  _szMessageClass_ parameter and returns S_OK if the form does not handle its own conflicts.</span></span> <span data-ttu-id="23752-127">如果窗体处理自己的冲突, **IsInConflict**将返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="23752-127">**IsInConflict** returns S_FALSE if the form handles its own conflicts.</span></span> 
  
<span data-ttu-id="23752-128">必须使用[IMAPIFormMgr:: LoadForm](imapiformmgr-loadform.md)方法打开不处理自己的冲突的窗体, 并且无法重用现有的 form 对象。</span><span class="sxs-lookup"><span data-stu-id="23752-128">A form that does not handle its own conflicts must be opened by using the [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) method and cannot reuse an existing form object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="23752-129">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="23752-129">Notes to callers</span></span>

<span data-ttu-id="23752-130">当应用程序从文件夹中的一封邮件移动到下一封邮件或上一封邮件时, 客户端应用程序通常需要处理冲突。</span><span class="sxs-lookup"><span data-stu-id="23752-130">Client applications typically have to deal with conflicts when the applications move from one message to the next or previous message in a folder.</span></span> <span data-ttu-id="23752-131">如果邮件发生冲突, 但该邮件的表单服务器可以处理冲突, 则客户端应用程序应执行通常的代码以显示下一条或上一封邮件。</span><span class="sxs-lookup"><span data-stu-id="23752-131">If a message is in conflict, but the form server for that message can handle conflicts, the client application should execute its usual code for displaying the next or previous message.</span></span> <span data-ttu-id="23752-132">如果窗体服务器无法处理冲突, 客户端应用程序应继续进行, 就像它不知道下一条或上一封邮件的邮件类一样。</span><span class="sxs-lookup"><span data-stu-id="23752-132">If the form server cannot handle conflicts, the client application should continue as if it was unaware of the message class of the next or previous message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="23752-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23752-133">See also</span></span>



[<span data-ttu-id="23752-134">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="23752-134">IMAPIFormAdviseSink::OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md)
  
[<span data-ttu-id="23752-135">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="23752-135">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="23752-136">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="23752-136">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="23752-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="23752-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

