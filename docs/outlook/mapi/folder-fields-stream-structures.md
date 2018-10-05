---
title: 文件夹字段流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: edbc9e6c-008c-4c13-9a0c-cb47ac0f3686
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96051bd2b62fd7c0e908a1018aac0225e44986be
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385086"
---
# <a name="folder-fields-stream-structures"></a>文件夹字段流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
消息的[PidTagUserFields](pidtaguserfields-canonical-property.md)属性包含二进制数据流，FolderUserFields，其中包含的文件夹的用户定义的字段定义。 本主题描述有关用户定义的字段定义的文件夹的流结构。 

FolderUserFields 流结构组成 FolderUserFieldsA 结构或 FolderUserFieldsA 结构跟 FolderUserFieldsW 结构。
  
此流中的数据元素存储紧随每个其他指定顺序如下：
  
- **FolderUserFieldsAnsi**: FolderUserFieldsA stream 结构。
    
- **FolderUserFieldsUnicode**（可选）： FolderUserFieldsW stream 结构。
    
FolderUserFieldsUnicode 状态检测到的 FolderUserFieldsAnsi 长度大于 FolderUserFields 的总长度。
  
> [!IMPORTANT]
> FolderUserFieldsAnsi 用于与旧，非 Unicode，版本的 MAPI 客户端的兼容性因此 FolderUserFieldsUnicode 是否存在，则忽略 FolderUserFieldsAnsi 的内容。 若要避免可能的数据中 ANSI 转换，始终创建 FolderUserFields 流时丢失包含 FolderUserFieldsW 部件。 
  
## <a name="folderuserfieldsa-stream-structure"></a>FolderUserFieldsA 流结构

FolderUserFieldsA 流结构是数组 FolderFieldDefinitionA 流结构包含定义的用户定义的所有字段，在 Outlook 文件夹中，除非覆盖 FolderUserFields 结构的 FolderUserFieldsW 部分。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：
  
- **FieldDefinitionCount**: DWORD （4 个字节），此流中的字段定义的数目。 这是**FieldDefinitions**数组中的元素的计数。
    
- **FieldDefinitions**： 数组 FolderFieldDefinitionA stream 结构。 此数组的计数等于**FieldDefinitionCount**数据元素。
    
除非此 FolderUserFieldsA 被覆盖的 FolderUserFieldsW 一部分 FolderUserFields 结构，该**FieldDefinitions**数组必须是"以 null 结尾"通过其最后一个 FolderFieldDefinitionA 元素 Common.FieldType 字段等于到 ftNull。
  
## <a name="folderuserfieldsw-stream-structure"></a>FolderUserFieldsW 流结构

FolderUserFieldsW 流结构是 FolderFieldDefinitionW 流结构包含定义的 Outlook 文件夹中所有用户定义的字段的数组。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：
  
- **FieldDefinitionCount**: DWORD （4 个字节），此流中的字段定义的数目。 这是**FieldDefinitions**数组中的元素的计数。
    
- **FieldDefinitions**： 数组 FolderFieldDefinitionW stream 结构。 此数组的计数等于**FieldDefinitionCount**数据元素。
    
**FieldDefinitions**数组必须是"以 null 结尾"，通过其最后一个 FolderFieldDefinitionW 元素 Common.FieldType 字段等于 ftNull。
  
## <a name="folderfielddefinitiona-stream-structure"></a>FolderFieldDefinitionA 流结构

FolderFieldDefinitionA 流结构与存储在 ANSI 中的字段名称中包含用户定义的字段的定义。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：
  
- **FieldType**: FldType （4 个字节），此字段的类型。
    
- **FieldNameLength**： 单词 （2 个字节）， **FieldName**数组中的元素的数目。
    
- **FieldName**: CHAR 的数组。 这是 ANSI CP_ACP 代码页表示的字段名称。 此数组的计数等于**FieldNameLength**。 字段名称都必须满足的[UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的名称参数的限制。 
    
   > [!NOTE]
   > 出于旧的兼容性，Outlook 可能能够处理不满足这些限制某些**FieldName**值，但是这种情况下不包含的此主题。 
  
- **常见**： FolderFieldDefinitionCommon stream 结构。
    
## <a name="folderfielddefinitionw-stream-structure"></a>FolderFieldDefinitionW 流结构

FolderFieldDefinitionW 流结构与存储在 Unicode 中的字段名称中包含用户定义的字段的定义。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：
  
- **FieldType**: FldType （4 个字节），此字段的类型。
    
- **FieldNameLength**： 单词 （2 个字节）， **FieldName**数组中的元素的数目。
    
- **FieldName**: WCHAR 的数组。 这是字段名称的 Unicode (utf-16) 表示形式。 此数组的计数等于**FieldNameLength**。 字段名称都必须满足的[UserProperties.Add](https://msdn.microsoft.com/library/microsoft.office.interop.outlook.userproperties.add.aspx)方法中指定的名称参数的限制。 
    
   > [!NOTE]
   > 出于旧的兼容性，Outlook 可能能够处理一些**FieldName**值不满足这些限制，但这种情况下不受本主题。 
  
- **常见**： FolderFieldDefinitionCommon stream 结构。
    
## <a name="fldtype-enumeration"></a>FldType 枚举

下表列出了**FldType**枚举值。 
  
|名称|值|含义|
|:-----|:-----|:-----|
|ftNull  <br/> |0x0  <br/> |此字段类型用于 null 终止字段定义的数组。  <br/> |
|ftString  <br/> |0x1  <br/> |文本  <br/> |
|ftInteger  <br/> |0x3  <br/> |整数  <br/> |
|ftTime  <br/> |0x5  <br/> |日期/时间  <br/> |
|ftBoolean  <br/> |0x6  <br/> |是/否  <br/> |
|ftDuration  <br/> |0x7  <br/> |Duration  <br/> |
|ftMultiString  <br/> |0xB  <br/> |Keywords  <br/> |
|ftFloat  <br/> |0xC  <br/> |数值或百分比  <br/> |
|ftCurrency  <br/> |0xE  <br/> |货币  <br/> |
|ftCalc  <br/> |0x12  <br/> |公式  <br/> |
|ftSwitch  <br/> |0x13  <br/> |仅显示第一个非空字段-忽略后续字段类型的组合。  <br/> |
|ftConcat  <br/> |0x17  <br/> |联接字段及任何文本片断每个其他类型的组合。  <br/> |
   
## <a name="folderfielddefinitioncommon-stream-structure"></a>FolderFieldDefinitionCommon 流结构

FolderFieldDefinitionCommon 流结构包含 FolderFieldDefinitionA 和 FolderFieldDefinitionW 常用的用户定义的字段定义的数据。
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟每个其他指定顺序如下：
  
- **PropSetGuid**: GUID （16 个字节） 的属性集的文件夹字段对应的 MAPI 属性名的 GUID。 此字段的值必须等于 PS_PUBLIC_STRINGS，除非字段类型是**ftNone**在这种情况下，此字段的值必须是等于 GUID_NULL。 
    
   > [!NOTE]
   > 出于旧的兼容性，Outlook 可能能够处理不满足此限制某些**PropSetGuid**值，但是这种情况下不包含的此主题。 
  
- **fcapm**: DWORD （4 个字节） 下, 表中列出的值以及的含义的零个或多个标志的组合。 具有相同值的标志有取决于该字段的类型，即 FldType 值的含义。
    
    |代表标志名称|值|含义|
    |:-----|:-----|:-----|
    |FCAPM_CAN_EDIT  <br/> |0x00000001  <br/> |域是可编辑。  <br/> |
    |FCAPM_CAN_SORT  <br/> |0x00000002  <br/> |字段进行排序。  <br/> |
    |FCAPM_CAN_GROUP  <br/> |0x00000004  <br/> |域是树状。  <br/> |
    |FCAPM_MULTILINE_TEXT  <br/> |0x00000100  <br/> |字段可以包含多行文本。  <br/> |
    |FCAPM_PERCENT  <br/> |0x01000000  <br/> |此字段的类型 ftFloat 是百分比字段。  <br/> |
    |FCAPM_DATEONLY  <br/> |0x01000000  <br/> |此字段的类型 ftTime 是仅日期时间字段。  <br/> |
    |FCAPM_UNITLESS  <br/> |0x01000000  <br/> |对于类型 ftInteger 此字段，没有单位允许显示格式;例如此类作为格式"计算机-640 k。..."不允许使用。  <br/> |
    |FCAPM_CAN_EDIT_IN_ITEM  <br/> |0x80000000  <br/> |字段可编辑项中： 这是专为自定义窗体。  <br/> |
   
- **dwString**: DWORD （4 个字节）。 请参阅第一个以下注释。
    
- **dwBitmap**: DWORD （4 个字节）。 请参阅第一个以下注释。
    
- **dwDisplay**: DWORD （4 个字节）。 请参阅第一个以下注释。
    
- **iFmt**: INT （4 个字节）。 字段类型具有"格式:"组合框中的"新建域"、"编辑域"和"字段属性"对话框，该组合框中选定的格式的基于 0 的索引。 没有该组合框的字段类型，这必须是 0。 该字段的值与字段类型一起唯一确定**dwString**， **dwBitmap**的值并**dwDisplay**字段，，请参阅第一个以下注释。
    
- **wszFormulaLength**： 单词 （2 个字节）， **wszFormulaLength**数组中的元素的数目。
    
- **wszFormulaLength**: WCHAR 的数组。 这是该字段的公式其标准格式字符串的 Unicode (utf-16) 表示形式。 请参阅标准的说明和 UI 格式的字段的公式的第二个以下注释。 此数组的计数等于**wszFormulaLength**。 公式的字符串必须为空字符串，除非字段类型为**ftCalc**、 **ftSwitch**或**ftConcat**。
    
> [!NOTE]
> 尽管**dwString**、 **dwBitmap**和**dwDisplay**的值唯一根据**FldType**值和**iFmt**值，它们是冗余，来确定其正确的值是仍所必需的正确处理 outlook 字段定义。 执行此决定的算法没有简单说明。 
> 
> 因此，若要找出哪些**dwString**、 **dwBitmap**和**dwDisplay**值对应于给定的**FldType**值和**iFmt**值，请执行测试通过创建用户定义的字段，该类型，并且所选的格式在**格式**组合框中，假定其适用性，检查为该用户定义的字段创建 Outlook 生成**FolderUserFields**流。 
  
在**新域**、**编辑字段**中，和用户定义的字段的**字段属性**对话框的**公式**文本框中编辑其 UI 格式中的字段的公式。 要将公式从 UI 格式转换为标准格式的算法取决于该字段类型中以下所述： 
- 对于类型**ftCalc**和**ftSwitch**的字段，内置域，不是相应的 MAPI 属性的标准格式的命名属性 kind MNID\_字符串，即替换字段名称片段，获得`[<field_name>]`使用片段`[_<field_dispid_decimal>]`。 

  例如，如果类型**公式**，即**ftCalc**，与正在美国英语的 Office UI 语言的字段的公式的 UI 格式为`[Business Phone] & [My custom field]`，其中`My custom field`是名称采用的用户定义的字段，此类公式的标准格式`[_14856] & [My custom field]`.

- 对于类型**ftConcat**的字段，可通过执行以下获得标准格式：

  1. 截断前导和尾随空白。 
  2. 分析公式转换为以下两种类型的片段序列： 
     - 用方括号，即，字段名称`[<field_name>]`。 
     - 不包含任何方括号子字符串。   
      确保没有两个段落的第二类彼此相邻的顺序。 如果公式无法分析这种方式，它将被视为无效。 
  3. 对于**ftCalc**和**ftSwitch**字段相同的第一类的片段执行替换为相同。 
  4. 为第二个类型的每个片段，转义所有双引号 (""") 字符，如果有，具有两个连续双引号字符，并将其括在双引号。 
  5. 插入 & 字符串 (`&`) 相邻片段每对之间。
 
  例如，使用美国英语的 Office UI 语言的字段的类型**ftConcat**公式的 UI 格式为时`text1 [Business Phone] "text2" [My custom field]`，其中`My custom field`是用户定义的字段，标准格式的名称，这样的公式很`""text1" & [_14856] & """text2""" & [My custom field]"`。 
  
## <a name="see-also"></a>另请参阅

- [FolderUserFields 流示例](folderuserfields-stream-sample.md)
- [为新的用户定义字段添加定义](how-to-add-a-definition-for-a-new-user-defined-field.md)

