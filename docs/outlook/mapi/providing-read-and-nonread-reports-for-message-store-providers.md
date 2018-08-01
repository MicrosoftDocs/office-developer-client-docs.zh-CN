---
title: 为邮件存储区提供程序提供读取和未读报告
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9644b8c5-ecc0-4ea3-972a-2169c78b99e5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b082d063cc77be46fcd3d4e07ec6753f78f8f335
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778607"
---
# <a name="providing-read-and-nonread-reports-for-message-store-providers"></a><span data-ttu-id="290ad-103">为邮件存储区提供程序提供读取和未读报告</span><span class="sxs-lookup"><span data-stu-id="290ad-103">Providing Read and Nonread Reports for Message Store Providers</span></span>

  
  
<span data-ttu-id="290ad-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="290ad-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="290ad-105">如果消息存储提供程序可以接收邮件，则需要支持阅读的报告和邮件存储提供程序接收的消息的 nonread 的报告。</span><span class="sxs-lookup"><span data-stu-id="290ad-105">If a message store provider can receive messages, it is required to support read reports and nonread reports of messages received by the message store provider.</span></span> <span data-ttu-id="290ad-106">如果收到的邮件包含**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，该属性值为 TRUE 的消息存储应向发送一封通知邮件发件人在用户打开邮件时指示邮件已被阅读。</span><span class="sxs-lookup"><span data-stu-id="290ad-106">If a received message contains the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property and that property's value is TRUE, the message store should send a notification message to the sender when the user opens the message, indicating that the message has been read.</span></span> <span data-ttu-id="290ad-107">同样，如果用户删除邮件，然后再打开它，消息存储应发出对指示未被阅读邮件发件人的回复。</span><span class="sxs-lookup"><span data-stu-id="290ad-107">Similarly, if the user deletes the message before opening it, the message store should issue a reply to the sender indicating that the message was not read.</span></span>
  
<span data-ttu-id="290ad-108">发出这些报告是一种创建[IMessage: IMAPIProp](imessageimapiprop.md)对象，填写相关属性在的消息，并将其提交到 MAPI 后台处理程序，就好像具有与用户发送邮件。</span><span class="sxs-lookup"><span data-stu-id="290ad-108">Issuing these reports is a matter of creating an [IMessage : IMAPIProp](imessageimapiprop.md) object, filling out the relevant properties on the message, and submitting it to the MAPI spooler as if the message had originated with the user.</span></span> <span data-ttu-id="290ad-109">[IMAPISupport::ReadReceipt](imapisupport-readreceipt.md)方法可用于此。</span><span class="sxs-lookup"><span data-stu-id="290ad-109">The [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md) method can be used for this.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="290ad-110">消息存储指定带挂起的读或 nonread 报告的未读邮件的副本时，必须采取特别注意。</span><span class="sxs-lookup"><span data-stu-id="290ad-110">Special care must be taken when a message store makes copies of an unread message with pending read or nonread reports.</span></span> <span data-ttu-id="290ad-111">当用户读取为其请求报告一条消息的所有副本时，应不会生成此类报告。</span><span class="sxs-lookup"><span data-stu-id="290ad-111">Such reports should not be generated when users read any copies of a message for which reports have been requested.</span></span> <span data-ttu-id="290ad-112">此类消息副本时，消息存储提供程序应包括[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)和[IMessage::SetReadFlag](imessage-setreadflag.md)对其调用 CLEAR_RN_PENDING 和 CLEAR_NRN_PENDING 标志。</span><span class="sxs-lookup"><span data-stu-id="290ad-112">When making a copy of such a message, the message store provider should include the CLEAR_RN_PENDING and CLEAR_NRN_PENDING flags in its calls to [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) and [IMessage::SetReadFlag](imessage-setreadflag.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="290ad-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="290ad-113">See also</span></span>



[<span data-ttu-id="290ad-114">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="290ad-114">Message Store Features</span></span>](message-store-features.md)

