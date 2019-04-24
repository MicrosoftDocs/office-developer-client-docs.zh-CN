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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336678"
---
# <a name="defining-new-mapi-properties"></a>定义新的 MAPI 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
尽管 mapi 提供的用于客户端和服务提供商的大量属性, MAPI 也支持在必要时创建新属性。 用于定义新的公共属性的一些有效方案包括客户端创建属性, 以支持新邮件类和服务提供程序创建新的属性以公开唯一的邮件系统功能。
  
服务提供商对现有 MAPI 对象或邮件类别定义新属性的方法通常无效。 使用 MAPI 的主要好处之一是, 设置了大量邮件系统元素的标准标识符和格式, 使用户能够无缝混合和匹配服务提供程序。 使用非标准属性的服务提供程序不能和其他服务提供商一起使用。 
  
客户端可以通过以下方式创建新邮件类别的内容属性:
  
- 在指定范围内为邮件类别特定的内容属性使用属性标识符。
    
    - 和
    
- 使用命名属性。 
    
第一种方法是首选方法, 因为并非所有服务提供程序都支持命名属性。 MAPI 为客户端定义了两个单独的范围, 以供客户端用于新邮件类别特定的内容属性:
  
- 0x6800 to 0x7BFF for 传输属性
    
- 0x7C00 to 0x7FFF for nontransmittable 属性
    
属性标识符必须位于预定义的范围内, 以帮助防止由不同供应商或用户定义的属性之间发生冲突。 但是, 这些区域中的属性的用户无法假定属性行为。 创建新邮件类的每个客户端都有权访问这些区域;带有标识符_xxxx_的属性可表示一个邮件类别的一个行为和另一个邮件类别的另一个行为。 
  
命名属性用于保证特定属性对邮件类是唯一的。 命名属性标识符以0x8000 范围开始。 客户端定义一个或多个名称, 然后调用邮件存储区的[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法将标识符与每个名称相关联。 只有当对象的所有者支持命名属性时, 客户端或服务提供程序才能使用命名属性为任何对象定义新属性。 这些属性的用户调用**GetIDsFromNames**和相关的**IMAPIProp**方法[GetNamesFromIDs](imapiprop-getnamesfromids.md), 以在名称和其标识符之间进行映射。
  
所有属性 (新的或现有的) 都必须使用预定义的属性类型集。 无法添加新的属性类型, 并且无法修改或删除现有类型。 简单、较小的属性 (例如单字符或16位整数属性) 可以存储在任何适当的类型中。 例如, 可以将整数存储为**ULONG** , 并且可以将字符串存储为**PT_STRING8**。 
  
使用**PT_BINARY**类型指示计数的字节数组。 此属性类型对扩展可存储在对象中的数据类型很有用。 字节按顺序传输, 并且不会对数据的含义进行假设。 当客户端应用程序从这种属性中读取数据时, 数据不会因存储的方式而改变。 当跨 cpu 移动数据时, 客户端必须执行任何必要的字节交换。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

