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
ms.openlocfilehash: 880731bf204778cde21da6cd9024a3ca86c6f6a5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434674"
---
# <a name="processing-a-sent-message"></a><span data-ttu-id="ad1ca-103">处理已发送的邮件</span><span class="sxs-lookup"><span data-stu-id="ad1ca-103">Processing a Sent Message</span></span>

  
  
<span data-ttu-id="ad1ca-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad1ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad1ca-105">发送的邮件在发送之后可以保留在 "发件箱" 文件夹中, 移动到指定用于保留已发送邮件的文件夹中, 或被删除。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-105">Outgoing messages, after they have been sent, can be left in the Outbox folder, moved to a folder designated to hold sent messages, or deleted.</span></span> <span data-ttu-id="ad1ca-106">处理的类型取决于是否设置了邮件存储库属性:</span><span class="sxs-lookup"><span data-stu-id="ad1ca-106">The type of processing depends on whether or not you have set the message store properties:</span></span>
  
- <span data-ttu-id="ad1ca-107">**PR_DELETE_AFTER_SUBMIT**([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ad1ca-107">**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md))</span></span> 
    
- <span data-ttu-id="ad1ca-108">**PR_SENTMAIL_ENTRYID**([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="ad1ca-108">**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md))</span></span> 
    
 <span data-ttu-id="ad1ca-109">**PR_DELETE_AFTER_SUBMIT**是一个布尔属性, 如果邮件发送后应将其删除, 则设置为 TRUE, 否则设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-109">**PR_DELETE_AFTER_SUBMIT** is a Boolean property, set to TRUE if messages should be deleted after they are sent, and FALSE otherwise.</span></span> <span data-ttu-id="ad1ca-110">**PR_SENTMAIL_ENTRYID**是文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-110">**PR_SENTMAIL_ENTRYID** is the entry identifier of a folder.</span></span> <span data-ttu-id="ad1ca-111">设置此属性时, 应将已发送的邮件移动到此条目标识符所表示的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-111">When this property is set, you should move sent messages to the folder represented by this entry identifier.</span></span> <span data-ttu-id="ad1ca-112">保存的邮件通常具有最后的邮件存储或传输提供程序的标识, 以发送它们。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-112">The saved messages typically have the identity of the last message store or transport provider to send them.</span></span> 
  
<span data-ttu-id="ad1ca-113">应设置其中一个或多个属性, 但不能同时设置这两个属性中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-113">Either one or the other, or neither of these properties should be set, but not both.</span></span> <span data-ttu-id="ad1ca-114">但是, 如果设置**PR_SENTMAIL_ENTRYID**, 则它必须包含有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-114">However, if you set **PR_SENTMAIL_ENTRYID**, it must contain a valid entry identifier.</span></span> 
  
<span data-ttu-id="ad1ca-115">下表描述了这些属性如何影响您对已发送邮件所执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-115">The following table describes how these properties affect what you do with sent messages.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ad1ca-116">如果两个属性都不设置:</span><span class="sxs-lookup"><span data-stu-id="ad1ca-116">If neither property is set:</span></span>  <br/> |<span data-ttu-id="ad1ca-117">将邮件保留在发送邮件的文件夹中 (通常为 "发件箱")。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-117">Leave the message in the folder from which it was sent (typically the Outbox).</span></span>  <br/> |
|<span data-ttu-id="ad1ca-118">如果设置了**PR_SENTMAIL_ENTRYID** :</span><span class="sxs-lookup"><span data-stu-id="ad1ca-118">If **PR_SENTMAIL_ENTRYID** is set:</span></span>  <br/> |<span data-ttu-id="ad1ca-119">将邮件移动到指定的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-119">Move the message to the indicated folder.</span></span>  <br/> |
|<span data-ttu-id="ad1ca-120">如果设置了**PR_DELETE_AFTER_SUBMIT** :</span><span class="sxs-lookup"><span data-stu-id="ad1ca-120">If **PR_DELETE_AFTER_SUBMIT** is set:</span></span>  <br/> |<span data-ttu-id="ad1ca-121">删除邮件。</span><span class="sxs-lookup"><span data-stu-id="ad1ca-121">Delete the message.</span></span>  <br/> |
   

