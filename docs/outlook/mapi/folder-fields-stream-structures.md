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
  
邮件的[PidTagUserFields](pidtaguserfields-canonical-property.md)属性包含二进制流 FolderUserFields, 其中包含文件夹用户定义的字段定义。 本主题介绍文件夹用户定义的字段定义的流结构。 

FolderUserFields 流结构由 FolderUserFieldsA 结构或 FolderUserFieldsA 结构组成, 其后跟 FolderUserFieldsW 结构。
  
此流中的数据元素按以下指定顺序立即按以下顺序存储:
  
- **FolderUserFieldsAnsi**: FolderUserFieldsA 流结构。
    
- **FolderUserFieldsUnicode**(可选): FolderUserFieldsW 流结构。
    
FolderUserFieldsUnicode 的总长度检测到的 FolderUserFields 的总长度大于 FolderUserFieldsAnsi 的长度。
  
> [!IMPORTANT]
> FolderUserFieldsAnsi 用于与 MAPI 客户端的旧版本、非 Unicode 版本兼容, 因此, 如果存在 FolderUserFieldsUnicode, FolderUserFieldsAnsi 的内容将被忽略。 若要避免在 ANSI 转换过程中可能出现数据丢失, 创建 FolderUserFields 流时始终包含 FolderUserFieldsW 部件。 
  
## <a name="folderuserfieldsa-stream-structure"></a>FolderUserFieldsA 流结构

FolderUserFieldsA 流结构是 FolderFieldDefinitionA 流结构的数组, 其中包含 Outlook 文件夹中所有用户定义的字段的定义, 除非由 FolderUserFields 结构的 FolderUserFieldsW 部分重写。
  
此流中的数据元素以小字节序字节顺序存储, 并按以下指定顺序立即后续:
  
- **FieldDefinitionCount**: DWORD (4 个字节), 此流中的字段定义数。 这是**FieldDefinitions**数组中的元素数。
    
- **FieldDefinitions**: FolderFieldDefinitionA 流结构的数组。 此数组的计数等于**FieldDefinitionCount**数据元素。
    
除非 FolderUserFields 结构的 FolderUserFieldsW 部分重写了此 FolderUserFieldsA, 否则**FieldDefinitions**数组必须为其最后一个 FolderFieldDefinitionA 元素的常见. FieldType 字段等于 "null 终止"到 ftNull。
  
## <a name="folderuserfieldsw-stream-structure"></a>FolderUserFieldsW 流结构

FolderUserFieldsW 流结构是 FolderFieldDefinitionW 流结构的数组, 其中包含 Outlook 文件夹中所有用户定义的字段的定义。
  
此流中的数据元素以小字节序字节顺序存储, 并按以下指定顺序立即后续:
  
- **FieldDefinitionCount**: DWORD (4 个字节), 此流中的字段定义数。 这是**FieldDefinitions**数组中的元素数。
    
- **FieldDefinitions**: FolderFieldDefinitionW 流结构的数组。 此数组的计数等于**FieldDefinitionCount**数据元素。
    
通过将**FieldDefinitions**数组的最后一个 FolderFieldDefinitionW 元素的 FieldType 字段等于 ftNull, 该数组必须为 "以 null 结尾"。
  
## <a name="folderfielddefinitiona-stream-structure"></a>FolderFieldDefinitionA 流结构

FolderFieldDefinitionA 流结构包含用户定义字段的定义, 该字段名称存储在 ANSI 中。
  
此流中的数据元素以小字节序字节顺序存储, 并按以下指定顺序立即后续:
  
- **FieldType**: FldType (4 个字节), 此字段的类型。
    
- **FieldNameLength**: WORD (2 个字节), **FieldName**数组中的元素数。
    
- **FieldName**: 字符数组。 这是字段名称的 ANSI CP_ACP 代码页表示形式。 此数组的计数等于**FieldNameLength**。 字段名称必须满足在[UserProperties](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的 name 参数的限制。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因, Outlook 可能会处理一些无法满足这些限制的**FieldName**值, 但本主题不包含此类情况。 
  
- **常见**: FolderFieldDefinitionCommon 流结构。
    
## <a name="folderfielddefinitionw-stream-structure"></a>FolderFieldDefinitionW 流结构

FolderFieldDefinitionW 流结构包含使用 Unicode 存储的字段名称的用户定义字段的定义。
  
此流中的数据元素以小字节序字节顺序存储, 并按以下指定顺序立即后续:
  
- **FieldType**: FldType (4 个字节), 此字段的类型。
    
- **FieldNameLength**: WORD (2 个字节), **FieldName**数组中的元素数。
    
- **FieldName**: WCHAR 数组。 这是字段名称的 Unicode (UTF-16) 表示形式。 此数组的计数等于**FieldNameLength**。 字段名称必须满足在[UserProperties](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的 name 参数的限制。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因, Outlook 可能会处理一些无法满足这些限制的**FieldName**值, 但本主题不包含此类情况。 
  
- **常见**: FolderFieldDefinitionCommon 流结构。
    
## <a name="fldtype-enumeration"></a>FldType 枚举

下表列出了**FldType**枚举值。 
  
|名称|值|含义|
|:-----|:-----|:-----|
|ftNull  <br/> |0x0  <br/> |此字段类型用于为 null 终止字段定义的数组。  <br/> |
|ftString  <br/> |0x1  <br/> |文本  <br/> |
|ftInteger  <br/> |0x3  <br/> |整数  <br/> |
|ftTime  <br/> |0x5  <br/> |日期/时间  <br/> |
|ftBoolean  <br/> |0x6  <br/> |是/否  <br/> |
|ftDuration  <br/> |0x7  <br/> |持续时间  <br/> |
|ftMultiString  <br/> |0xB  <br/> |关键字  <br/> |
|ftFloat  <br/> |0xC  <br/> |数字或百分比  <br/> |
|ftCurrency  <br/> |0xE  <br/> |货币  <br/> |
|ftCalc  <br/> |0x12  <br/> |Formula  <br/> |
|ftSwitch  <br/> |0x13  <br/> |仅显示第一个非空字段的类型组合-将忽略后续的字段。  <br/> |
|ftConcat  <br/> |0x17  <br/> |类型相互联接字段和任何文本片段的组合。  <br/> |
   
## <a name="folderfielddefinitioncommon-stream-structure"></a>FolderFieldDefinitionCommon 流结构

FolderFieldDefinitionCommon 流结构包含 FolderFieldDefinitionA 和 FolderFieldDefinitionW 通用的用户定义的字段定义的数据。
  
此流中的数据元素以小字节序字节顺序存储, 并按以下指定顺序立即后续:
  
- **PropSetGuid**: GUID (16 个字节), "文件夹" 字段相应的 MAPI 属性名称的属性集 GUID。 此字段的值必须等于 PS_PUBLIC_STRINGS, 除非字段类型为**ftNone** 。在这种情况下, 此字段的值必须等于 GUID_NULL。 
    
   > [!NOTE]
   > 出于旧版兼容性的原因, Outlook 可以处理一些**PropSetGuid**值不符合此限制的情况, 但本主题不包含这种情况。 
  
- **fcapm**: DWORD (4 个字节), 下表列出了零个或多个标志的值与这些值和含义的值的组合。 具有相同值的标志的含义取决于字段的类型, 即 FldType 值。
    
    |标记名称|值|含义|
    |:-----|:-----|:-----|
    |FCAPM_CAN_EDIT  <br/> |0x00000001  <br/> |该字段是可编辑的。  <br/> |
    |FCAPM_CAN_SORT  <br/> |0x00000002  <br/> |字段是可排序的。  <br/> |
    |FCAPM_CAN_GROUP  <br/> |0x00000004  <br/> |字段为 groupable。  <br/> |
    |FCAPM_MULTILINE_TEXT  <br/> |0x00000100  <br/> |该字段可以包含多行文本。  <br/> |
    |FCAPM_PERCENT  <br/> |0x01000000  <br/> |"ftFloat" 类型的此字段是 "百分比" 字段。  <br/> |
    |FCAPM_DATEONLY  <br/> |0x01000000  <br/> |ftTime 类型的此字段是仅限日期的时间字段。  <br/> |
    |FCAPM_UNITLESS  <br/> |0x01000000  <br/> |对于类型为 ftInteger 的此字段, 显示格式中不允许使用任何单位;例如 "Computer-640 K ..." 的格式不允许使用。  <br/> |
    |FCAPM_CAN_EDIT_IN_ITEM  <br/> |0x80000000  <br/> |可以在项目中编辑该字段: 这是专门针对自定义窗体的。  <br/> |
   
- **dwString**: DWORD (4 个字节)。 请参阅第一个后面的注释。
    
- **dwBitmap**: DWORD (4 个字节)。 请参阅第一个后面的注释。
    
- **dwDisplay**: DWORD (4 个字节)。 请参阅第一个后面的注释。
    
- **iFmt**: INT (4 个字节)。 对于 "New field"、"Edit field" 和 "field Properties" 对话框中具有 "format:" 组合框的字段类型, 该组合框中所选格式的从0开始的索引。 对于没有该组合框的字段类型, 该类型必须为0。 字段的值与字段类型一起唯一地确定**dwString**、 **dwBitmap**和**dwDisplay**字段的值, 请参阅第一个下一条注释。
    
- **wszFormulaLength**: WORD (2 个字节), **wszFormulaLength**数组中的元素数。
    
- **wszFormulaLength**: WCHAR 的数组。 这是其标准格式的字段的公式字符串的 Unicode (utf-16) 表示形式。 请参阅第二个注释, 了解有关字段公式的标准和 UI 格式的说明。 此数组的计数等于**wszFormulaLength**。 如果字段类型为**ftCalc**、 **ftSwitch**或**ftConcat**, 则公式字符串必须为空字符串。
    
> [!NOTE]
> 尽管**dwString**、 **dwBitmap**和**dwDisplay**的值是基于**FldType**值和**iFmt**值 (这些值是冗余的) 进行唯一确定的, 但仍需要它们的正确值才能正确Outlook 对字段定义的处理。 对执行此确定的算法没有简单的描述。 
> 
> 因此, 若要找出哪个**dwString**、 **dwBitmap**和**dwDisplay**值对应于给定的**FldType**值和**iFmt**值, 请通过创建该类型的用户定义的字段, 并选择该格式来执行测试在 "**格式**" 组合框中, 假定其适用性, 检查 Outlook 为该用户定义的字段创建的结果**FolderUserFields**流。 
  
在用户定义的字段的**新字段**、**编辑字段**和**字段属性**对话框的 "**公式**" 文本框中编辑字段的 UI 格式的公式。 将公式从 UI 格式转换为标准格式的算法取决于字段类型, 如下所述: 
- 对于**ftCalc**和**ftSwitch**类型的字段, 内置字段的标准格式 (其对应的 MAPI 属性不是类型 MNID\_字符串的命名属性) 是通过替换字段名称片段获取的, 这是`[<field_name>]`包含片段`[_<field_dispid_decimal>]`。 

  例如, 如果类型**公式**的某个字段的公式的 UI 格式为**ftCalc**, 而 Office UI 语言为美国英语`[Business Phone] & [My custom field]`, 则在其中`My custom field`是用户定义字段的名称, 这种公式的标准格式是`[_14856] & [My custom field]`.

- 对于类型为**ftConcat**的字段, 将通过执行以下操作来获取标准格式:

  1. 截断前导和尾随空格。 
  2. 将公式分析为以下两种类型的段落序列: 
     - 括在方括号中的字段名称, 即`[<field_name>]`。 
     - 不包含任何方括号的子串。   
      确保序列中的第二种片段没有相邻的两个片段。 如果无法通过这种方式解析公式, 则认为该公式无效。 
  3. 对 " **ftCalc** " 和 " **ftSwitch** " 字段执行对第一种类型的段落的相同替换。 
  4. 对于第二种类型的每个片段, 转义所有双引号 ("" ") 字符 (如果有), 并使用两个连续的双引号字符将其括在双引号中。 
  5. 在每对相邻片段`&`之间插入一个和号字符串 ()。
 
  例如, 如果类型为**ftConcat**的字段的公式的 UI 格式是`text1 [Business Phone] "text2" [My custom field]`, 使用 Office UI 语言 US 英语, 其中`My custom field`是用户定义字段的名称, 则此类公式的标准格式为。 `""text1" & [_14856] & """text2""" & [My custom field]"` 
  
## <a name="see-also"></a>另请参阅

- [FolderUserFields 流示例](folderuserfields-stream-sample.md)
- [为新的用户定义的字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)

