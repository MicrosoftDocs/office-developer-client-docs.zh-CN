---
title: MAPI 对象和属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0aebf536-dcfb-406d-86ac-65db98c78139
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0efc111523ad285d54fc40e37fe83a1130f1d291
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776276"
---
# <a name="mapi-objects-and-properties"></a>MAPI 对象和属性

  
  
**适用于**： Outlook 
  
支持许多不同类型的对象的一些属性。 使用多个对象的属性的示例，以下属性：
  
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 是用于打开对象的二进制标识符。
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 是对象的用于标识类型的常量。
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 是一个字符串，用于描述用户对象。
    
其他属性对单个对象的类型有意义。 适用于一种类型的对象的属性的示例，以下属性：
  
- **PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是邮件的一个字符串，用于描述的类型。
    
- **PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md)) 是整数，用于标识表中的行。
    
- **PR_ATTACH_SIZE**([PidTagAttachSize](pidtagattachsize-canonical-property.md)) 是用于存储附件中的字节数的整数。
    
仍其他属性是仅适用于单个中特定状态对象的类型。 此类型的属性通常是邮件属性。 首次创建一条消息，及其属性集时非常小。 它是由客户端发送给邮件系统通过收件人，增加属性所需描述的消息的数目。 其中一些新增了属性显示仅在邮件上是时其他人显示仅对邮件发送它时被传递。 消息也有与他们所属的类关联的属性。 报告消息，例如，具有不受支持的其他类，如说明消息的消息的属性。 
  
每个对象都具有一些必需的属性和可能或可能没有其他可选属性。 必须先对象可以使用其[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法成功保存在对象存在的属性所需的属性。 客户端或使用对象的服务提供商可以取决于所需的属性的可用性**SaveChanges**调用后。 即，它们可以确保将成功对对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法或[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用，以检索这些属性。 
  
可选属性是，具体取决于对象的实施，也可能不支持由对象的属性。 使用对象的客户端或服务提供程序无法预期可选属性，可通过**GetProps**或**OpenProperty**方法并设置为有效的值。 
  
列表或在此属性的引用，请参阅[MAPI 属性](mapi-properties.md)。 属于邮件的每个属性的说明存储和对象的标准接口的讨论中找不到地址簿对象。 例如，文件夹属性将讨论与**IMAPIFolder**并且与**IMailUser**讨论消息的用户属性。 与**IMessage**和[消息属性概述 （英文）](message-properties-overview.md)中描述了消息属性，包括报表消息属性。 相应的[MAPI 表](mapi-tables.md)主题描述了属于每个表的不同类型的属性。 例如，层次结构表属性详见[层次结构表](hierarchy-tables.md)。 在[选择窗体的属性设置](choosing-a-form-s-property-set.md)描述属于窗体服务器的属性。
  
当客户端或服务提供程序调用对象的**GetProps**方法来检索多个其属性，这些属性是不可用**GetProps**返回警告 MAPI_W_ERRORS_RETURNED。 呼叫被视为是成功，因为返回的一些属性。 不可用的客户端或服务提供程序调用**OpenProperty**和目标属性时，该方法将失败错误 MAPI_E_NOT_FOUND。 请务必选中，然后再尝试使用它返回请求的属性。 
  
根据该对象，提供了实现和属性，服务提供商属性可以具有读/写或只读权限。 读/写权限允许客户端或服务提供商使用的属性来更改其值;只读权限允许仅服务提供商拥有对象进行更改。 
  
若要找出完全哪些属性当前设置的对象，请调用[IMAPIProp::GetPropList](imapiprop-getproplist.md)。 **GetPropList**方法，可以找出了之前尝试打开可能不存在的属性进行的呼叫者。 因为没有任何标准的特定类型的所有对象都支持的属性集，所以不可能猜测对象支持某个特定的属性。 调用**GetPropList**消除了猜测工作。 
  
## <a name="see-also"></a>另请参阅



[MAPI 对象和属性](mapi-objects-and-properties.md)

