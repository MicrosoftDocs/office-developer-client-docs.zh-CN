---
title: 实现邮件存储中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df5003d5-cbfe-40b2-a481-e2e11dce4b3e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 223dfa2ac990875e98e876ab491bf09caf63e874
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416641"
---
# <a name="implementing-messages-in-message-stores"></a>实现邮件存储中的邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
[IMessage ： IMAPIProp](imessageimapiprop.md)接口类似于[IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)接口，因为两个接口都派生自[IMAPIProp ： IUnknown](imapipropiunknown.md)接口。 客户端使用 **IMAPIProp** 方法访问邮件的内容。 **IMessage** 接口提供用于处理邮件 (其他方法，例如添加附件或修改邮件收件人) 。 **IMessage 接口** 中的方法修改未直接存储在邮件属性中的邮件的属性。 
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

