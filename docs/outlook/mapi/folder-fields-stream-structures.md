---
title: 文件夹字段流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: edbc9e6c-008c-4c13-9a0c-cb47ac0f3686
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96051bd2b62fd7c0e908a1018aac0225e44986be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336888"
---
# <a name="folder-fields-stream-structures"></a>文件夹字段流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
邮件的 [PidTagUserFields](pidtaguserfields-canonical-property.md) 属性包含二进制流 FolderUserFields，其中包含文件夹用户定义的字段定义。 本主题介绍文件夹用户定义的字段定义的流结构。 

FolderUserFields 流结构由 FolderUserFieldsA 结构或 FolderUserFieldsA 结构后跟 FolderUserFieldsW 结构组成。
  
此流中的数据元素按以下指定顺序紧接在一起存储：
  
- **FolderUserFieldsAnsi：FolderUserFieldsA** 流结构。
    
- **FolderUserFieldsUnicode** (可选) ：FolderUserFieldsW 流结构。
    
FolderUserFieldsUnicode 存在由 FolderUserFields 的总长度大于 FolderUserFieldsAnsi 的长度检测到。
  
> [!IMPORTANT]
> FolderUserFieldsAnsi 用于兼容较旧的非 Unicode 版本的 MAPI 客户端，因此如果存在 FolderUserFieldsUnicode，则忽略 FolderUserFieldsAnsi 的内容。 为了避免在 ANSI 转换中丢失数据，在创建 FolderUserFields 流时，始终包括 FolderUserFieldsW 部件。 
  
## <a name="folderuserfieldsa-stream-structure"></a>FolderUserFieldsA 流结构

FolderUserFieldsA 流结构是 FolderFieldDefinitionA 流结构的数组，其中包含 Outlook 文件夹中所有用户定义字段的定义，除非 FolderUserFields 结构的 FolderUserFieldsW 部分重写。
  
此流中的数据元素按小尾字节顺序存储，并按以下指定顺序彼此紧随：
  
- **FieldDefinitionCount**：DWORD (4 字节) ，即此流中的字段定义数。 这是 **FieldDefinitions 数组中的元素** 计数。
    
- **FieldDefinitions：FolderFieldDefinitionA** 流结构的数组。 此数组的计数等于 **FieldDefinitionCount** 数据元素。
    
除非 FolderUserFieldsA 由 FolderUserFields 结构的 FolderUserFieldsW 部分替代，否则 **FieldDefinitions** 数组必须通过将最后一个 FolderFieldDefinitionA 元素的 Common.FieldType 字段等于 ftNull 来"以 null 终止"。
  
## <a name="folderuserfieldsw-stream-structure"></a>FolderUserFieldsW Stream 结构

FolderUserFieldsW 流结构是 FolderFieldDefinitionW 流结构的数组，其中包含 Outlook 文件夹中所有用户定义字段的定义。
  
此流中的数据元素按小尾字节顺序存储，并按以下指定顺序彼此紧随：
  
- **FieldDefinitionCount**：DWORD (4 字节) ，即此流中的字段定义数。 这是 **FieldDefinitions 数组中的元素** 计数。
    
- **FieldDefinitions：FolderFieldDefinitionW** 流结构的数组。 此数组的计数等于 **FieldDefinitionCount** 数据元素。
    
**FieldDefinitions** 数组必须"null-terminated"，其最后一个 FolderFieldDefinitionW 元素的 Common.FieldType 字段等于 ftNull。
  
## <a name="folderfielddefinitiona-stream-structure"></a>FolderFieldDefinitionA 流结构

FolderFieldDefinitionA 流结构包含用户定义的字段的定义，该字段的名称存储在 ANSI 中。
  
此流中的数据元素按小尾字节顺序存储，并按以下指定顺序彼此紧随：
  
- **FieldType**：FldType (4 字节) ，此字段的类型。
    
- **FieldNameLength：WORD** (2 字节) ， **即 FieldName** 数组中的元素数。
    
- **FieldName**：CHAR 的数组。 这是字段名称CP_ACP ANSI 代码页表示形式。 此数组的计数等于 **FieldNameLength**。 字段名称必须满足 [UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx) 方法中指定的对 Name 参数的限制。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因，Outlook 可能无法处理某些不满足这些限制的 **FieldName** 值，但本主题未涵盖此类情况。 
  
- **常见**：FolderFieldDefinitionCommon 流结构。
    
## <a name="folderfielddefinitionw-stream-structure"></a>FolderFieldDefinitionW 流结构

FolderFieldDefinitionW 流结构包含用户定义的字段的定义，该字段的名称存储在 Unicode 中。
  
此流中的数据元素按小尾字节顺序存储，并按以下指定顺序彼此紧随：
  
- **FieldType**：FldType (4 字节) ，此字段的类型。
    
- **FieldNameLength：WORD** (2 字节) ， **即 FieldName** 数组中的元素数。
    
- **FieldName：WCHAR** 的数组。 这是字段名称的 Unicode (UTF-16) 表示形式。 此数组的计数等于 **FieldNameLength**。 字段名称必须满足 [UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx) 方法中指定的对 Name 参数的限制。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因，Outlook 可能能够处理一些不满足这些限制的 **FieldName** 值，但本主题未涵盖此类情况。 
  
- **常见**：FolderFieldDefinitionCommon 流结构。
    
## <a name="fldtype-enumeration"></a>FldType 枚举

**FldType** 枚举值如下表所列。 
  
|名称|值|含义|
|:-----|:-----|:-----|
|ftNull  <br/> |0x0  <br/> |此字段类型用于以 null 终止字段定义的数组。  <br/> |
|ftString  <br/> |0x1  <br/> |文本  <br/> |
|ftInteger  <br/> |0x3  <br/> |整数  <br/> |
|ftTime  <br/> |0x5  <br/> |日期/时间  <br/> |
|ftBoolean  <br/> |0x6  <br/> |是/否  <br/> |
|ftDuration  <br/> |0x7  <br/> |期限  <br/> |
|ftMultiString  <br/> |0xB  <br/> |关键字  <br/> |
|ftFloat  <br/> |0xC  <br/> |数字或百分比  <br/> |
|ftCurrency  <br/> |0xE  <br/> |货币  <br/> |
|ftCalc  <br/> |0x12  <br/> |公式  <br/> |
|ftSwitch  <br/> |0x13  <br/> |只显示第一个非空字段的类型组合 - 忽略后续字段。  <br/> |
|ftConcat  <br/> |0x17  <br/> |将字段类型与任意文本片段相互组合。  <br/> |
   
## <a name="folderfielddefinitioncommon-stream-structure"></a>FolderFieldDefinitionCommon 流结构

FolderFieldDefinitionCommon 流结构包含用户定义的字段定义的数据，该定义对 FolderFieldDefinitionA 和 FolderFieldDefinitionW 都很常见。
  
此流中的数据元素按小尾字节顺序存储，并按以下指定顺序彼此紧随：
  
- **PropSetGuid**：GUID (16) ，即文件夹字段的相应 MAPI 属性名称的属性集 GUID。 此字段的值必须等于 PS_PUBLIC_STRINGS，除非字段类型是 **ftNone，** 在这种情况下，此字段的值必须等于 GUID_NULL。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因，Outlook 也许能够处理一些不满足此限制的 **PropSetGuid** 值，但本主题未涵盖此类情况。 
  
- **fcapm：DWORD** (4 字节) ，零个或多个标记的组合标记下表列出了其值和含义。 具有相同值的标志的含义取决于字段的类型，即 FldType 值。
    
    |标志名称|值|含义|
    |:-----|:-----|:-----|
    |FCAPM_CAN_EDIT  <br/> |0x00000001  <br/> |字段是可编辑的。  <br/> |
    |FCAPM_CAN_SORT  <br/> |0x00000002  <br/> |字段可排序。  <br/> |
    |FCAPM_CAN_GROUP  <br/> |0x00000004  <br/> |字段可分组。  <br/> |
    |FCAPM_MULTILINE_TEXT  <br/> |0x00000100  <br/> |该字段可以包含多个文本行。  <br/> |
    |FCAPM_PERCENT  <br/> |0x01000000  <br/> |类型为 ftFloat 的此字段是百分比字段。  <br/> |
    |FCAPM_DATEONLY  <br/> |0x01000000  <br/> |类型 ftTime 的此字段是仅日期时间字段。  <br/> |
    |FCAPM_UNITLESS  <br/> |0x01000000  <br/> |对于 ftInteger 类型的此字段，不允许以显示格式使用单位;例如，"Computer - 640 K..."等格式不允许。  <br/> |
    |FCAPM_CAN_EDIT_IN_ITEM  <br/> |0x80000000  <br/> |可以在项中编辑字段：这专用于自定义窗体。  <br/> |
   
- **dwString**：DWORD (4 字节) 。 请参阅下面的第一条"注意"。
    
- **dwBitmap**：DWORD (4 字节) 。 请参阅下面的第一条"注意"。
    
- **dwDisplay**：DWORD (4 字节) 。 请参阅下面的第一条"注意"。
    
- **iFmt**：INT (4 字节) 。 对于"新建字段"、"编辑字段"和"字段属性"对话框中具有"Format："组合框的字段类型，该组合框中所选格式的基于 0 的索引。 对于没有该组合框的字段类型，必须为 0。 字段值与字段类型一起唯一地确定 **dwString、dwBitmap** 和 **dwDisplay** 字段的值，请参阅下面的第一个注释。
    
- **wszFormulaLength：WORD** (2 字节) ， **即 wszFormulaLength 数组中的元素** 数。
    
- **wszFormulaLength：WCHAR** 的数组。 这是 Unicode (UTF-16) 格式的字段公式字符串的表示形式。 有关字段公式的标准和 UI 格式的说明，请参阅下面的第二个注释。 此数组的计数等于 **wszFormulaLength**。 公式字符串必须为空字符串，除非字段类型是 **ftCalc**、 **ftSwitch** 或 **ftConcat**。
    
> [!NOTE]
> 尽管 **dwString、dwBitmap** 和 **dwDisplay** 的值根据 **FldType** 值和 **iFmt** 值（冗余）进行唯一确定，但是 Outlook 正确处理字段定义仍然需要这些值。 没有用于执行此确定算法的简单说明。 
> 
> 因此，若要找出哪些 **dwString、dwBitmap** 和 **dwDisplay** 值对应于给定的 **FldType** 值和 **iFmt** 值，请通过创建该类型的用户定义的字段来执行测试，使用在"格式"组合框中选择的格式（假定其适用性）检查 Outlook 为该用户定义的字段创建的结果 **FolderUserFields** 流。  
  
字段的 UI 格式的公式在用户定义的字段的"新建字段"、"编辑字段"和"字段属性"对话框的"公式"文本框中编辑。  将公式从 UI 格式转换为标准格式的算法取决于字段类型，如下所述： 
- 对于 **类型为 ftCalc** 和 **ftSwitch** 的字段，内置字段的标准格式（对应的 MAPI 属性不是类型 MNID STRING 的命名属性）通过替换字段名称片段（即片段）获取。 \_ `[<field_name>]` `[_<field_dispid_decimal>]` 

  例如，如果公式类型为 **Formula** 的字段（即 **ftCalc，Office** UI 语言为美国英语）的 UI 格式为 ，其中 是用户定义字段的名称，则此类公式的标准格式为 `[Business Phone] & [My custom field]` `My custom field` `[_14856] & [My custom field]` 。

- 对于 **类型 ftConcat** 的字段，通过执行下列操作获得标准格式：

  1. 截断前导空格和尾随空格。 
  2. 将公式解析为以下两种类型的片段序列： 
     - 方括号中的字段名称，即 `[<field_name>]` 。 
     - 不包含任何方括号的子字符串。   
      确保序列中不相邻第二类的两个片段。 如果无法通过此方式分析公式，则认为它无效。 
  3. 对第一种片段执行与 **ftCalc** 和 **ftSwitch** 字段相同的替换。 
  4. 对于第二种的每个片段，用两个连续的双引号字符转义所有双引号 (""") 字符（如果有）并括在双引号中。 
  5. 在每个相邻片段对 () 插入一个 `&` 与字符的字符串。
 
  例如，使用 Office UI 语言美国英语，如果 **ftConcat** 类型的字段的公式的 UI 格式为 ，其中 是用户定义的域的名称，则此类公式的标准格式为 `text1 [Business Phone] "text2" [My custom field]` `My custom field` `""text1" & [_14856] & """text2""" & [My custom field]"` 。 
  
## <a name="see-also"></a>另请参阅

- [FolderUserFields 流示例](folderuserfields-stream-sample.md)
- [添加新字段User-Defined定义](how-to-add-a-definition-for-a-new-user-defined-field.md)

