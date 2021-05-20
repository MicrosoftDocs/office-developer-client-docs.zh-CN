---
title: 查找已发送或已保存的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b6714a5-7f36-4a72-9a2a-0d7fdf0e21b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86373fae2753df66d4456cc0fc00f8b289977650
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437418"
---
# <a name="finding-sent-or-saved-messages"></a><span data-ttu-id="85a5d-103">查找已发送或已保存的邮件</span><span class="sxs-lookup"><span data-stu-id="85a5d-103">Finding Sent or Saved Messages</span></span>

  
  
<span data-ttu-id="85a5d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85a5d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="85a5d-105">**查找已保存或发送的所有传出邮件**</span><span class="sxs-lookup"><span data-stu-id="85a5d-105">**To locate all the outgoing messages that you have saved or sent**</span></span>
  
1. <span data-ttu-id="85a5d-106">调用 [IMsgStore：：CompareEntryIDs](imsgstore-compareentryids.md) 将包含已发送邮件的文件夹与包含传入邮件的文件夹进行比较。</span><span class="sxs-lookup"><span data-stu-id="85a5d-106">Call [IMsgStore::CompareEntryIDs](imsgstore-compareentryids.md) to compare the folder that contains your sent messages with the folder that contains your incoming messages.</span></span> 
    
2. <span data-ttu-id="85a5d-107">将  _lpEntryID1_ 参数设置为指向 **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) ，将  _lpEntryID2_ 参数设置为指向 **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="85a5d-107">Set the  _lpEntryID1_ parameter to point to **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) and the  _lpEntryID2_ parameter to point to **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="85a5d-108">请注意，如果在邮件发送后删除邮件或将任何已发送的邮件移动到另一个文件夹，此策略将不起作用。</span><span class="sxs-lookup"><span data-stu-id="85a5d-108">Be aware that if you either delete messages after they are sent or have moved any of the sent messages to another folder, this strategy will not work.</span></span> 
  
<span data-ttu-id="85a5d-109">如果在检查传入邮件时注意到传输提供程序通常设置的属性缺失，您可以假定该邮件从未由传输提供程序处理过。</span><span class="sxs-lookup"><span data-stu-id="85a5d-109">If in examining an incoming message you notice that the properties that are typically set by a transport provider are missing, you can assume that the message was never handled by a transport provider.</span></span> <span data-ttu-id="85a5d-110">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="85a5d-110">These properties include:</span></span>
  
- <span data-ttu-id="85a5d-111">**PR_RECEIVED_BY** 属性</span><span class="sxs-lookup"><span data-stu-id="85a5d-111">**PR_RECEIVED_BY** properties</span></span> 
    
- <span data-ttu-id="85a5d-112">**PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="85a5d-112">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="85a5d-113">**PR_TRANSPORT_MESSAGE_HEADERS (** [PidTagTransportMessageHeaders)](pidtagtransportmessageheaders-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="85a5d-113">**PR_TRANSPORT_MESSAGE_HEADERS** ([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span></span>
    
- <span data-ttu-id="85a5d-114">**PR_MESSAGE_TO_ME (** [PidTagMessageToMe)](pidtagmessagetome-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="85a5d-114">**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))</span></span>
    
- <span data-ttu-id="85a5d-115">**PR_MESSAGE_CC_ME (** [PidTagMessageCcMe)](pidtagmessageccme-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="85a5d-115">**PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))</span></span>
    
- <span data-ttu-id="85a5d-116">**PR_MESSAGE_RECIP_ME (** [PidTagMessageRecipientMe)](pidtagmessagerecipientme-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="85a5d-116">**PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))</span></span>
    

