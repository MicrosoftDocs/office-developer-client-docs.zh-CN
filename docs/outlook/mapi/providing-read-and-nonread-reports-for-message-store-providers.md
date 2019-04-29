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
# <a name="providing-read-and-nonread-reports-for-message-store-providers"></a>提供邮件存储提供程序的读取和未读报告

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件存储提供程序可以接收邮件, 则需要支持对邮件存储提供程序接收的邮件的读取报告和未读报告。 如果收到的邮件包含**PR_READ_RECEIPT_REQUESTED** ([PidTagReadReceiptRequested](pidtagreadreceiptrequested-canonical-property.md)) 属性, 并且该属性的值为 TRUE, 则当用户打开邮件时, 邮件存储应向发件人发送一封通知邮件。指示邮件已被阅读。 同样, 如果用户在打开邮件之前删除了邮件, 邮件存储应向发件人发出答复, 表明该邮件未被阅读。
  
发出这些报告是为了创建[IMessage: IMAPIProp](imessageimapiprop.md)对象, 填写邮件上的相关属性, 并将其提交到 MAPI 后台处理程序, 就好像邮件是由用户发出的一样。 [IMAPISupport:: ReadReceipt](imapisupport-readreceipt.md)方法可用于此项。 
  
> [!NOTE]
> 当邮件存储区使用挂起的读取或未读报告制作未读邮件的副本时, 必须特别小心。 当用户读取已请求报告的邮件的任何副本时, 不应生成此类报告。 在生成此类邮件的副本时, 邮件存储提供程序应在其对[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)和[IMessage:: SetReadFlag](imessage-setreadflag.md)的调用中包括 CLEAR_RN_PENDING 和 CLEAR_NRN_PENDING 标志。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

