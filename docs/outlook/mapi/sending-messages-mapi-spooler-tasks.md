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
ms.openlocfilehash: eef65990637d9c164ffe75f682e01ed134510e32
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570273"
---
# <a name="sending-messages-mapi-spooler-tasks"></a><span data-ttu-id="9bdb3-103">发送邮件：MAPI 后台处理程序任务</span><span class="sxs-lookup"><span data-stu-id="9bdb3-103">Sending Messages: MAPI Spooler Tasks</span></span>

  
  
<span data-ttu-id="9bdb3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9bdb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9bdb3-105">MAPI 后台处理程序时所涉及的邮件传输过程中的邮件存储区不与紧密耦合传输提供程序，以及邮件需要预处理时紧密耦合的存储和传输无法处理收件人。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-105">The MAPI spooler is involved in the message transmission process when the message store is not tightly coupled with a transport provider, when the tightly coupled store and transport cannot handle a recipient, and when the message requires preprocessing.</span></span>
  
 <span data-ttu-id="9bdb3-106">**任何必要预处理之后 MAPI 后台处理程序执行以下步骤：**</span><span class="sxs-lookup"><span data-stu-id="9bdb3-106">**After any necessary preprocessing, the MAPI spooler performs the following steps:**</span></span>
  
1. <span data-ttu-id="9bdb3-107">如果邮件没有锁定，请使用[IMsgStore::SetLockState](imsgstore-setlockstate.md)方法锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-107">If the message is not locked, locks the message by using the [IMsgStore::SetLockState](imsgstore-setlockstate.md) method.</span></span> 
    
2. <span data-ttu-id="9bdb3-108">已向其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE 的所有收件人发送邮件的传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-108">Has the transport provider send the message to all recipients that have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to FALSE.</span></span> 
    
3. <span data-ttu-id="9bdb3-109">调用程序清理已添加到的邮件在预处理如果**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性已设置期间使用的任何其他信息的适当的函数 ([RemovePreprocessInfo](removepreprocessinfo.md))。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-109">Calls the appropriate function ([RemovePreprocessInfo](removepreprocessinfo.md)) for cleaning up any additional information that was added to the message for use during preprocessing if the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property has been set.</span></span> <span data-ttu-id="9bdb3-110">传输提供程序注册其预处理器的函数时指定此函数。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-110">This function is specified when the transport provider registers its preprocessor function.</span></span> 
    
4. <span data-ttu-id="9bdb3-111">调用[IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-111">Calls [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method.</span></span> <span data-ttu-id="9bdb3-112">在**FinishedMsg**，消息存储提供程序：</span><span class="sxs-lookup"><span data-stu-id="9bdb3-112">In **FinishedMsg**, the message store provider:</span></span>
    
  - <span data-ttu-id="9bdb3-113">解除对邮件。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-113">Unlocks the message.</span></span>
    
  - <span data-ttu-id="9bdb3-114">调用[IMAPISupport::DoSentMail](imapisupport-dosentmail.md)方法来执行出站挂接处理如果消息挂接提供程序存在。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-114">Calls the [IMAPISupport::DoSentMail](imapisupport-dosentmail.md) method to perform outbound hook processing if a messaging hook provider exists.</span></span> <span data-ttu-id="9bdb3-115">它然后将邮件复制到**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的项标识符标识的文件夹，如果不取代的消息挂接提供程序的发送消息处理。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-115">It then copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property, if not superseded by a messaging hook provider's sent message processing.</span></span> <span data-ttu-id="9bdb3-116">最后，如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性已设置为 TRUE 删除邮件。</span><span class="sxs-lookup"><span data-stu-id="9bdb3-116">Finally, it deletes the message if the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property has been set to TRUE.</span></span> 
    

