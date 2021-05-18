---
title: PackedAnsiString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ada86f04-e81b-4f97-b9c1-1c8ec5e1a5dd
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3e48e57deba5c274982eeb515d27f203ec5ac7fc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404503"
---
# <a name="packedansistring-stream-structure"></a>PackedAnsiString 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
PackedAnsiString 流结构包含字符串的 ANSI 表示形式，该字符串基于运行 Microsoft Outlook 的计算机的 ANSI 代码页。 此字符串不以空字符结尾。 此流中的数据元素按小尾字节顺序存储，并按下面列出的顺序彼此紧接。 实际存在的数据元素取决于 ANSI 表示形式中的字符串长度。
  
- 对于 ANSI 表示形式包含小于 255 字节的字符串，数据元素如下所示：
    
  - 长度：BYTE (1 字节) ，字符串的 ANSI 表示形式的长度（以字节数为单位）。
    
  - 字符：CHAR 的数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 ANSI 表示形式。
    
- 对于 ANSI 表示形式包含 255 到 65535 字节的字符串，数据元素如下所示：
    
  - 前缀：BYTE (1 字节) ，值 255 (0xff) 。
    
  - 长度：WORD (2 字节) ，字符串的 ANSI 表示形式的长度（以字节数为单位）。
    
  - 字符：CHAR 的数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 ANSI 表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

