---
title: MAPI 属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e5b23f-1bdb-4fbf-a27d-e3301a359573
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ed11677d09ae5acacced77373b2bca783d1ec0b7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776301"
---
# <a name="mapi-property-overview"></a>MAPI 属性概述

  
  
**适用于**： Outlook 
  
属性是 MAPI 对象的属性。 属性描述有关该对象，例如邮件或消息的用户的地址类型的主题行。 MAPI 定义多个属性，某些来描述许多对象和一些仅适合特定类型的对象。 客户端和服务提供商可以通过创建新的自定义属性扩展 MAPI 的一组预定义属性。 客户端可以定义属性来描述新的邮件类，并且服务提供商可以定义属性来公开其邮件系统的独特功能。
  
属性可以是永久或临时。 可以存储保留会话中的属性，其对象的数据或配置文件中。 仅用于当前会话期间存在的临时属性。 
  
客户端和服务提供商可以显示为具有表或属性表的用户的属性。 表为用户提供某些属于多个对象的属性的只读的视图。 数据表示对象和属性的每个列的每个行显示行和列格式。 属性表是选项卡式显示相关的单个对象的属性对话框。 属性表可以提供只读或读/写访问数据。 允许用户更改由属性表的实施者。
  
[IMAPIProp](imapipropiunknown.md)接口是用于处理属性的主接口。 支持属性的所有对象都实现**IMAPIProp**。 **IMAPIProp**包括方法用于检索属性值将复制属性、 更改和保存这些更改，属性名称和它们的标识符，之间的映射和检索以前错误的信息。 
  
有几种数据结构，用于描述属性和属性的信息。 最常用的结构是[SPropValue](spropvalue.md)结构和[SPropTagArray](sproptagarray.md)结构。 **SPropValue**结构包含描述属性信息的三个部分： 
  
- 数据或属性的值。
    
- 该属性的值，如整数或 Boolean 数据类型。 
    
- 唯一标识的属性和组件负责维护其特定范围内的数值。 例如，没有保留内容定义 MAPI，另一个范围用来存储内容的邮件属性的属性由用于自定义邮件类别的客户端消息的区域。 
    
属性类型和标识符合并到单个组件调用属性标记中。 属性标记都是可用于轻松引用的属性的常量。 定义的 MAPI 属性的属性标记包含在 MAPITAGS。H 头文件和**SPropValue**结构的**ulPropTag**成员。 客户端和服务提供商使用属性标记标识、 检索和更新的相应属性。 
  
**SPropTagArray**结构是属性标记的计数的阵列。 用于描述属性使用**SPropTagArray**结构许多**IMAPIProp**和其他接口中的方法。 
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

