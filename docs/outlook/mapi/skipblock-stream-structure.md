---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a3367a15374234658fd9d10f3c2a5f3a191c80e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435542"
---
# <a name="skipblock-stream-structure"></a>SkipBlock 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
SkipBlock 流结构是一个以整数开头的数据块，该整数指定块的剩余部分的长度。 如果字段定义采用 PropDefV2 格式，则此流结构存在于 [FieldDefinition](fielddefinition-stream-structure.md) 流中。 
  
SkipBlock 流结构的用途取决于其在 FieldDefinition 流的 SkipBlocks 数据元素中的一系列类似结构中的相对位置。 SkipBlocks 系列应至少包含一个终止系列的 SkipBlock 结构，并且 Size 数据元素等于 0。 如果第一个结构不是终止结构 (即 Size 数据元素大于 0) ，则 Outlook 假定第一个结构在 Unicode (UTF-16) 中指定字段名称。
  
此流中的数据元素以小尾序字节顺序存储，并按下面指定的顺序彼此紧接。
  
- 大小：DWORD (4 字节) ，内容数据元素的大小（以字节数为单位）。
    
- 内容：BYTE 数组。 此数组的计数等于 Size 数据元素。 Content 数据元素的含义取决于 SkipBlock 结构在系列中的位置以及 Outlook。 如果第一个 SkipBlock 结构不是终止结构，Outlook将第一个 SkipBlock 结构视为在 Unicode 中指定字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构。 
    
## <a name="see-also"></a>另请参阅



[Outlook项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)

