---
title: SkipBlock 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 2499587b-2a0e-4987-9bf7-591bef41b894
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 5a3367a15374234658fd9d10f3c2a5f3a191c80e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282668"
---
# <a name="skipblock-stream-structure"></a>SkipBlock 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
SkipBlock 流结构是一种以整数开头的数据块, 用于指定块的剩余部分的长度。 如果字段定义为 PropDefV2 格式, 则[FieldDefinition](fielddefinition-stream-structure.md)流中存在此流结构。 
  
SkipBlock 流结构的用途取决于其在 FieldDefinition 流的 SkipBlocks 数据元素中的一系列类似结构中的相对位置。 SkipBlocks 系列应包含至少一个 SkipBlock 结构, 该结构将终止系列并使 Size 数据元素等于0。 如果第一个结构不是终止结构 (即, Size 数据元素大于 0), Outlook 将假定第一个结构以 Unicode (UTF-16) 指定字段名称。
  
此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序依次后续。
  
- 大小: DWORD (4 个字节), 内容数据元素的大小 (以字节数表示)。
    
- 内容: 字节数组。 此数组的计数等于大小数据元素。 内容数据元素的意义取决于 SkipBlock 结构在系列中的位置和 Outlook 的版本。 如果第一个 SkipBlock 结构不是终止结构, Outlook 会将第一个 SkipBlock 结构视为用 Unicode 指定字段名称的[FirstSkipBlockContent](firstskipblockcontent-stream-structure.md)流结构。 
    
## <a name="see-also"></a>另请参阅



[Outlook 项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)
  
[FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)

