---
title: 消息存储提供程序的支持邮件附件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d5fabc40-71e8-4afa-9846-533da605ce6c
description: 上次修改时间： 2015 年 12 月 7 日
ms.openlocfilehash: e3d6844f8fe6121d6ea063a9594aaf1fed581ee5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778898"
---
# <a name="supporting-message-attachments-for-message-store-providers"></a>消息存储提供程序的支持邮件附件

 
  
**适用于**： Outlook 
  
消息存储提供程序不需要支持邮件附件。 但是，多个客户端应用程序还希望能够将附件添加到邮件。 如果您的消息存储将用于创建或存储 IPM。说明消息，则您应支持邮件附件。 默认消息存储提供程序还应支持邮件附件。 有关详细信息，请参阅[MAPI 邮件类](mapi-message-classes.md)和[默认邮件存储区](default-message-stores.md)。
  
有五种类型的附件的 MAPI 支持： 文件附件、 数据附件、 邮件附件、 OLE 对象附件和链接。 支持每种类型的要求具有不同。 客户端区分两种类型的附件通过 attachment 对象的**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。
  
支持附件意味着实现[IAttach: IMAPIProp](iattachimapiprop.md)接口。 此**IAttach**接口具有自己的; 没有方法它具有仅从[IMAPIProp](imapipropiunknown.md)接口继承的方法。 消息存储提供程序必须已实现消息对象的属性，因为这大大简化了支持的附件的任务。 基本上实现**IAttach**意味着提供一种客户端访问的特定邮件的附件的属性表的方法。 
  
数据附件是只需为其直接在附件**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性中存储附件的内容的附件。 数据附件存在主要是为了使客户端可以将文件附加到一条消息，当发件人和收件人的邮件没有访问常见的文件服务器。 有关详细信息，请参阅**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。
  
邮件附件的附件的附件子对象是另一个[IMessage: MAPIProp](imessageimapiprop.md)对象。 由于消息存储提供程序已经支持**IMessage**接口，并不难支持邮件附件。 
  
支持 OLE 对象附件意味着实现 OLE **IStorage**、 **IStream**和**IStreamDocfile**接口。 消息存储提供程序必须能够将客户端打开对象时到活动的 OLE 对象存储在消息中的 OLE 对象数据转换。 
  
链接有两种类型： 指向文件和指向其他消息。 文件的链接以及**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) **PR_ATTACH_METHOD**属性使用 ATTACH_BY_REF_ONLY 值指定文件的位置。
  
一个如何实现指向邮件可能依赖于本地邮件系统的方面，因此，不能完全此处介绍。 例如，将链接发送给一条消息，对基于服务器的消息存储存储通常是消息的只需发送链接，提供的发件人和收件人有权访问该服务器的项标识符。 其他消息的系统配置提供其他要求和实现指向邮件难题。
  
## <a name="see-also"></a>另请参阅



[消息存储功能](message-store-features.md)

