---
title: PropertyDefinition 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: ab677a06-6d7d-47e7-99ea-535b0b24389a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 479339762867aa778bc8bc8baa1f21f6bc34b441
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438587"
---
# <a name="propertydefinition-stream-structure"></a>PropertyDefinition 流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
PropertyDefinition 流结构是[FieldDefinition](fielddefinition-stream-structure.md)流结构的数组，其中包含 Microsoft Outlook 项中所有用户定义字段的定义，以及某些内置字段的数据绑定设置。 
  
您可以编程方式操作 PropertyDefinition 流结构。 但是，通过使用窗体设计器，Outlook，尤其是数据绑定控件的"属性"对话框，可以实现类似的结果。  
  
PropertyDefinition 流结构中的字段定义可以是两种格式之一：PropDefV1 和 PropDefV2。 Outlook同时支持 PropDefV1 和 PropDefV2。 单个 PropertyDefinition 流结构中的所有字段定义必须具有相同的格式。 有关 PropDefV1 和 PropDefV2 如何区别的信息，请参阅 [FieldDefinition Stream Structure](fielddefinition-stream-structure.md)。
  
此流中的数据元素以小尾序字节顺序存储，并按下面指定的顺序彼此紧接。
  
- 版本：WORD (2 字节) ，PropertyDefinition 流结构中字段定义的格式。 下表显示可能的值。
    
    |**值**|**说明**|
    |:-----|:-----|
    |0x0102  <br/> |格式为 PropDefV1。  <br/> |
    |0x0103  <br/> |格式为 PropDefV2。  <br/> |
   
- FieldDefinitionCount：DWORD (4 字节) ，即此流中的字段定义数。 这是 FieldDefinitions 数据元素中的数组元素计数。
    
- FieldDefinitions：FieldDefinition 流结构的数组。 此数组的计数等于 FieldDefinitionCount 数据元素。
    
## <a name="see-also"></a>另请参阅

- [Outlook项目和字段](outlook-items-and-fields.md)
- [添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
- [PropertyDefinition Stream 示例](propertydefinition-stream-sample.md)
- [流结构](stream-structures.md)

