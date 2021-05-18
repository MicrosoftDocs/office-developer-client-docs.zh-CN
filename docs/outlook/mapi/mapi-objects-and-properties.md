---
title: MAPI 对象和属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0aebf536-dcfb-406d-86ac-65db98c78139
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7fef84b7519c7a9d6373198283e903fba4fd0780
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411209"
---
# <a name="mapi-objects-and-properties"></a>MAPI 对象和属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
许多不同类型的对象支持某些属性。 下列属性是多个对象使用的属性示例：
  
- **PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) 是一个二进制标识符，用于打开对象。
    
- **PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) 是一个用来标识对象类型的常量。
    
- **PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 是一个字符串，用于向用户描述对象。
    
其他属性对单一类型的对象有意义。 以下属性是应用于一种类型的对象的属性示例：
  
- **PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是一个用于描述邮件类型的字符串。
    
- **PR_ROWID (** [PidTagRowid](pidtagrowid-canonical-property.md)) 是一个整数，用于标识表格中的行。
    
- **PR_ATTACH_SIZE (** [PidTagAttachSize](pidtagattachsize-canonical-property.md)) 是一个整数，用于存储附件中的字节数。
    
此外，其他属性仅适用于处于特定状态中的单一类型对象。 此类型的属性通常是邮件属性。 首次创建邮件时，其属性集很小。 由于客户端通过邮件系统将邮件发送给收件人，因此描述邮件所需的属性数会增加。 其中一些添加的属性仅在邮件传递时显示，而其他属性仅在邮件发送时出现在邮件上。 邮件还具有与其所属的类关联的属性。 例如，报告邮件具有其他类的邮件不支持的属性，例如便笺邮件。 
  
每个对象都有一些必需的属性，并且可能（也可能没有）其他可选属性。 必需属性是对象上必须存在的属性，然后才能使用 [对象的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法成功保存该对象。 使用对象的客户端或服务提供商可能依赖于 **SaveChanges** 调用后所需属性的可用性。 也就是说，他们可以确保调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法或 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法来检索这些属性将成功。 
  
可选属性是对象可能支持也可能不受对象支持的属性，具体取决于对象的实现者。 使用 对象的客户端或服务提供商无法期望可选属性通过 **GetProps** 或 **OpenProperty** 方法可用并设置为有效值。 
  
有关此参考中的列表或属性，请参阅 [MAPI Properties](mapi-properties.md)。 有关属于每个邮件存储和通讯簿对象的属性的说明，请参阅对象的标准接口讨论。 例如，使用 **IMAPIFolder** 讨论文件夹属性，使用 **IMailUser** 讨论邮件用户属性。 Message properties， including report message properties， are described with **IMessage** and in [Message Properties Overview](message-properties-overview.md). 适当的 [MAPI](mapi-tables.md) 表主题中介绍了属于每种不同类型的表的属性。 例如，层次结构表属性在 [Hierarchy Tables 中进行了介绍](hierarchy-tables.md)。 Choosing [a Form's Property Set](choosing-a-form-s-property-set.md)中描述了属于表单服务器的属性。
  
当客户端或服务提供商调用对象的 **GetProps** 方法来检索其多个属性，并且其中一个属性不可用时 **，GetProps** 将返回警告MAPI_W_ERRORS_RETURNED。 调用被视为成功，因为返回了一些属性。 当客户端或服务提供商调用 **OpenProperty** 并且目标属性不可用时，该方法将失败，并返回MAPI_E_NOT_FOUND。 在尝试使用请求的属性之前，检查是否返回了请求的属性，这一点很重要。 
  
根据对象、提供实现的服务提供程序和 属性，属性可以具有读/写或只读权限。 读/写权限允许客户端或服务提供商使用 属性更改其值;只读权限仅允许拥有该对象的服务提供商进行更改。 
  
若要准确找出当前为对象设置的属性，请调用 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)。 **GetPropList** 方法允许调用方在尝试打开可能不存在的属性之前找到可用项。 由于不存在特定类型的所有对象都支持的标准属性集，因此无法猜测对象是否支持特定属性。 调用 **GetPropList** 可消除猜测工作。 
  
## <a name="see-also"></a>另请参阅



[MAPI 对象和属性](mapi-objects-and-properties.md)

