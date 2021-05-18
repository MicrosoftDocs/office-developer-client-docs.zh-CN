---
title: PackedUnicodeString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e4cb1613-7e81-432a-ae3a-7fedb05dac65
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fc20c259f30ded2f96f3bf314e74207bebcac980
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422612"
---
# <a name="packedunicodestring-stream-structure"></a>PackedUnicodeString 流结构

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
PackedUnicodeString 流结构包含 Unicode (UTF-16) 字符串的表示形式。 此字符串不以空字符结尾。 此流中的数据元素按小尾字节顺序存储，并按下面列出的顺序彼此紧接。 实际存在的数据元素取决于 UTF-16 表示形式中的字符串长度。
  
- 对于 UTF-16 表示形式包含小于 255 个 WCHAR 的字符串，数据元素如下所示：
    
  - 长度：BYTE (1 字节) ，字符串的 UTF-16 表示形式的长度（以 WCHAR 数表示）。
    
  - 字符：WCHAR 的数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 UTF-16 表示形式。
    
- 对于 UTF-16 表示形式包含 255 到 65535 WCHAR 的字符串，数据元素如下所示：
    
  - 前缀：BYTE (1 字节) ，值 255 (0xff) 。
    
  - 长度：WORD (2 字节) ，即字符串的 UTF-16 表示形式的长度（以 WCHAR 数表示）。
    
  - 字符：WCHAR 的数组。 此数组的计数等于 Length 数据元素。 数组中的数据是字符串的 UTF-16 表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook项目和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

