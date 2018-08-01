---
title: 添加新用户定义的字段的定义
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 183d3b86-4506-44da-bbfc-d6242ad89e57
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 26c329323eebff6cfdf4f4be4dffe9a62f8745e6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775080"
---
# <a name="add-a-definition-for-a-new-user-defined-field"></a>添加新用户定义的字段的定义
 
**适用于**： Outlook 
  
当您向 Microsoft Outlook 项目中添加用户定义的字段时，您将字段定义添加到相应[属性定义](propertydefinition-stream-structure.md)流结构。 使用以下过程将一个新的字段定义添加到属性定义流结构。 
  
### <a name="to-add-a-definition-for-a-new-user-defined-field"></a>若要添加新用户定义的字段的定义

1. 将现有的字段定义的属性定义流结构复制到新的字段定义数组。 
    
2. 如果任何现有的字段定义 PropDefV1 格式，则将其转换为 PropDefV2 格式。 有关字段定义格式的详细信息，请参阅[属性定义流结构](propertydefinition-stream-structure.md)和[FieldDefinition 流结构](fielddefinition-stream-structure.md)。
    
3. 创建新用户定义的字段的定义 PropDefV2 格式并将其添加到数组。
    
4. 如果尚未设置的 Version 元素的值，请将属性定义流结构的 Version 元素设置为 0x0103。
    
5. 递增 1 FieldDefinitionCount 元素。
    
6. 存储为 FieldDefinitions 元素的值的数组。
    
## <a name="see-also"></a>另请参阅

- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)

