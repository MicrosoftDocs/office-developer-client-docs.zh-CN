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
  
属性是 MAPI 对象的属性。 属性描述有关对象的信息，例如邮件的主题行或邮件用户的地址类型。 MAPI 定义了许多属性，一些属性用于描述许多对象，有些属性仅适用于特定类型的对象。 客户端和服务提供商可以通过创建新的自定义属性来扩展 MAPI 的预定义属性集。 客户端可以定义属性来描述新的邮件类，而服务提供商可以定义属性来公开其邮件系统的独特功能。
  
属性可以是永久性的或临时的。 在会话和会话期间保留的属性可以与对象的数据或配置文件一起存储。 临时属性仅在当前会话期间存在。 
  
客户端和服务提供商可以向具有表或属性的用户显示属性表。 表为用户提供了属于多个对象的一些属性的只读视图。 数据以行和列格式显示，每行表示一个对象，每一列表示一个属性。 属性表是选项卡式对话框，用于显示单个对象的相关属性。 属性表可提供对数据的只读或读/写访问权限。 是否允许用户进行更改取决于项目实施者属性表。
  
[IMAPIProp](imapipropiunknown.md)接口是处理属性的主要接口。 支持属性的所有对象都实现 **IMAPIProp**。 **IMAPIProp** 包括用于检索属性值、复制属性、进行更改和保存这些更改、在属性名称及其标识符之间映射以及检索有关之前错误的信息的方法。 
  
有几个数据结构用于描述属性和有关属性的信息。 最常用的结构是 [SPropValue](spropvalue.md) 结构和 [SPropTagArray](sproptagarray.md) 结构。 **SPropValue** 结构包含描述属性的三条信息： 
  
- 属性的数据或值。
    
- 属性值的数据类型，如整数或布尔值。 
    
- 特定范围内用于唯一标识负责维护该属性和组件的数值。 例如，有一个保留 MAPI 定义的邮件内容属性的范围，还有一个保留客户端为自定义邮件类定义的邮件内容属性的范围。 
    
属性类型和标识符组合到一个称为属性标记的组件中。 属性标记是可用于轻松引用该属性的常量。 MAPITAGS 中包含 MAPI 定义的属性的属性标记。H 头文件和 **SPropValue** 结构的 **ulPropTag** 成员。 客户端和服务提供商使用属性标记来标识、检索和更新相应的属性。 
  
**SPropTagArray** 结构是属性标记的计数数组。 **IMAPIProp 和其他** 接口中的许多方法都使用 **SPropTagArray** 结构来描述属性。 
  
## <a name="see-also"></a>另请参阅



[MAPI 概念](mapi-concepts.md)

