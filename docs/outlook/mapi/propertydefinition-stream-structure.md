---
title: PropertyDefinition 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: ab677a06-6d7d-47e7-99ea-535b0b24389a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 479339762867aa778bc8bc8baa1f21f6bc34b441
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328481"
---
# <a name="propertydefinition-stream-structure"></a>PropertyDefinition 流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
PropertyDefinition 流结构是[FieldDefinition](fielddefinition-stream-structure.md)流结构的数组, 其中包含 Microsoft Outlook 项目中所有用户定义的字段的定义, 以及某些内置字段的数据绑定设置。 
  
您可以以编程方式操作 PropertyDefinition 流结构。 但是, 您可以使用 Outlook 窗体设计器来获得类似的结果, 并在数据绑定控件的 "**属性**" 对话框中进行查找。 
  
PropertyDefinition 流结构中的字段定义可以是以下两种格式之一: PropDefV1 和 PropDefV2。 Outlook 同时支持 PropDefV1 和 PropDefV2。 一个 PropertyDefinition 流结构中的所有字段定义的格式必须相同。 有关 PropDefV1 和 PropDefV2 的不同之处的详细信息, 请参阅[FieldDefinition Stream Structure](fielddefinition-stream-structure.md)。
  
此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序依次后续。
  
- 版本: WORD (2 个字节), PropertyDefinition 流结构中的字段定义的格式。 下表显示可能的值。
    
    |**Value**|**说明**|
    |:-----|:-----|
    |0x0102  <br/> |格式为 PropDefV1。  <br/> |
    |0x0103  <br/> |格式为 PropDefV2。  <br/> |
   
- FieldDefinitionCount: DWORD (4 个字节), 此流中的字段定义数。 这是 FieldDefinitions 数据元素中数组元素的计数。
    
- FieldDefinitions: FieldDefinition 流结构的数组。 此数组的计数等于 FieldDefinitionCount 数据元素。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项目和字段](outlook-items-and-fields.md)
- [为新的用户定义的字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
- [PropertyDefinition 流示例](propertydefinition-stream-sample.md)
- [流结构](stream-structures.md)

