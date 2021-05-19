---
title: 定义新的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a2325ea-ddfa-480f-b65f-f5b20471fb40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 666ee413319765e39e25d586208f764afc93ae6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425013"
---
# <a name="defining-new-mapi-properties"></a>定义新的 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
尽管 MAPI 提供了大量供客户端和服务提供商使用的属性，但 MAPI 仍支持在必要时新建属性。 定义新的公共属性的一些有效方案包括客户端创建属性以支持新邮件类，以及服务提供商创建新属性来公开唯一的邮件系统功能。
  
服务提供商通常无效为现有 MAPI 对象或邮件类定义新属性。 使用 MAPI 的主要好处之一是设置大量邮件系统元素的标准标识符和格式，使用户能够无缝混合和匹配服务提供商。 使用非标准属性的服务提供商不能很好地与其他服务提供商一起工作。 
  
客户端可以通过：为新邮件类创建内容属性：
  
- 在指定范围内对特定于邮件类的内容属性使用属性标识符。
    
    - 或 -
    
- 使用命名属性。 
    
首选第一个选项，因为并非所有服务提供商都支持命名属性。 MAPI 为客户端定义两个单独的范围以用于新的特定于邮件类的内容属性：
  
- 0x6800可0x7BFF属性的自定义属性
    
- 0x7C00 0x7FFF属性的自定义设置
    
属性标识符必须属于预定义的范围，以帮助防止由不同供应商或用户定义的属性之间发生冲突。 但是，这些范围中的属性用户不能对属性的行为做出假设。 每个创建新邮件类的客户端都有权访问这些范围;标识符为  _xxxx_ 的属性可以表示一个邮件类的一个行为，另一个邮件类的另一个行为。 
  
命名属性用于保证特定属性对于邮件类是唯一的。 命名属性标识符从0x8000开始。 客户端定义一个或多个名称，然后调用消息存储的 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法以将标识符与每个名称关联。 只有在对象的所有者支持命名属性时，客户端或服务提供商才能使用命名属性定义任何对象的新属性。 这些属性的用户调用 **GetIDsFromNames** 和相关 **IMAPIProp** 方法 [GetNamesFromIDs，](imapiprop-getnamesfromids.md)以在名称及其标识符之间映射。
  
所有属性（新属性或现有属性）都必须使用预定义属性类型集。 无法添加新属性类型，并且无法修改或删除现有类型。 简单的小属性（如单字符或 16 位整数属性）可以存储在任何适当的类型中。 例如，整数可以存储为 **ULONG，** 字符串可以存储 **为PT_STRING8。** 
  
使用 **PT_BINARY** 类型指示计数的字节数组。 此属性类型对于扩展可存储在对象中的数据类型非常有用。 字节按顺序传输，并且未对数据的含义做出任何假设。 当客户端应用程序从此类属性中读取数据时，数据与数据的存储方法保持不变。 在 CPU 之间移动数据时，客户端必须执行任何必要的字节交换。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

