---
title: 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9e305071-b6a5-4bd8-892e-25553d04bb15
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f1f1e028797edaa0afb45df4f39aca15ff6d425
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407821"
---
# <a name="stream-structures"></a>流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
Microsoft 项目的用户定义字段Outlook存储在[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。 此属性的值是一个二进制流，其中包含用户定义的字段的定义以及项目内置字段的数据绑定Outlook设置。 本节提供有关二进制流结构的信息，这些信息在下列流结构中细分。 
  
> [!NOTE]
> 这些流结构的名称 (例如 PropertyDefinition、FieldDefinition 和 SkipBlock) 及其数据元素在技术上不是消息 API (MAPI) 编程接口的一部分，并且在此处仅出于实际流结构的文档目的提供。 开发人员可以选择在应用程序中标记这些流结构和数据元素。 
  
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)
    
- [FieldDefinition 流结构](fielddefinition-stream-structure.md)
    
- [SkipBlock 流结构](skipblock-stream-structure.md)
    
- [FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
    
- [PackedAnsiString 流结构](packedansistring-stream-structure.md)
    
- [PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)
    
## <a name="see-also"></a>另请参阅



[Outlook项目和字段](outlook-items-and-fields.md)
  
[添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[PropertyDefinition Stream 示例](propertydefinition-stream-sample.md)

