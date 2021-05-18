---
title: Outlook项目和字段
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
# <a name="outlook-items-and-fields"></a>Outlook项目和字段

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft Outlook 提供了专门用于其功能的项目类型 (例如，邮件项目、约会、联系人、任务和注释) 。 Outlook为每种项目类型提供标准字段，通常称为内置字段。 Outlook还允许用户创建自定义字段，通常称为用户定义的字段。 每个字段都与一个数据类型和一个值关联。 数据类型的示例包括 Currency、Date/Time、Duration、Integer、Keywords 和 **Text。**      用户可以通过使用窗体设计器定义自定义Outlook。
  
在可编程性级别，每个项目都由 [IMessage 对象](imessageimapiprop.md) 表示。 每个用户定义的字段都与字段定义和值相关联。 
  
### <a name="field-definition"></a>字段定义

字段定义包括名称、数据类型和其他有关字段的信息。 对于每个项，Outlook定义字段的定义存储在相应 **IMessage** 对象的 [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。 **PidLidPropertyDefinitionStream** 属性包含一个称为 [PropertyDefinition](propertydefinition-stream-structure.md)的二进制流，其中包含字段定义。 有关字段定义的流结构详细信息，请参阅 [Stream Structures](stream-structures.md)。
  
### <a name="field-value"></a>域值

项目的每个用户定义的字段都有一个值，该值存储在相应的命名属性中。 该命名属性位于PS_PUBLIC_STRINGS集内，并且具有一个 Unicode 字符串作为属性名称。 属性数据类型对应于字段的类型。 如果 **IMessage** 对象中不存在该属性，则Outlook假定属性的默认值合理。 例如，对于字符串类型，Outlook属性不存在时假定为空字符串。 
  
## <a name="see-also"></a>另请参阅



[添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition Stream 示例](propertydefinition-stream-sample.md)
  
[流结构](stream-structures.md)
  
[PropertyDefinition 流结构](propertydefinition-stream-structure.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[SkipBlock 流结构](skipblock-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
  
[PackedAnsiString 流结构](packedansistring-stream-structure.md)
  
[PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)

