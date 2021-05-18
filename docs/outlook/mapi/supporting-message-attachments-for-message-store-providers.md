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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412133"
---
# <a name="supporting-message-attachments-for-message-store-providers"></a>支持邮件存储提供程序的邮件附件

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您的邮件存储提供程序不需要支持邮件附件。 但是，许多客户端应用程序希望能够向邮件添加附件。 如果你的邮件存储将用于创建或存储 IPM。请注意邮件，然后应支持邮件附件。 默认邮件存储提供程序还应支持邮件附件。 有关详细信息，请参阅[MAPI Message Classes](mapi-message-classes.md)和[Default Message Stores。](default-message-stores.md)
  
MAPI 支持五种类型的附件：文件附件、数据附件、邮件附件、OLE 对象附件和链接。 支持每种类型的要求是不同的。 客户端通过附件对象的[PidTagAttachMethod PR_ATTACH_METHOD (PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 区分这两种类型的附件。 
  
支持附件意味着实现 [IAttach ： IMAPIProp](iattachimapiprop.md) 接口。 **IAttach** 接口没有其自己的方法;它只有从 [IMAPIProp](imapipropiunknown.md)接口继承的方法。 由于邮件存储提供程序必须已经实现邮件对象的属性，这大大简化了支持附件的任务。 实现 **IAttach 基本上** 意味着为客户端提供访问邮件上特定附件的属性表的方法。 
  
数据附件只是附件附件的内容直接存储在附件的 PR_ATTACH_DATA_BIN ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 附件。  数据附件主要是为了允许客户端在邮件的发件人和收件人无法访问公用文件服务器时将文件附加到邮件。 有关详细信息，请参阅 PR_ATTACH_METHOD  ([PidTagAttachMethod](pidtagattachmethod-canonical-property.md)) 属性。
  
邮件附件是附件子对象是另一 [个 IMessage ： MAPIProp 对象的](imessageimapiprop.md) 附件。 由于邮件存储提供程序已经支持 **IMessage** 接口，因此支持邮件附件并不困难。 
  
支持 OLE 对象附件意味着实现 OLE **IStorage、IStream** 和 **IStreamDocfile** 接口。 当客户端打开邮件时，邮件存储提供程序必须能够将邮件中存储的 OLE 对象数据转换为活动 OLE 对象。 
  
链接有两种类型：指向文件的链接和指向其他邮件的链接。 指向文件的链接使用 **PR_ATTACH_METHOD** 属性的 ATTACH_BY_REF_ONLY 值以及 **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或 **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 来指定文件的位置。
  
实现指向邮件的链接可能取决于本地邮件系统的各个方面，因此无法在此处完整记录。 例如，向基于服务器的邮件存储中存储的邮件发送链接通常只是发送链接邮件的条目标识符，只要发件人和收件人都有权访问该服务器。 其他邮件系统配置对实现指向邮件的链接提出了其他要求和难题。
  
## <a name="see-also"></a>另请参阅



[邮件存储功能](message-store-features.md)

