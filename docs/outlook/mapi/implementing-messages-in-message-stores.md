---
title: 实现邮件存储区中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df5003d5-cbfe-40b2-a481-e2e11dce4b3e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c21fea9b0c8de96f427c4bcdfabfde3a0032f0c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775811"
---
# <a name="implementing-messages-in-message-stores"></a>实现邮件存储区中的邮件

  
  
**适用于**： Outlook 
  
[IMessage: IMAPIProp](imessageimapiprop.md)接口是类似于[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口中的两个接口派生[IMAPIProp: IUnknown](imapipropiunknown.md)接口。 客户端使用**IMAPIProp**方法访问一条消息的内容。 **IMessage**接口提供用于处理邮件 （例如，将附件添加或修改邮件的收件人） 的其他方法。 **IMessage**接口中的方法修改的消息不直接在该消息属性中存储的属性。 
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

