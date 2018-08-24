---
title: Outlook 项和字段
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 605fab0f-c045-4d2b-a2da-447a111f66a9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: caa231842c5fd51deb80144f12fdf53e51ccc980
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22582873"
---
# <a name="outlook-items-and-fields"></a>Outlook 项和字段

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 提供了专用于他们的功能 （例如邮件项目、 约会、 联系人、 任务和 notes） 的项目类型。 Outlook 提供了每种类型的项目，通常称作内置字段的标准字段。 Outlook 还允许用户创建自定义字段，通常称作用户定义的字段。 每个字段相关联的数据类型和值。 数据类型的示例是**货币**、**日期/时间**、**持续时间**、**整数**、**关键字**和**文本**。 用户可以通过在 Outlook 中使用窗体设计器中定义自定义字段。
  
可编程性级别由[IMessage](imessageimapiprop.md)对象表示每个项目。 用户定义的每个字段相关联的字段定义和值。 
  
### <a name="field-definition"></a>字段定义

字段定义包括名称、 数据类型和字段的其他信息。 对于每个项，Outlook 相应**IMessage**对象的[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中存储所有用户定义的字段的定义。 **PidLidPropertyDefinitionStream**属性将包含二进制流称为[属性定义](propertydefinition-stream-structure.md)包含的字段定义。 有关字段定义流结构的详细信息，请参阅[流结构](stream-structures.md)。
  
### <a name="field-value"></a>域值

项目的每个用户定义的字段有一个相应的命名属性中存储的值。 命名属性位于 PS_PUBLIC_STRINGS 属性集，并具有与属性名称 Unicode 字符串。 属性的数据类型对应于字段类型。 如果该属性不存在**IMessage**对象中，Outlook 将假定属性的合理的默认值。 例如，string 类型，Outlook 假定为空字符串如果属性不存在。 
  
## <a name="see-also"></a>另请参阅



[为新的用户定义字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition 流示例](propertydefinition-stream-sample.md)
  
[流结构](stream-structures.md)
  
[PropertyDefinition 流结构](propertydefinition-stream-structure.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[SkipBlock 流结构](skipblock-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
  
[PackedAnsiString 流结构](packedansistring-stream-structure.md)
  
[PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)

