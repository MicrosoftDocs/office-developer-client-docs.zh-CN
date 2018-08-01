---
title: 处理已发送的邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 55b3e692-753d-45e9-a40d-22adc81b75da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cea1a1008ecbff698b757d6c67af5c279954656
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778546"
---
# <a name="processing-a-sent-message"></a><span data-ttu-id="2e7f1-103">处理已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="2e7f1-103">Processing a Sent Message</span></span>

  
  
<span data-ttu-id="2e7f1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2e7f1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2e7f1-105">传出消息后被发送，可以处于发件箱文件夹，移动到文件夹指定用于保存已发送邮件，或删除。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-105">Outgoing messages, after they have been sent, can be left in the Outbox folder, moved to a folder designated to hold sent messages, or deleted.</span></span> <span data-ttu-id="2e7f1-106">处理的类型取决于已设置属性存储的邮件：</span><span class="sxs-lookup"><span data-stu-id="2e7f1-106">The type of processing depends on whether or not you have set the message store properties:</span></span>
  
- <span data-ttu-id="2e7f1-107">**PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2e7f1-107">**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span></span> 
    
- <span data-ttu-id="2e7f1-108">**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2e7f1-108">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span> 
    
 <span data-ttu-id="2e7f1-109">**PR_DELETE_AFTER_SUBMIT**为布尔值属性，否则设置为 TRUE 如果应在后发送，删除消息和 FALSE。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-109">**PR_DELETE_AFTER_SUBMIT** is a Boolean property, set to TRUE if messages should be deleted after they are sent, and FALSE otherwise.</span></span> <span data-ttu-id="2e7f1-110">**PR_SENTMAIL_ENTRYID**是文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-110">**PR_SENTMAIL_ENTRYID** is the entry identifier of a folder.</span></span> <span data-ttu-id="2e7f1-111">当设置此属性时，您应将已发送的邮件移动到表示此项标识符的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-111">When this property is set, you should move sent messages to the folder represented by this entry identifier.</span></span> <span data-ttu-id="2e7f1-112">保存的邮件通常具有标识的最后一个消息存储或传输提供程序将发送给他们。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-112">The saved messages typically have the identity of the last message store or transport provider to send them.</span></span> 
  
<span data-ttu-id="2e7f1-113">一个或其他，或两个属性都不应设置，但不是能同时。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-113">Either one or the other, or neither of these properties should be set, but not both.</span></span> <span data-ttu-id="2e7f1-114">但是，如果您设置**PR_SENTMAIL_ENTRYID**，它必须包含一个有效项标识符。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-114">However, if you set **PR_SENTMAIL_ENTRYID**, it must contain a valid entry identifier.</span></span> 
  
<span data-ttu-id="2e7f1-115">下表描述了这些属性如何影响您对于已发送邮件的处理。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-115">The following table describes how these properties affect what you do with sent messages.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2e7f1-116">如果既属性设置：</span><span class="sxs-lookup"><span data-stu-id="2e7f1-116">If neither property is set:</span></span>  <br/> |<span data-ttu-id="2e7f1-117">将邮件保留从中发送 （通常发件箱） 的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-117">Leave the message in the folder from which it was sent (typically the Outbox).</span></span>  <br/> |
|<span data-ttu-id="2e7f1-118">如果设置**PR_SENTMAIL_ENTRYID** :</span><span class="sxs-lookup"><span data-stu-id="2e7f1-118">If **PR_SENTMAIL_ENTRYID** is set:</span></span>  <br/> |<span data-ttu-id="2e7f1-119">将邮件移动到指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-119">Move the message to the indicated folder.</span></span>  <br/> |
|<span data-ttu-id="2e7f1-120">如果设置**PR_DELETE_AFTER_SUBMIT** :</span><span class="sxs-lookup"><span data-stu-id="2e7f1-120">If **PR_DELETE_AFTER_SUBMIT** is set:</span></span>  <br/> |<span data-ttu-id="2e7f1-121">删除邮件。</span><span class="sxs-lookup"><span data-stu-id="2e7f1-121">Delete the message.</span></span>  <br/> |
   

