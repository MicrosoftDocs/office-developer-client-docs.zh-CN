---
title: MAPI 属性概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 02e5b23f-1bdb-4fbf-a27d-e3301a359573
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 99887bab2b576e6e6c05414ee9daf1bd6e8d0463
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408325"
---
# <a name="mapi-property-overview"></a>MAPI 属性概述

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
属性是 MAPI 对象的属性。 属性描述有关对象的内容, 如邮件的主题行或邮件用户的地址类型。 MAPI 定义了许多属性, 有些用于描述许多对象, 而有些则仅适用于特定类型的对象。 客户端和服务提供程序可以通过创建新的自定义属性来扩展 MAPI 的一组预定义属性。 客户端可以定义用于描述新邮件类的属性, 服务提供程序可以定义属性来公开其邮件系统的独特功能。
  
属性可以是永久性的, 也可以是临时的。 从 session to session 中保留的属性可以与它们的对象数据或配置文件存储在一起。 临时属性仅存在于当前会话的持续时间中。 
  
客户端和服务提供程序可以向具有表或属性表的用户显示属性。 表为用户提供了属于多个对象的某些属性的只读视图。 数据按行和列的格式显示, 每行表示一个对象, 每个列都是一个属性。 属性表是用于显示单个对象的相关属性的选项卡式对话框。 属性表可以提供对数据的只读或读/写访问权限。 是否允许用户进行更改是由属性表的实施者决定的。
  
[IMAPIProp](imapipropiunknown.md)接口是用于处理属性的主要接口。 支持属性的所有对象都实现**IMAPIProp**。 **IMAPIProp**包含用于检索属性值、复制属性、更改和保存这些更改、属性名称与其标识符之间的映射以及检索有关前一个错误的信息的方法。 
  
有几个用于描述属性的数据结构和有关属性的信息。 最常使用的结构是[SPropValue](spropvalue.md)结构和[SPropTagArray](sproptagarray.md)结构。 **SPropValue**结构包含描述属性的三部分信息: 
  
- 属性的数据或值。
    
- 属性值的数据类型, 如 integer 或 Boolean。 
    
- 特定范围内的数值, 用于唯一标识负责维护该属性和组件的值。 例如, 有一个范围来保存 MAPI 定义的邮件内容属性和另一个范围, 以保留客户端为自定义邮件类别定义的邮件内容属性。 
    
属性类型和标识符组合成一个称为属性标记的组件。 属性标记是可用于轻松引用属性的常量。 由 MAPI 定义的属性的属性标记包含在 MAPITAGS 中。H 头文件, 在**SPropValue**结构的**ulPropTag**成员中。 客户端和服务提供程序使用属性标记来标识、检索和更新相应的属性。 
  
**SPropTagArray**结构是一个计数的属性标记数组。 **IMAPIProp**和其他接口中的许多方法都使用**SPropTagArray**结构来描述属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

