---
title: 属性定义流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: ab677a06-6d7d-47e7-99ea-535b0b24389a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 289227ee171c2325cad0ed321dab4f635a0ca724
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778582"
---
# <a name="propertydefinition-stream-structure"></a>属性定义流结构

**适用于**： Outlook 
  
属性定义流结构是包含在 Microsoft Outlook 项目中，所有用户定义的字段定义和一些内置字段的数据绑定设置[FieldDefinition](fielddefinition-stream-structure.md)流结构的数组。 
  
您可以编程方式处理属性定义流结构。 但是，您可以通过使用 Outlook 窗体设计器来实现类似的结果，并且**属性**对话框，尤其是数据绑定控件框。 
  
在属性定义流结构中的字段定义可为以下两种格式之一： PropDefV1 和 PropDefV2。 Outlook 支持 PropDefV1 和 PropDefV2。 在单个属性定义流结构中的所有字段定义都必须属于相同的格式。 有关如何 PropDefV1 和 PropDefV2 不同的详细信息，请参阅[FieldDefinition 流结构](fielddefinition-stream-structure.md)。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面指定的顺序。
  
- 版本： WORD （2 个字节） 属性定义中的字段定义的格式 stream 结构。 下表显示可能的值。
    
    |**值**|**说明**|
    |:-----|:-----|
    |0x0102  <br/> |格式为 PropDefV1。  <br/> |
    |0x0103  <br/> |格式为 PropDefV2。  <br/> |
   
- FieldDefinitionCount: DWORD （4 个字节），此流中的字段定义的数目。 这是 FieldDefinitions data 元素中的数组元素的计数。
    
- FieldDefinitions: FieldDefinition 流结构的数组。 此数组的计数等于 FieldDefinitionCount 数据元素。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项和字段](outlook-items-and-fields.md)
- [为新的用户定义字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
- [PropertyDefinition 流示例](propertydefinition-stream-sample.md)
- [流结构](stream-structures.md)

