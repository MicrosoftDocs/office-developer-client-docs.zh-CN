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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 329771bf79e30f07c9de0a311aa2a836ca507c38
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580031"
---
# <a name="imapiformmgrisinconflict"></a><span data-ttu-id="ca171-103">IMAPIFormMgr::IsInConflict</span><span class="sxs-lookup"><span data-stu-id="ca171-103">IMAPIFormMgr::IsInConflict</span></span>

  
  
<span data-ttu-id="ca171-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca171-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca171-105">确定窗体是否可以处理其自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-105">Determines whether a form can handle its own message conflicts.</span></span> <span data-ttu-id="ca171-106">如果已通过多个用户同时编辑邮件有冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-106">A message is in conflict if it has been simultaneously edited by more than one user.</span></span> <span data-ttu-id="ca171-107">这可能对公用文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="ca171-107">This can happen to messages in public folders.</span></span>
  
```cpp
HRESULT IsInConflict(
  ULONG ulMessageFlags,
  ULONG ulMessageStatus,
  LPCSTR szMessageClass LPMAPIFOLDER pFolderFocus
);
```

## <a name="parameters"></a><span data-ttu-id="ca171-108">参数</span><span class="sxs-lookup"><span data-stu-id="ca171-108">Parameters</span></span>

 <span data-ttu-id="ca171-109">_ulMessageFlags_</span><span class="sxs-lookup"><span data-stu-id="ca171-109">_ulMessageFlags_</span></span>
  
> <span data-ttu-id="ca171-110">[in]一个指向标志从一条消息，指示邮件的当前状态的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性复制的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ca171-110">[in] A pointer to a bitmask of flags copied from the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property of a message that indicates the current state of the message.</span></span>
    
 <span data-ttu-id="ca171-111">_ulMessageStatus_</span><span class="sxs-lookup"><span data-stu-id="ca171-111">_ulMessageStatus_</span></span>
  
> <span data-ttu-id="ca171-112">[in]复制从一条消息，提供有关状态的消息的附加信息的**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) 属性的客户端或提供程序定义标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ca171-112">[in] A bitmask of client-defined or provider-defined flags copied from the **PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md)) property of a message that provides additional information about the state of the message.</span></span>
    
 <span data-ttu-id="ca171-113">_szMessageClass_</span><span class="sxs-lookup"><span data-stu-id="ca171-113">_szMessageClass_</span></span>
  
> <span data-ttu-id="ca171-114">[in]命名邮件的邮件类的字符串。</span><span class="sxs-lookup"><span data-stu-id="ca171-114">[in] A string that names the message's message class.</span></span>
    
 <span data-ttu-id="ca171-115">_pFolderFocus_</span><span class="sxs-lookup"><span data-stu-id="ca171-115">_pFolderFocus_</span></span>
  
> <span data-ttu-id="ca171-116">[in]一个指向包含邮件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca171-116">[in] A pointer to the folder that contains the message.</span></span> <span data-ttu-id="ca171-117">_PFolderFocus_参数可以是 NULL，如果这样的文件夹不存在 （例如，如果邮件嵌入到另一条消息）。</span><span class="sxs-lookup"><span data-stu-id="ca171-117">The  _pFolderFocus_ parameter can be NULL if such a folder does not exist (for example, if the message is embedded in another message).</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ca171-118">返回值</span><span class="sxs-lookup"><span data-stu-id="ca171-118">Return value</span></span>

<span data-ttu-id="ca171-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ca171-119">S_OK</span></span> 
  
> <span data-ttu-id="ca171-120">窗体并不处理其自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-120">The form does not handle its own message conflicts.</span></span>
    
<span data-ttu-id="ca171-121">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ca171-121">S_FALSE</span></span> 
  
> <span data-ttu-id="ca171-122">窗体处理自己消息冲突，或为其传递信息消息不存在冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-122">The form handles its own message conflicts, or the message for which information was passed is not in conflict.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ca171-123">注解</span><span class="sxs-lookup"><span data-stu-id="ca171-123">Remarks</span></span>

<span data-ttu-id="ca171-124">表单查看器调用**IMAPIFormMgr::IsInConflict**方法来发现是否特定窗体并不处理其自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-124">Form viewers call the **IMAPIFormMgr::IsInConflict** method to discover whether a particular form does not handle its own message conflicts.</span></span> <span data-ttu-id="ca171-125">**IsInConflict**检查存在冲突标志_ulMessageFlags_和_ulMessageStatus_参数中的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ca171-125">**IsInConflict** checks the bitmasks in the  _ulMessageFlags_ and  _ulMessageStatus_ parameters for the presence of a conflict flag.</span></span> <span data-ttu-id="ca171-126">如果设置冲突标志， **IsInConflict**解析_szMessageClass_参数中传递的邮件类和如果窗体不处理其自己的冲突，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ca171-126">If a conflict flag is set, **IsInConflict** resolves the message class passed in the  _szMessageClass_ parameter and returns S_OK if the form does not handle its own conflicts.</span></span> <span data-ttu-id="ca171-127">如果表单处理自己冲突， **IsInConflict**返回 S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="ca171-127">**IsInConflict** returns S_FALSE if the form handles its own conflicts.</span></span> 
  
<span data-ttu-id="ca171-128">并不处理其自己的冲突的窗体必须使用[IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md)方法打开和无法重用现有的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="ca171-128">A form that does not handle its own conflicts must be opened by using the [IMAPIFormMgr::LoadForm](imapiformmgr-loadform.md) method and cannot reuse an existing form object.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ca171-129">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ca171-129">Notes to callers</span></span>

<span data-ttu-id="ca171-130">客户端应用程序通常必须时应用程序将从一个邮件移动到文件夹中的下一页或上一页邮件处理冲突。</span><span class="sxs-lookup"><span data-stu-id="ca171-130">Client applications typically have to deal with conflicts when the applications move from one message to the next or previous message in a folder.</span></span> <span data-ttu-id="ca171-131">如果邮件是冲突，但该消息的窗体服务器可以处理冲突，客户端应用程序应执行用于显示的下一页或上一页消息其往常代码。</span><span class="sxs-lookup"><span data-stu-id="ca171-131">If a message is in conflict, but the form server for that message can handle conflicts, the client application should execute its usual code for displaying the next or previous message.</span></span> <span data-ttu-id="ca171-132">如果窗体服务器无法处理冲突，就好像它，下一页或上一页邮件的邮件类不知道应继续客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca171-132">If the form server cannot handle conflicts, the client application should continue as if it was unaware of the message class of the next or previous message.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ca171-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca171-133">See also</span></span>



[<span data-ttu-id="ca171-134">IMAPIFormAdviseSink::OnActivateNext</span><span class="sxs-lookup"><span data-stu-id="ca171-134">IMAPIFormAdviseSink::OnActivateNext</span></span>](imapiformadvisesink-onactivatenext.md)
  
[<span data-ttu-id="ca171-135">PidTagMessageFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca171-135">PidTagMessageFlags Canonical Property</span></span>](pidtagmessageflags-canonical-property.md)
  
[<span data-ttu-id="ca171-136">PidTagMessageStatus 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca171-136">PidTagMessageStatus Canonical Property</span></span>](pidtagmessagestatus-canonical-property.md)
  
[<span data-ttu-id="ca171-137">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ca171-137">IMAPIFormMgr : IUnknown</span></span>](imapiformmgriunknown.md)

