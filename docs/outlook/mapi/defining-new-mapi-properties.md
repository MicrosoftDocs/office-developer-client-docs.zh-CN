---
title: 定义新的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1a2325ea-ddfa-480f-b65f-f5b20471fb40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f922ee95cda84311d840aa9de339883c57efba56
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590321"
---
# <a name="defining-new-mapi-properties"></a>定义新的 MAPI 属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
丰富的属性以供客户端和服务提供商提供的 MAPI，尽管 MAPI 启用要创建必要的新属性。 定义新的公共属性的有效方案的一些包括客户端创建属性以支持新的邮件类和服务提供程序创建新属性公开唯一消息系统功能。
  
通常不有效的服务提供程序定义的现有 MAPI 对象或消息类的新属性。 使用 MAPI 的主要优点之一是标准的标识符和格式的大量元素设置，使用户能够无缝混合和匹配的邮件系统的服务提供商。 使用非标准属性的服务提供商无效以及与其他服务提供商。 
  
客户端可以创建的新邮件类的内容属性：
  
- 使用邮件类特定内容属性属性指定范围内的标识符。
    
    - 或者-
    
- 使用命名的属性。 
    
最好是第一个选项，因为并非所有服务提供商都支持命名的属性。 MAPI 定义为客户端用于新的邮件类特定内容属性的两个单独的范围：
  
- 0x6800 到 0x7BFF 可传送属性
    
- 0x7C00 到 0x7FFF nontransmittable 属性
    
为了帮助防止其他供应商或用户定义的属性之间的冲突的预定义范围中必须属于属性标识符。 但是，这些范围中的属性的用户无法进行假设来对行为的属性。 创建新的邮件类的每个客户端有权访问这些范围;一个邮件类的一个行为和另一个邮件类的另一个行为，可能意味着标识符_格式_的属性。 
  
命名的属性用于保证特定属性是唯一的邮件类。 命名的属性标识符启动 0x8000 范围中。 客户端定义一个或多个名称，然后调用的消息存储[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法与每个名称相关联的标识符。 命名的属性可以由客户端或服务提供商，用于定义的任何对象的新属性，仅当对象的所有者支持命名的属性。 这些属性的用户呼叫**GetIDsFromNames**和相关的**IMAPIProp**方法， [GetNamesFromIDs](imapiprop-getnamesfromids.md)，名称和其标识符之间进行映射。
  
所有属性，新的或现有，必须都使用一的组预定义的属性类型。 无法添加新的属性类型，不能修改或删除现有的类型。 简单、 小属性，如单字符或 16 位整数属性可以存储在任何适当的类型。 例如，可以作为**ULONG**存储整数和字符串可以存储为**PT_STRING8**。 
  
使用**PT_BINARY**类型指示计数的字节数组。 此属性类型可用于扩展的可以对象中存储的数据类型。 序列中传输字节和任何假定所做的数据的含义。 当客户端应用程序读取利用这种属性的数据时，数据是从存储方式不变。 客户端必须执行任何所需的字节交换跨 Cpu 移动数据。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

