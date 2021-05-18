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
# <a name="imapiformmgrisinconflict"></a><span data-ttu-id="870b5-103">IMAPIFormMgr::IsInConflict</span><span class="sxs-lookup"><span data-stu-id="870b5-103">IMAPIFormMgr::IsInConflict</span></span>

  
  
<span data-ttu-id="870b5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="870b5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="870b5-105">确定表单是否可以处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-105">Determines whether a form can handle its own message conflicts.</span></span> <span data-ttu-id="870b5-106">如果邮件已由多个用户同时编辑，则邮件存在冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-106">A message is in conflict if it has been simultaneously edited by more than one user.</span></span> <span data-ttu-id="870b5-107">公用文件夹中的邮件可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="870b5-107">This can happen to messages in public folders.</span></span>
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a><span data-ttu-id="870b5-108">参数</span><span class="sxs-lookup"><span data-stu-id="870b5-108">Parameters</span></span>

 <span data-ttu-id="870b5-109">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="870b5-109">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="870b5-110">[in]指向从邮件的 **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的标志的位掩码的指针，指示邮件的当前状态。</span><span class="sxs-lookup"><span data-stu-id="870b5-110">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of a message that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="870b5-111">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="870b5-111">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="870b5-112">[in]从邮件的 **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性复制的客户端定义或提供程序定义标志的位掩码，提供有关邮件状态的其他信息。</span><span class="sxs-lookup"><span data-stu-id="870b5-112">[in] A bitmask of client-defined or provider-defined flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of a message that provides additional information about the state of the message.</span></span>
    
 <span data-ttu-id="870b5-113">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="870b5-113">_szMessageClass_</span></span>
  
> <span data-ttu-id="870b5-114">[in]一个字符串，用于命名邮件的邮件类。</span><span class="sxs-lookup"><span data-stu-id="870b5-114">[in] A string that names the message's message class.</span></span>
    
 <span data-ttu-id="870b5-115">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="870b5-115">_pFolderFocus_</span></span>
  
> <span data-ttu-id="870b5-116">[in]指向包含邮件的文件夹的指针。</span><span class="sxs-lookup"><span data-stu-id="870b5-116">[in] A pointer to the folder that contains the message.</span></span> <span data-ttu-id="870b5-117">如果  _不存在此类文件夹，pFolderFocus_ 参数可以是 NULL (例如，如果邮件嵌入另一个邮件) 。</span><span class="sxs-lookup"><span data-stu-id="870b5-117">The  _pFolderFocus_ parameter can be NULL if such a folder does not exist (for example, if the message is embedded in another message).</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="870b5-118">返回值</span><span class="sxs-lookup"><span data-stu-id="870b5-118">Return value</span></span>

<span data-ttu-id="870b5-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="870b5-119">S_OK</span></span> 
  
> <span data-ttu-id="870b5-120">表单不处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-120">The form does not handle its own message conflicts.</span></span>
    
<span data-ttu-id="870b5-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="870b5-121">S_FALSE</span></span> 
  
> <span data-ttu-id="870b5-122">表单处理自己的邮件冲突，或者传递信息的邮件没有冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-122">The form handles its own message conflicts, or the message for which information was passed is not in conflict.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="870b5-123">备注</span><span class="sxs-lookup"><span data-stu-id="870b5-123">Remarks</span></span>

<span data-ttu-id="870b5-124">表单查看者调用 **IMAPIFormMgr：：IsInConflict** 方法来发现特定表单是否不处理其自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-124">Form viewers call the **IMAPIFormMgr::IsInConflict** method to discover whether a particular form does not handle its own message conflicts.</span></span> <span data-ttu-id="870b5-125">**IsInConflict** 检查  _ulMessageFlags_ 和  _ulMessageStatus_ 参数中的位掩码是否存在冲突标志。</span><span class="sxs-lookup"><span data-stu-id="870b5-125">**IsInConflict** checks the bitmasks in the  _ulMessageFlags_ and  _ulMessageStatus_ parameters for the presence of a conflict flag.</span></span> <span data-ttu-id="870b5-126">如果设置了冲突标志 **，IsInConflict** 将解析  _在 szMessageClass_ 参数中传递的邮件类，如果S_OK不处理自己的冲突，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="870b5-126">If a conflict flag is set, **IsInConflict** resolves the message class passed in the  _szMessageClass_ parameter and returns S_OK if the form does not handle its own conflicts.</span></span> <span data-ttu-id="870b5-127">**如果表单处理S_FALSE，则 IsInConflict** 返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="870b5-127">**IsInConflict** returns S_FALSE if the form handles its own conflicts.</span></span> 
  
<span data-ttu-id="870b5-128">不处理其自身的冲突的表单必须使用 [IMAPIFormMgr：：LoadForm](imapiformmgr-loadform.md) 方法打开，并且不能重复使用现有的表单对象。</span><span class="sxs-lookup"><span data-stu-id="870b5-128">A form that does not handle its own conflicts must be opened by using the [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) method and cannot reuse an existing form object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="870b5-129">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="870b5-129">Notes to callers</span></span>

<span data-ttu-id="870b5-130">当应用程序从一封邮件移动到文件夹中的下一封邮件或上一封邮件时，客户端应用程序通常必须处理冲突。</span><span class="sxs-lookup"><span data-stu-id="870b5-130">Client applications typically have to deal with conflicts when the applications move from one message to the next or previous message in a folder.</span></span> <span data-ttu-id="870b5-131">如果邮件存在冲突，但该邮件的窗体服务器可以处理冲突，则客户端应用程序应执行其用于显示下一封邮件或上一封邮件的常用代码。</span><span class="sxs-lookup"><span data-stu-id="870b5-131">If a message is in conflict, but the form server for that message can handle conflicts, the client application should execute its usual code for displaying the next or previous message.</span></span> <span data-ttu-id="870b5-132">如果表单服务器无法处理冲突，则客户端应用程序应继续，就像不知道下一封邮件或上一封邮件的邮件类一样。</span><span class="sxs-lookup"><span data-stu-id="870b5-132">If the form server cannot handle conflicts, the client application should continue as if it was unaware of the message class of the next or previous message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="870b5-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="870b5-133">See also</span></span>



[<span data-ttu-id="870b5-134">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="870b5-134">IMAPIFormAdviseSink::OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md)
  
[<span data-ttu-id="870b5-135">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="870b5-135">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="870b5-136">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="870b5-136">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="870b5-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="870b5-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

