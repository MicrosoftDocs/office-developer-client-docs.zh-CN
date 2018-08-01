---
title: 发送邮件 MAPI 后台处理程序任务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 81c65f21-03ba-43eb-a6d4-d311e660ac5c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ff40eddf63e67f45495e90c1a960e45b7cc6cfb0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778745"
---
# <a name="sending-messages-mapi-spooler-tasks"></a><span data-ttu-id="a6f84-103">发送邮件：MAPI 后台处理程序任务</span><span class="sxs-lookup"><span data-stu-id="a6f84-103">Sending Messages: MAPI Spooler Tasks</span></span>

  
  
<span data-ttu-id="a6f84-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a6f84-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a6f84-105">MAPI 后台处理程序时所涉及的邮件传输过程中的邮件存储区不与紧密耦合传输提供程序，以及邮件需要预处理时紧密耦合的存储和传输无法处理收件人。</span><span class="sxs-lookup"><span data-stu-id="a6f84-105">The MAPI spooler is involved in the message transmission process when the message store is not tightly coupled with a transport provider, when the tightly coupled store and transport cannot handle a recipient, and when the message requires preprocessing.</span></span>
  
 <span data-ttu-id="a6f84-106">**任何必要预处理之后 MAPI 后台处理程序执行以下步骤：**</span><span class="sxs-lookup"><span data-stu-id="a6f84-106">**After any necessary preprocessing, the MAPI spooler performs the following steps:**</span></span>
  
1. <span data-ttu-id="a6f84-107">如果邮件没有锁定，请使用[IMsgStore::SetLockState](imsgstore-setlockstate.md)方法锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="a6f84-107">If the message is not locked, locks the message by using the [IMsgStore::SetLockState](imsgstore-setlockstate.md) method.</span></span> 
    
2. <span data-ttu-id="a6f84-108">已向其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE 的所有收件人发送邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="a6f84-108">Has the transport provider send the message to all recipients that have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to FALSE.</span></span> 
    
3. <span data-ttu-id="a6f84-109">调用程序清理已添加到的邮件在预处理如果**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性已设置期间使用的任何其他信息的适当的函数 ([RemovePreprocessInfo](removepreprocessinfo.md))。</span><span class="sxs-lookup"><span data-stu-id="a6f84-109">Calls the appropriate function ([RemovePreprocessInfo](removepreprocessinfo.md)) for cleaning up any additional information that was added to the message for use during preprocessing if the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property has been set.</span></span> <span data-ttu-id="a6f84-110">传输提供程序注册其预处理器的函数时指定此函数。</span><span class="sxs-lookup"><span data-stu-id="a6f84-110">This function is specified when the transport provider registers its preprocessor function.</span></span> 
    
4. <span data-ttu-id="a6f84-111">调用[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a6f84-111">Calls [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method.</span></span> <span data-ttu-id="a6f84-112">在**FinishedMsg**，消息存储提供程序：</span><span class="sxs-lookup"><span data-stu-id="a6f84-112">In **FinishedMsg**, the message store provider:</span></span>
    
  - <span data-ttu-id="a6f84-113">解除对邮件。</span><span class="sxs-lookup"><span data-stu-id="a6f84-113">Unlocks the message.</span></span>
    
  - <span data-ttu-id="a6f84-114">调用[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)方法来执行出站挂接处理如果消息挂接提供程序存在。</span><span class="sxs-lookup"><span data-stu-id="a6f84-114">Calls the [IMAPISupport::DoSentMail](imapisupport-dosentmail.md) method to perform outbound hook processing if a messaging hook provider exists.</span></span> <span data-ttu-id="a6f84-115">它然后将邮件复制到**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的项标识符标识的文件夹，如果不取代的消息挂接提供程序的发送消息处理。</span><span class="sxs-lookup"><span data-stu-id="a6f84-115">It then copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property, if not superseded by a messaging hook provider's sent message processing.</span></span> <span data-ttu-id="a6f84-116">最后，如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性已设置为 TRUE 删除邮件。</span><span class="sxs-lookup"><span data-stu-id="a6f84-116">Finally, it deletes the message if the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property has been set to TRUE.</span></span> 
    

