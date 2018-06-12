---
title: 消息存储提供程序提供读取和 Nonread 的报告
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
# <a name="providing-read-and-nonread-reports-for-message-store-providers"></a>消息存储提供程序提供读取和 Nonread 的报告

  
  
**适用于**： Outlook 
  
如果消息存储提供程序可以接收邮件，则需要支持阅读的报告和邮件存储提供程序接收的消息的 nonread 的报告。 如果收到的邮件包含**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性，该属性值为 TRUE 的消息存储应向发送一封通知邮件发件人在用户打开邮件时指示邮件已被阅读。 同样，如果用户删除邮件，然后再打开它，消息存储应发出对指示未被阅读邮件发件人的回复。
  
发出这些报告是一种创建[IMessage: IMAPIProp](imessageimapiprop.md)对象，填写相关属性在的消息，并将其提交到 MAPI 后台处理程序，就好像具有与用户发送邮件。 [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md)方法可用于此。 
  
> [!NOTE]
> 消息存储指定带挂起的读或 nonread 报告的未读邮件的副本时，必须采取特别注意。 当用户读取为其请求报告一条消息的所有副本时，应不会生成此类报告。 此类消息副本时，消息存储提供程序应包括[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)和[IMessage::SetReadFlag](imessage-setreadflag.md)对其调用 CLEAR_RN_PENDING 和 CLEAR_NRN_PENDING 标志。 
  
## <a name="see-also"></a>另请参阅



[消息存储功能](message-store-features.md)

