---
title: 提供邮件存储提供程序的读取和未读报告
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9644b8c5-ecc0-4ea3-972a-2169c78b99e5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 96546d3d766af398ff7acb50f4fc3a479b5668b2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432336"
---
# <a name="providing-read-and-nonread-reports-for-message-store-providers"></a><span data-ttu-id="6a156-103">提供邮件存储提供程序的读取和未读报告</span><span class="sxs-lookup"><span data-stu-id="6a156-103">Providing Read and Nonread Reports for Message Store Providers</span></span>

  
  
<span data-ttu-id="6a156-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a156-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a156-105">如果邮件存储提供程序可以接收邮件, 则需要支持对邮件存储提供程序接收的邮件的读取报告和未读报告。</span><span class="sxs-lookup"><span data-stu-id="6a156-105">If a message store provider can receive messages, it is required to support read reports and nonread reports of messages received by the message store provider.</span></span> <span data-ttu-id="6a156-106">如果收到的邮件包含**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性, 并且该属性的值为 TRUE, 则当用户打开邮件时, 邮件存储应向发件人发送一封通知邮件。指示邮件已被阅读。</span><span class="sxs-lookup"><span data-stu-id="6a156-106">If a received message contains the **PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) property and that property's value is TRUE, the message store should send a notification message to the sender when the user opens the message, indicating that the message has been read.</span></span> <span data-ttu-id="6a156-107">同样, 如果用户在打开邮件之前删除了邮件, 邮件存储应向发件人发出答复, 表明该邮件未被阅读。</span><span class="sxs-lookup"><span data-stu-id="6a156-107">Similarly, if the user deletes the message before opening it, the message store should issue a reply to the sender indicating that the message was not read.</span></span>
  
<span data-ttu-id="6a156-108">发出这些报告是为了创建[IMessage: IMAPIProp](imessageimapiprop.md)对象, 填写邮件上的相关属性, 并将其提交到 MAPI 后台处理程序, 就好像邮件是由用户发出的一样。</span><span class="sxs-lookup"><span data-stu-id="6a156-108">Issuing these reports is a matter of creating an [IMessage : IMAPIProp](imessageimapiprop.md) object, filling out the relevant properties on the message, and submitting it to the MAPI spooler as if the message had originated with the user.</span></span> <span data-ttu-id="6a156-109">[IMAPISupport:: ReadReceipt](imapisupport-readreceipt.md)方法可用于此项。</span><span class="sxs-lookup"><span data-stu-id="6a156-109">The [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md) method can be used for this.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6a156-110">当邮件存储区使用挂起的读取或未读报告制作未读邮件的副本时, 必须特别小心。</span><span class="sxs-lookup"><span data-stu-id="6a156-110">Special care must be taken when a message store makes copies of an unread message with pending read or nonread reports.</span></span> <span data-ttu-id="6a156-111">当用户读取已请求报告的邮件的任何副本时, 不应生成此类报告。</span><span class="sxs-lookup"><span data-stu-id="6a156-111">Such reports should not be generated when users read any copies of a message for which reports have been requested.</span></span> <span data-ttu-id="6a156-112">在生成此类邮件的副本时, 邮件存储提供程序应在其对[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)和[IMessage:: SetReadFlag](imessage-setreadflag.md)的调用中包括 CLEAR_RN_PENDING 和 CLEAR_NRN_PENDING 标志。</span><span class="sxs-lookup"><span data-stu-id="6a156-112">When making a copy of such a message, the message store provider should include the CLEAR_RN_PENDING and CLEAR_NRN_PENDING flags in its calls to [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) and [IMessage::SetReadFlag](imessage-setreadflag.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6a156-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a156-113">See also</span></span>



[<span data-ttu-id="6a156-114">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="6a156-114">Message Store Features</span></span>](message-store-features.md)

