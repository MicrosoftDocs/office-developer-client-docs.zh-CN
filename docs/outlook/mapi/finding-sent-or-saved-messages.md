---
title: 查找已发送或保存的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b6714a5-7f36-4a72-9a2a-0d7fdf0e21b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6e8b618e477475e8e7f45c266791086af63d8bfb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774941"
---
# <a name="finding-sent-or-saved-messages"></a><span data-ttu-id="2772f-103">查找已发送或保存的邮件</span><span class="sxs-lookup"><span data-stu-id="2772f-103">Finding Sent or Saved Messages</span></span>

  
  
<span data-ttu-id="2772f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2772f-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="2772f-105">**若要找到已保存或发送的所有传出邮件**</span><span class="sxs-lookup"><span data-stu-id="2772f-105">**To locate all the outgoing messages that you have saved or sent**</span></span>
  
1. <span data-ttu-id="2772f-106">调用[IMsgStore::CompareEntryIDs](imsgstore-compareentryids.md)进行比较的文件夹，包含与包含您的传入邮件的文件夹已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="2772f-106">Call [IMsgStore::CompareEntryIDs](imsgstore-compareentryids.md) to compare the folder that contains your sent messages with the folder that contains your incoming messages.</span></span> 
    
2. <span data-ttu-id="2772f-107">设置以指向**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) _lpEntryID1_参数和_lpEntryID2_参数以指向**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="2772f-107">Set the  _lpEntryID1_ parameter to point to **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) and the  _lpEntryID2_ parameter to point to **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)).</span></span>
    
<span data-ttu-id="2772f-108">请注意，如果它们发送或已移动已发送任何的邮件到另一个文件夹中后，也可以删除邮件，此策略将无法工作。</span><span class="sxs-lookup"><span data-stu-id="2772f-108">Be aware that if you either delete messages after they are sent or have moved any of the sent messages to another folder, this strategy will not work.</span></span> 
  
<span data-ttu-id="2772f-109">如果在检查传入消息您注意到丢失了通常设置由传输提供程序的属性，可以假定该消息已从不处理由传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="2772f-109">If in examining an incoming message you notice that the properties that are typically set by a transport provider are missing, you can assume that the message was never handled by a transport provider.</span></span> <span data-ttu-id="2772f-110">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="2772f-110">These properties include:</span></span>
  
- <span data-ttu-id="2772f-111">**PR_RECEIVED_BY**属性</span><span class="sxs-lookup"><span data-stu-id="2772f-111">**PR_RECEIVED_BY** properties</span></span> 
    
- <span data-ttu-id="2772f-112">**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2772f-112">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="2772f-113">**PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2772f-113">**PR_TRANSPORT_MESSAGE_HEADERS** ([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))</span></span>
    
- <span data-ttu-id="2772f-114">**PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2772f-114">**PR_MESSAGE_TO_ME** ([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))</span></span>
    
- <span data-ttu-id="2772f-115">**PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2772f-115">**PR_MESSAGE_CC_ME** ([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))</span></span>
    
- <span data-ttu-id="2772f-116">**PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2772f-116">**PR_MESSAGE_RECIP_ME** ([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))</span></span>
    

