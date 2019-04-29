---
title: Outlook 项目和字段
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 605fab0f-c045-4d2b-a2da-447a111f66a9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b40752d4a5f445368752ad4caf5c919f6e0ce27b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409116"
---
# <a name="outlook-items-and-fields"></a>Outlook 项目和字段

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 提供了专用于其功能的项目类型 (例如, 邮件项目、约会、联系人、任务和便笺)。 Outlook 为每种类型的项目 (通常称为内置域) 提供标准字段。 Outlook 还允许用户创建自定义字段, 通常称为用户定义的字段。 每个字段都与一个数据类型和一个值相关联。 数据类型的示例包括**货币**、**日期/时间**、**持续时间**、**整数**、**关键字**和**文本**。 用户可以通过使用 Outlook 中的窗体设计器来定义自定义字段。
  
在可编程性级别, 每个项目都由一个[IMessage](imessageimapiprop.md)对象表示。 每个用户定义的字段都与一个字段定义和一个值相关联。 
  
### <a name="field-definition"></a>字段定义

字段定义包括名称、数据类型和有关字段的其他信息。 对于每个项目, Outlook 将所有用户定义的字段的定义存储在相应的**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。 **PidLidPropertyDefinitionStream**属性包含一个包含字段定义的 PropertyDefinition 的二进制流 (称为 " [](propertydefinition-stream-structure.md) ")。 有关字段定义的流结构的详细信息, 请参阅[stream 结构](stream-structures.md)。
  
### <a name="field-value"></a>域值

项目的每个用户定义的字段都有一个存储在相应的命名属性中的值。 该命名属性在设置 PS_PUBLIC_STRINGS 属性中, 并将 Unicode 字符串作为属性名称。 该属性的数据类型对应于字段的类型。 如果该属性不在**IMessage**对象中, 则 Outlook 假定该属性的默认值是合理的。 例如, 对于 string 类型, 如果属性不存在, Outlook 将假定为空字符串。 
  
## <a name="see-also"></a>另请参阅



[为新的用户定义的字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition 流示例](propertydefinition-stream-sample.md)
  
[流结构](stream-structures.md)
  
[PropertyDefinition 流结构](propertydefinition-stream-structure.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[SkipBlock 流结构](skipblock-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
  
[PackedAnsiString 流结构](packedansistring-stream-structure.md)
  
[PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)

