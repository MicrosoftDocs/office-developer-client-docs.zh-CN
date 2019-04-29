---
title: PropertyDefinition 流示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 7919f4d7-04df-4a96-a5b1-b7b460890486
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 63a8141221c0ff7a8c6ffee20587b682386f87b5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406659"
---
# <a name="propertydefinition-stream-sample"></a>PropertyDefinition 流示例

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题介绍 PropertyDefinition 流的示例。 流包含用户定义的字段的定义`TextField1`。 类型为**Text**, 定义为 PropDefV2 格式。
  
## <a name="data-dump"></a>数据转储

以下是流的数据转储, 因为它将显示在二进制编辑器中。
  
|流偏移量|数据字节|ASCII 数据|
|:-----|:-----|:-----|
| `0000000000` <br/> | `03 01 01 00 00 00 45 00 00 00 08 00 00 00 00 00` <br/> | `???...E...?.....` <br/> |
| `0000000010` <br/> | `0A 00 54 00 65 00 78 00 74 00 46 00 69 00 65 00` <br/> | `?.T.e.x.t.F.i.e.` <br/> |
| `0000000020` <br/> | `6C 00 64 00 31 00 0A 54 65 78 74 46 69 65 6C 64` <br/> | `l.d.1.?TextField` <br/> |
| `0000000030` <br/> | `31 00 00 00 00 00 00 00 00 15 00 00 00 0A 54 00` <br/> | `1........?...?T.` <br/> |
| `0000000040` <br/> | `65 00 78 00 74 00 46 00 69 00 65 00 6C 00 64 00` <br/> | `e.x.t.F.i.e.l.d.` <br/> |
| `0000000050` <br/> | `31 00 00 00 00 00` <br/> | `1.....` <br/> |
   
以下是对 PropertyDefinition 流的示例数据的分析:
  
- Version: Offset 0x0, 2 个字节: 0x0103 (PropDefV2)。
    
- FieldDefinitionCount: 偏移 0x2, 4 个字节: 0x1 (1)。
    
- FieldDefinitions: 偏移量 0x6, 1 FieldDefinition stream。
    
  - Flags: Offset 0x6, 4 个字节: 0x45 (PDO_IS_CUSTOM |PDO_PRINT_SAVEAS |PDO_PRINT_SAVEAS_DEF)。
    
  - VT: 偏移量 0xA, 2 个字节: 0x8 (**VT_BSTR**)。
    
  - DispId: 偏移量 0xC, 4 个字节: 0x0 (0)。
    
  - NmidNameLength: Offset 0x10, 2 个字节: 0xA (10)。
    
  - NmidName: 偏移量 0x12, 10 WCHARs 数组。 Unicode 字符串值: "TextField1"。
    
  - NameANSI: 偏移量 0x26, PackedAnsiString stream。
    
    - Length: 偏移量 0x26, 1 个字节: 0xA (10)。
      
    - 字符: 偏移 0x27, 数组为10个字符。 ANSI 字符串值: "TextField1"。
    
  - FormulaANSI: 偏移量 0x31, PackedAnsiString stream。
    
    - Length: 偏移量 0x31, 1 个字节: 0x0 (0)。
      
    - 字符: 偏移量 0x32, 0 个字符数组。 空 ANSI 字符串。
    
  - ValidationRuleANSI: 偏移量 0x32, PackedAnsiString stream。
    
    - Length: 偏移量 0x32, 1 个字节: 0x0 (0)。
      
    - 字符: 偏移量 0x33, 0 个字符数组。 空 ANSI 字符串。
    
  - ValidationTextANSI: 偏移量 0x33, PackedAnsiString stream。
    
    - Length: 偏移量 0x33, 1 个字节: 0x0 (0)。
      
    - 字符: 偏移量 0x34, 0 个字符数组。 空 ANSI 字符串。
    
  - ErrorANSI: 偏移量 0x34, PackedAnsiString stream。
    
    - Length: 偏移量 0x34, 1 个字节: 0x0 (0)。
      
    - 字符: 偏移量 0x35, 0 个字符数组。 空 ANSI 字符串。
    
  - InternalType: 偏移量 0x35, 4 个字节: 0x0 (iTypeString)。
    
  - SkipBlocks: 偏移量 0x39, 系列的 SkipBlock 流。
    
  - 第一个 SkipBlock
    
    - 大小: 偏移 0x39, 4 个字节: 0x15 (21)。
      
    - 内容: 偏移 0x3D, 数组为21字节。 这是第一个 SkipBlock 流, 因此此数组包含一个 FirstSkipBlockContent 流。
      
      - FieldName: Offset 0x3D, PackedUnicodeString stream。
        
        - Length: 偏移量 0x3D, 1 个字节: 0xA (10)。
          
        - 字符: 偏移 0x3E, 数组为 10 WCHARs。 Unicode 字符串值: "TextField1"。
    
  - 第二个 SkipBlock
    
    - 大小: 偏移 0x52, 4 个字节: 0x0 (0)。 这是终止的 SkipBlock 流。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项目和字段](outlook-items-and-fields.md)
- [流结构](stream-structures.md)
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)
- [FieldDefinition 流结构](fielddefinition-stream-structure.md)
- [SkipBlock 流结构](skipblock-stream-structure.md)
- [FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
- [PackedAnsiString 流结构](packedansistring-stream-structure.md)
- [PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)

