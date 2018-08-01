---
title: PackedAnsiString 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ada86f04-e81b-4f97-b9c1-1c8ec5e1a5dd
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5494558db65e19891848264c170ba85a55c5df71
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776576"
---
# <a name="packedansistring-stream-structure"></a>PackedAnsiString 流结构

  
  
**适用于**： Outlook 
  
PackedAnsiString 流结构包含 ANSI 字符串表示形式，根据在其上运行 Microsoft Outlook 的计算机的 ANSI 代码页。 未通过空字符终止此字符串。 此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面列出的顺序。 存在的实际数据元素取决于 ANSI 表示中字符串的长度。
  
- 一个字符串，其 ANSI 表示包含不超过 255 个字节，数据要素如下所示：
    
  - 时长： 字节 （1 个字节），ANSI 字符串表示形式的长度，以字节为单位数。
    
  - 字符数： CHAR 的数组。 此数组的计数等于长度数据元素。 数组中的数据是 ANSI 字符串表示形式。
    
- 一个字符串，其 ANSI 表示包含 255 到 65535 字节，数据要素如下所示：
    
  - 前缀： 字节 （1 个字节），255 之间的值 (0xff)。
    
  - 时长： 单词 （2 个字节），ANSI 字符串表示形式的长度，以字节为单位数。
    
  - 字符数： CHAR 的数组。 此数组的计数等于长度数据元素。 数组中的数据是 ANSI 字符串表示形式。
    
## <a name="see-also"></a>另请参阅



[Outlook 项和字段](outlook-items-and-fields.md)
  
[流结构](stream-structures.md)
  
[FieldDefinition 流结构](fielddefinition-stream-structure.md)

