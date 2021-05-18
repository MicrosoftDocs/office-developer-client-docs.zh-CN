---
title: 属性名称和属性集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cb216f5c-c965-4372-a15b-82090a410266
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa9d6afcaf1b360f37e8c8873c9d1a823fcd4888
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328544"
---
# <a name="property-names-and-property-sets"></a>属性名称和属性集

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
每个命名属性的名称都有两个部分：
  
- 用于指定属性集的全局唯一标识符或 GUID。
    
- Unicode 字符字符串或 32 位数值。 
    
命名属性的名称使用 [MAPINAMEID](mapinameid.md) 结构进行描述。 此结构包含一个属性集成员、一个以数字或字符串格式指定名称的成员，以及一个用来标识使用哪种格式的成员。 由于属性集是属性名称的一部分，因此不是可选的。 MAPI 定义了多个供客户端和服务提供商使用的属性集，但如果现有的属性集不合适，可以定义新的属性集。 客户端和服务提供商可以通过调用 [CoCreateGUID](https://msdn.microsoft.com/library/ms688568.aspx) 函数定义自己的属性集。 通常，为自定义客户端应用程序创建这些属性集。 
  
MAPI 的属性集由以下常量表示：
  
PS_MAPI
  
PS_PUBLIC_STRINGS
  
PS_ROUTING_EMAIL_ADDRESSES
  
PS_ROUTING_ADDRTYPE
  
PS_ROUTING_SEARCH_KEY
  
PS_ROUTING_DISPLAY_NAME
  
PS_ROUTING_ENTRYID
  
保留PS_MAPI属性集;服务提供商使用此属性为标识符低于命名属性范围的属性生成名称。 客户端PS_PUBLIC_STRINGS IPM 邮件的命名属性使用属性集。 由于 PS_PUBLIC_STRINGS 属性集的命名属性显示在客户端的用户界面中，因此属于 IPC 邮件类的不可访问邮件（如那些属于 IPC 邮件类的邮件）应避免使用此属性集创建命名属性。 相反，它们应在特定于邮件类的范围（从 0x6800 到 0x7FFF）内创建属性。
  
其他属性设置用于描述通常是路由列表成员的收件人的命名属性。 包含的信息类型与与收件人列表属性关联的属性相同，网关理解这些属性集内的属性，以要求映射目标邮件系统。 由于有五种类型的信息用于描述属性，MAPI 定义了五种不同的属性集。 发送必须为其路由列表成员包含地址和地址类型的邮件的客户端会为 PS_ROUTING_EMAIL_ADDRESSES 和 PS_ROUTING_ADDRTYPE 属性集的每个成员分配命名属性。 这可确保地址和地址类型在发送到外消息系统时保持可行。
  
## <a name="see-also"></a>另请参阅



[MAPI 命名属性](mapi-named-properties.md)

