---
title: 发送邮件 MAPI 后台处理程序任务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 81c65f21-03ba-43eb-a6d4-d311e660ac5c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8a6730cca5c75a888afb5ff0a44f1e2a0a6465e6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339674"
---
# <a name="sending-messages-mapi-spooler-tasks"></a><span data-ttu-id="11ee9-103">发送邮件: MAPI 后台处理程序任务</span><span class="sxs-lookup"><span data-stu-id="11ee9-103">Sending Messages: MAPI Spooler Tasks</span></span>

  
  
<span data-ttu-id="11ee9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="11ee9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="11ee9-105">当邮件存储区与传输提供程序不紧密结合时, 如果紧耦合存储和传输无法处理收件人, 以及当邮件需要预处理时, MAPI 后台处理程序将包含在邮件传输过程中。</span><span class="sxs-lookup"><span data-stu-id="11ee9-105">The MAPI spooler is involved in the message transmission process when the message store is not tightly coupled with a transport provider, when the tightly coupled store and transport cannot handle a recipient, and when the message requires preprocessing.</span></span>
  
 <span data-ttu-id="11ee9-106">**在进行任何必要的预处理后, MAPI 后台处理程序将执行以下步骤:**</span><span class="sxs-lookup"><span data-stu-id="11ee9-106">**After any necessary preprocessing, the MAPI spooler performs the following steps:**</span></span>
  
1. <span data-ttu-id="11ee9-107">如果邮件未锁定, 则使用[IMsgStore:: SetLockState](imsgstore-setlockstate.md)方法锁定邮件。</span><span class="sxs-lookup"><span data-stu-id="11ee9-107">If the message is not locked, locks the message by using the [IMsgStore::SetLockState](imsgstore-setlockstate.md) method.</span></span> 
    
2. <span data-ttu-id="11ee9-108">使传输提供程序将邮件发送给将其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE 的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="11ee9-108">Has the transport provider send the message to all recipients that have their **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) property set to FALSE.</span></span> 
    
3. <span data-ttu-id="11ee9-109">调用适当的函数 ([RemovePreprocessInfo](removepreprocessinfo.md)) 来清除添加到邮件中以供在预处理过程中使用的任何其他信息 (如果已设置**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性)。</span><span class="sxs-lookup"><span data-stu-id="11ee9-109">Calls the appropriate function ([RemovePreprocessInfo](removepreprocessinfo.md)) for cleaning up any additional information that was added to the message for use during preprocessing if the **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) property has been set.</span></span> <span data-ttu-id="11ee9-110">此函数在传输提供程序注册其预处理器函数时指定。</span><span class="sxs-lookup"><span data-stu-id="11ee9-110">This function is specified when the transport provider registers its preprocessor function.</span></span> 
    
4. <span data-ttu-id="11ee9-111">调用[IMsgStore:: FinishedMsg](imsgstore-finishedmsg.md)方法。</span><span class="sxs-lookup"><span data-stu-id="11ee9-111">Calls [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md) method.</span></span> <span data-ttu-id="11ee9-112">在**FinishedMsg**中, 邮件存储区提供程序:</span><span class="sxs-lookup"><span data-stu-id="11ee9-112">In **FinishedMsg**, the message store provider:</span></span>
    
  - <span data-ttu-id="11ee9-113">解除对邮件的锁定。</span><span class="sxs-lookup"><span data-stu-id="11ee9-113">Unlocks the message.</span></span>
    
  - <span data-ttu-id="11ee9-114">调用[IMAPISupport::D osentmail](imapisupport-dosentmail.md)方法来执行出站挂钩处理 (如果存在消息传递挂钩提供程序)。</span><span class="sxs-lookup"><span data-stu-id="11ee9-114">Calls the [IMAPISupport::DoSentMail](imapisupport-dosentmail.md) method to perform outbound hook processing if a messaging hook provider exists.</span></span> <span data-ttu-id="11ee9-115">然后, 它将邮件复制到由**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的条目标识符标识的文件夹中 (如果不是由邮件传递挂钩提供程序的已发送邮件处理取代的)。</span><span class="sxs-lookup"><span data-stu-id="11ee9-115">It then copies the message to the folder identified by the entry identifier in the **PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) property, if not superseded by a messaging hook provider's sent message processing.</span></span> <span data-ttu-id="11ee9-116">最后, 如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE, 则删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="11ee9-116">Finally, it deletes the message if the **PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) property has been set to TRUE.</span></span> 
    

