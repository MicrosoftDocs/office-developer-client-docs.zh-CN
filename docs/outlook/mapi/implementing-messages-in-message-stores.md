---
title: 在邮件存储区中实施邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df5003d5-cbfe-40b2-a481-e2e11dce4b3e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 223dfa2ac990875e98e876ab491bf09caf63e874
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310092"
---
# <a name="implementing-messages-in-message-stores"></a>在邮件存储区中实施邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
[IMessage: IMAPIProp](imessageimapiprop.md)接口类似于[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口, 这两个接口均派生自[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 客户端使用**IMAPIProp**方法访问邮件的内容。 **IMessage**接口提供用于处理邮件的其他方法 (例如, 添加附件或修改邮件的收件人)。 **IMessage**接口中的方法可修改未直接存储在邮件属性中的邮件的属性。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

