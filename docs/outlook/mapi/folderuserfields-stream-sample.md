---
title: FolderUserFields 流示例
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 30e5e887-a324-4ed2-ba2a-eb4c19ba38d2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 76ad693b05e3989bd64ba66565ae4def22110ad0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564897"
---
# <a name="folderuserfields-stream-sample"></a>FolderUserFields 流示例

**适用于**： Outlook 2013 |Outlook 2016 
  
本主题介绍 FolderUserFields 流的示例。 流包含用户定义的字段的定义`TextField1`。 类型为**文本**，并 FolderUserFields 流包含 FolderUserFieldsAnsi 和 FolderUserFieldsUnicode 部件。 有关详细信息，请参阅[文件夹字段流结构](folder-fields-stream-structures.md)。
  
## <a name="data-dump"></a>数据转储

下面是流的它将二进制编辑器中显示数据转储。
  
|流偏移|数据字节|ASCII 数据|
|:-----|:-----|:-----|
| `0000000000` <br/> | `02 00 00 00 01 00 00 00 0A 00 54 65 78 74 46 69` <br/> | `..........TextFi` <br/> |
| `0000000010` <br/> | `65 6C 64 31 29 03 02 00 00 00 00 00 C0 00 00 00` <br/> | `eld1).......A...` <br/> |
| `0000000020` <br/> | `00 00 00 46 07 00 00 80 00 00 00 00 00 00 00 00` <br/> | `...F............` <br/> |
| `0000000030` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000040` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000050` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `0000000060` <br/> | `00 00 00 00 00 00 02 00 00 00 01 00 00 00 0A 00` <br/> | `................` <br/> |
| `0000000070` <br/> | `54 00 65 00 78 00 74 00 46 00 69 00 65 00 6C 00` <br/> | `T.e.x.t.F.i.e.l.` <br/> |
| `0000000080` <br/> | `64 00 31 00 29 03 02 00 00 00 00 00 C0 00 00 00` <br/> | `d.1.).......A...` <br/> |
| `0000000090` <br/> | `00 00 00 46 07 00 00 80 00 00 00 00 00 00 00 00` <br/> | `...F............` <br/> |
| `00000000A0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000B0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000C0` <br/> | `00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00` <br/> | `................` <br/> |
| `00000000D0` <br/> | `00 00 00 00 00 00` <br/> | `......` <br/> |
   

以下是**FolderUserFields**流的示例数据的分析：
  
- FolderUserFieldsAnsi： 偏移的 0x0。
    
  - FieldDefinitionCount： 偏移 0x0，4 个字节： 0x00000002:uc (2)。
    
  - FieldDefinitions： 偏移 0x4，数组 2 FolderFieldDefinitionA 流。
    
    **第一个数组元素**：
    
    - FieldType： 偏移 0x4，4 个字节： 0x00000001 (ftString)。
      
    - FieldNameLength： 偏移 0x8，2 个字节： 0x000A (10)
      
    - FieldName： 偏移 0xA，10 个字符的数组。 ANSI 字符串值:"TextField1"。
      
    - 常见： 偏移 0x14。
    
      - PropSetGuid： 偏移 0x14，16 个字节: {00020329-0000-0000-C000-000000000046} (PS_PUBLIC_STRINGS)。
        
      - fcapm： 偏移 0x24，4 个字节： 0x80000007 (FCAPM_CAN_EDIT |FCAPM_CAN_SORT |FCAPM_CAN_GROUP |FCAPM_CAN_EDIT_IN_ITEM)。
        
      - dwString： 偏移 0x28，4 个字节： 0x00000000。
        
      - dwBitmap： 偏移 0x2C，4 个字节： 0x00000000。
        
      - dwDisplay： 偏移 0x30，4 个字节： 0x00000000。
        
      - iFmt： 偏移 0x34，4 个字节： 0x00000000。
        
      - wszFormulaLength： 偏移 0x38，2 个字节： 0x0000 (0)。
        
      - wszFormula： 偏移量 0x3A，0 WCHARs 的数组。 空字符串值。
    
    **第二个数组元素**：
    
    - FieldType： 偏移 0x3A，4 个字节： 0x00000000 (ftNone)。
      
    - FieldNameLength： 偏移 0x3E，2 个字节： 0x0000 (0)。
      
    - FieldName： 偏移 0x40，0 字符数组。 空字符串值。
      
    - 常见： 偏移 0x40。
    
      - PropSetGuid： 偏移 0x40，16 个字节： {00000000-0000-0000-0000-000000000000} (GUID_NULL)。
        
      - fcapm： 偏移 0x50，4 个字节： 0x00000000 (0)。
        
      - dwString： 偏移 0x54，4 个字节： 0x00000000。
        
      - dwBitmap： 偏移 0x58，4 个字节： 0x00000000。
        
      - dwDisplay： 偏移 0x5C，4 个字节： 0x00000000。
        
      - iFmt： 偏移 0x60，4 个字节： 0x00000000。
        
      - wszFormulaLength： 偏移 0x64，2 个字节： 0x0000 (0)。
        
      - wszFormula： 偏移量 0x66，0 WCHARs 的数组。 空字符串值。
    
- FolderUserFieldsUnicode： 偏移 0x66。
    
  - FieldDefinitionCount： 偏移 0x66，4 个字节： 0x00000002:uc (2)。
    
  - FieldDefinitions： 偏移 0x6A，数组 2 FolderFieldDefinitionW 流。
    
    **第一个数组元素**：
    
    - FieldType： 偏移 0x6A，4 个字节： 0x00000001 (ftString)。
      
    - FieldNameLength： 偏移 0x6E，2 个字节： 0x000A (10)。
      
    - FieldName： 偏移 0x70，10 WCHARs 的数组。 Unicode 字符串值:"TextField1"。
      
    - 常见： 偏移 0x84。
    
      - PropSetGuid： 偏移 0x84，16 个字节: {00020329-0000-0000-C000-000000000046} (PS_PUBLIC_STRINGS)。
        
      - fcapm： 偏移 0x94，4 个字节： 0x80000007 (FCAPM_CAN_EDIT |FCAPM_CAN_SORT |FCAPM_CAN_GROUP |FCAPM_CAN_EDIT_IN_ITEM)。
        
      - dwString： 偏移 0x98，4 个字节： 0x00000000。
        
      - dwBitmap： 偏移 0x9C，4 个字节： 0x00000000。
        
      - dwDisplay： 偏移 0xA0，4 个字节： 0x00000000。
        
      - iFmt： 偏移 0xA4，4 个字节： 0x00000000。
        
      - wszFormulaLength： 偏移 0xA8，2 个字节： 0x0000 (0)。
        
      - wszFormula： 偏移量 0xAA，0 WCHARs 的数组。 空字符串值。
    
    **第二个数组元素**：
    
    - FieldType： 偏移 0xAA，4 个字节： 0x00000000 (ftNone)。
      
    - FieldNameLength： 偏移 0xAE，2 个字节： 0x0000 (0)。
      
    - FieldName： 偏移 0xB0，0 WCHARs 的数组。 空字符串值。
      
    - 常见： 偏移 0xB0。
    
      - PropSetGuid： 偏移 0xB0，16 个字节： {00000000-0000-0000-0000-000000000000} (GUID_NULL)。
        
      - fcapm： 偏移 0xC0，4 个字节： 0x00000000 (0)。
        
      - dwString： 偏移 0xC4，4 个字节： 0x00000000。
        
      - dwBitmap： 偏移 0xC8，4 个字节： 0x00000000。
        
      - dwDisplay： 偏移 0xCC，4 个字节： 0x00000000。
        
      - iFmt： 偏移 0xD0，4 个字节： 0x00000000。
        
      - wszFormulaLength： 偏移 0xD4，2 个字节： 0x0000 (0)。
        
      - wszFormula： 偏移量 0xD6，0 WCHARs 的数组。 空字符串值。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项和字段](outlook-items-and-fields.md)
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)
- [FieldDefinition 流结构](fielddefinition-stream-structure.md)
- [SkipBlock 流结构](skipblock-stream-structure.md)
- [FirstSkipBlockContent 流结构](firstskipblockcontent-stream-structure.md)
- [PackedAnsiString 流结构](packedansistring-stream-structure.md)
- [PackedUnicodeString 流结构](packedunicodestring-stream-structure.md)

