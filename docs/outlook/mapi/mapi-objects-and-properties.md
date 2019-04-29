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
  
许多不同类型的对象都支持某些属性。 以下属性是多个对象使用的属性示例:
  
- **PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md)) 是用于打开对象的二进制标识符。
    
- **PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md)) 是一个常量, 用于标识对象的类型。
    
- **PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 是用于向用户描述对象的字符字符串。
    
其他属性对一种类型的对象很有意义。 以下属性是应用于一种类型的对象的属性示例:
  
- **PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 是用于描述邮件类型的字符字符串。
    
- **PR_ROWID**([PidTagRowid](pidtagrowid-canonical-property.md)) 是用于标识表中的行的整数。
    
- **PR_ATTACH_SIZE**([PidTagAttachSize](pidtagattachsize-canonical-property.md)) 是一个整数, 用于存储附件中的字节数。
    
仍有一些其他属性仅适用于特定状态中的一种类型的对象。 此类型的属性通常是邮件属性。 首次创建邮件时, 它的一组属性非常小。 当客户端通过邮件系统发送给收件人时, 描述邮件所需的属性数会增加。 某些添加的属性仅在邮件传递过程中显示在邮件中, 而其他属性仅在邮件发送时显示在邮件上。 邮件还具有与它们所属的类关联的属性。 例如, 报告邮件具有其他类的邮件不支持的属性, 如注释消息。 
  
每个对象都有一些必需的属性, 并且可能有也可能不包含其他可选属性。 必需属性是对象在可以使用其[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法成功保存之前必须存在于对象上的属性。 使用对象的客户端或服务提供程序可以依赖于**SaveChanges**调用之后所需属性的可用性。 也就是说, 它们可以确保对对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法或[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用, 以检索这些属性将会成功。 
  
可选属性是一些属性, 取决于对象的实施者, 对象可能支持也可能不支持这些属性。 使用该对象的客户端或服务提供程序不能预期可通过**GetProps**或**OpenProperty**方法使用的可选属性并将其设置为有效的值。 
  
有关此引用中的列表或属性, 请参阅[MAPI 属性](mapi-properties.md)。 有关每个邮件存储和通讯簿对象的属性的说明, 可参阅对象的标准界面的讨论。 例如, **IMAPIFolder**和消息用户属性与**IMailUser**讨论的文件夹属性一起讨论。 邮件属性 (包括报告邮件属性) 在**IMessage**和[邮件属性概述](message-properties-overview.md)中进行了介绍。 在相应的[MAPI 表](mapi-tables.md)主题中介绍了属于每种不同类型的表的属性。 例如, 层次结构表中介绍了层次[](hierarchy-tables.md)结构表属性。 属于表单服务器的属性在[选择窗体的属性集](choosing-a-form-s-property-set.md)中进行描述。
  
当客户端或服务提供程序调用对象的**GetProps**方法以检索它的多个属性, 并且其中一个属性不可用时, **GetProps**将返回警告 MAPI_W_ERRORS_RETURNED。 由于返回了一些属性, 因此该调用被认为是成功的。 当客户端或服务提供程序调用**OpenProperty**且 target 属性不可用时, 该方法将失败, 并出现错误 MAPI_E_NOT_FOUND。 在尝试使用请求的属性之前, 务必先检查该属性是否返回。 
  
根据对象、提供实现的服务提供程序和属性, 属性可以具有读/写权限或只读权限。 读/写权限允许客户端或服务提供程序使用属性更改其值;只读权限仅允许拥有该对象的服务提供程序进行更改。 
  
若要准确了解当前为对象设置的属性, 请调用[IMAPIProp:: GetPropList](imapiprop-getproplist.md)。 使用**GetPropList**方法, 调用方可以找出在尝试打开可能不存在的属性之前可用的内容。 由于不存在特定类型的所有对象都支持的标准属性集, 因此无法猜测对象是否支持特定属性。 调用**GetPropList**可消除猜测工作。 
  
## <a name="see-also"></a>另请参阅



[MAPI 对象和属性](mapi-objects-and-properties.md)

