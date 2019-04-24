---
title: 为用户定义的新字段添加定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 183d3b86-4506-44da-bbfc-d6242ad89e57
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2879299d152d8fea7690162ae55a22f337f5fd59
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299067"
---
# <a name="add-a-definition-for-a-new-user-defined-field"></a>为用户定义的新字段添加定义
 
**适用于**：Outlook 2013 | Outlook 2016 
  
将用户定义的字段添加到 Microsoft Outlook 项时, 会将字段定义添加到相应的[PropertyDefinition](propertydefinition-stream-structure.md)流结构中。 使用以下过程可将新的字段定义添加到 PropertyDefinition 流结构中。 
  
### <a name="to-add-a-definition-for-a-new-user-defined-field"></a>为新的用户定义的字段添加定义

1. 将 PropertyDefinition 流结构的现有字段定义复制到新的字段定义数组。 
    
2. 如果任何现有字段定义的格式为 PropDefV1, 则将其转换为 PropDefV2 格式。 有关字段定义格式的详细信息, 请参阅[PropertyDefinition stream structure](propertydefinition-stream-structure.md) and [FieldDefinition stream structure](fielddefinition-stream-structure.md)。
    
3. 以 PropDefV2 格式创建新的用户定义字段的定义, 并将其添加到数组中。
    
4. 将 PropertyDefinition 流结构的 version 元素设置为 0x0103 (如果 version 元素尚未设置为该值)。
    
5. 将 FieldDefinitionCount 元素递增1。
    
6. 将数组存储为 FieldDefinitions 元素的值。
    
## <a name="see-also"></a>另请参阅

- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)

