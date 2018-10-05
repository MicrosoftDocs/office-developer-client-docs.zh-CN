---
title: 属性名称和属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cb216f5c-c965-4372-a15b-82090a410266
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa9d6afcaf1b360f37e8c8873c9d1a823fcd4888
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391652"
---
# <a name="property-names-and-property-sets"></a>属性名称和属性集

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个命名属性的名称具有两个部分：
  
- 全局唯一标识符或用于指定属性集 GUID。
    
- Unicode 字符串或 32 位数字值。 
    
介绍了使用[MAPINAMEID](mapinameid.md)结构的命名属性的名称。 此结构包含属性集成员、 数字或字符串的格式，指定名称的成员和确定使用哪种格式的成员。 由于属性集的属性名称的一部分，它不是可选。 MAPI 定义了供客户端和服务提供商使用的多个属性集，但如果不合适现有属性集，可以定义一组新属性。 客户端和服务提供商可以通过调用[CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx)函数来定义自己的属性集。 通常这些属性集创建自定义客户端应用程序。 
  
MAPI 的属性集由以下常量表示：
  
PS_MAPI
  
PS_PUBLIC_STRINGS
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_SEARCH_KEY
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
专门 PS_MAPI 属性集;服务提供商使用它可生成与范围的命名的属性的标识符的属性的名称。 客户端使用 PS_PUBLIC_STRINGS 属性集 IPM 消息的命名属性。 因为命名 PS_PUBLIC_STRINGS 设置的属性中的属性显示在客户端的用户界面中，不可见的消息如那些属于 IPC 邮件类应避免创建名为该属性设置的属性。 相反，他们应在邮件类特定区域中，通过 0x7FFF 0x6800 创建属性。
  
其他属性集保留描述通常路由列表中的成员的收件人的命名的属性。 包含相同类型的收件人列表属性与关联的属性的信息，这些属性集的属性可理解的网关需要映射的邮件系统的目标。 有五种类型的描述属性的信息，因为 MAPI 定义了五个不同的属性集。 客户端发送一条消息，必须包括地址和地址类型为其路由列表成员分配一个 PS_ROUTING_EMAIL_ADDRESSES 中每个成员的命名的属性和 PS_ROUTING_ADDRTYPE 属性设置。 这样可以确保地址和地址类型保持可行时发送给外部邮件系统。
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

