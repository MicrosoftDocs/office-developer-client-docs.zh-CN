---
title: PackedAnsiString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ada86f04-e81b-4f97-b9c1-1c8ec5e1a5dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3e48e57deba5c274982eeb515d27f203ec5ac7fc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348508"
---
# <a name="packedansistring-stream-structure"></a>PackedAnsiString 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
PackedAnsiString 流结构包含字符串的 ansi 表示形式, 它基于运行 Microsoft Outlook 的计算机的 ansi 代码页。 此字符串不是由 null 字符终止的。 此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面列出的顺序后续。 现有的实际数据元素取决于 ANSI 表示形式的字符串的长度。
  
- 对于 ANSI 表示形式包含小于255个字节的字符串, 数据元素如下所示:
    
  - length: BYTE (1 个字节), 字符串的 ANSI 表示形式的长度 (以字节为单位)。
    
  - 字符: 字符数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 ANSI 表示形式。
    
- 对于 ANSI 表示形式包含255到65535字节的字符串, 数据元素如下所示:
    
  - Prefix: BYTE (1 个字节), 值为 255 (0xff)。
    
  - length: WORD (2 个字节), 字符串的 ANSI 表示形式的长度 (以字节为单位)。
    
  - 字符: 字符数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 ANSI 表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook 项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

