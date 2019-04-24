---
title: 支持邮件存储提供程序的邮件附件
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d5fabc40-71e8-4afa-9846-533da605ce6c
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 69d1df5bf206cddd0d25698665c9fd87b81e4ea5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350622"
---
# <a name="supporting-message-attachments-for-message-store-providers"></a>支持邮件存储提供程序的邮件附件

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您的邮件存储提供程序不需要支持邮件附件。 但是, 许多客户端应用程序希望能够将附件添加到邮件中。 如果您的邮件存储将用于创建或存储 IPM。注释邮件, 则应支持邮件附件。 默认邮件存储提供程序还应支持邮件附件。 有关详细信息, 请参阅[MAPI 邮件类别](mapi-message-classes.md)和[默认邮件存储](default-message-stores.md)。
  
MAPI 支持以下五种类型的附件: 文件附件、数据附件、邮件附件、OLE 对象附件和链接。 支持每种类型的要求各不相同。 客户端通过附件对象上的**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性来区分这两种类型的附件。
  
支持附件是指实现[IAttach: IMAPIProp](iattachimapiprop.md)接口。 **IAttach**接口本身没有自己的方法;它仅具有从[IMAPIProp](imapipropiunknown.md)接口继承的方法。 由于您的邮件存储区提供程序必须已实现邮件对象的属性, 因此这极大地简化了支持附件的任务。 实现**IAttach**基本上意味着提供一种方法, 使客户端可以访问邮件中特定附件的属性表。 
  
数据附件只是附件内容直接存储在附件的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性中的附件。 数据附件主要用于允许客户端在邮件的发件人和收件人无法访问公用文件服务器时将文件附加到邮件。 有关详细信息, 请参阅**PR_ATTACH_METHOD** ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。
  
邮件附件是附件子对象是另一个[IMessage: MAPIProp](imessageimapiprop.md)对象的附件。 因为邮件存储提供程序已经支持**IMessage**接口, 所以支持邮件附件并不难。 
  
支持 ole 对象附件是指实现 ole **IStorage**、 **IStream**和**IStreamDocfile**接口。 当客户端打开对象时, 您的邮件存储区提供程序必须能够将邮件中存储的 ole 对象数据转换为活动的 OLE 对象。 
  
链接分为两种类型: 指向指向其他邮件的文件和链接的链接。 指向文件的链接使用**PR_ATTACH_METHOD**属性的 ATTACH_BY_REF_ONLY 值以及**PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 来指定文件的位置。
  
如何实现邮件的链接可能取决于本地邮件系统的各个方面, 因此无法在此处完全记录。 例如, 发送指向存储在基于服务器的邮件存储在邮件上的邮件的链接通常只是发送链接邮件的条目标识符, 从而使发件人和收件人都有权访问该服务器。 其他邮件系统配置提供了对邮件链接实施的其他要求和挑战。
  
## <a name="see-also"></a>另请参阅



[邮件存储区功能](message-store-features.md)

