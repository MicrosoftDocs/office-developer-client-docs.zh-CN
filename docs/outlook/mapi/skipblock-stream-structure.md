---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d84704300602bada4cf93c9d3f6622feaf16f352
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778808"
---
# <a name="skipblock-stream-structure"></a>SkipBlock 流结构

  
  
**适用于**： Outlook 
  
SkipBlock 流结构是开头一个整数，指定的块的剩余部分的长度的数据块。 如果字段定义为 PropDefV2 格式，该流结构存在于[FieldDefinition](fielddefinition-stream-structure.md) stream 中。 
  
SkipBlock 流结构的目的取决于其在一系列类似的 FieldDefinition 流 SkipBlocks data 元素中的结构中的相对位置。 SkipBlocks 系列应包含至少一个 SkipBlock 结构终止系列且具有等于 0 的大小数据元素。 如果第一个结构中不是终止结构 （即，大小数据元素是大于 0），Outlook 假定的第一个结构 Unicode (utf-16) 中指定的字段名称。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面指定的顺序。
  
- 规模： DWORD （4 个字节） 的大小，以字节为单位的内容数据元素的数量。
    
- 内容： BYTE 的数组。 此数组的计数等于大小数据元素。 内容数据元素的含义取决于 SkipBlock 结构系列中的位置和 Outlook 版本。 如果第一个 SkipBlock 结构不终止的结构，Outlook 就会将视为 Unicode 中指定的字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构的第一个 SkipBlock 结构。 
    
## <a name="see-also"></a>另请参阅



[Outlook 项和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)

