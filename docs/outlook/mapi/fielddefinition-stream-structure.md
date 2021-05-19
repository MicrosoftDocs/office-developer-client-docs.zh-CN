---
title: FieldDefinition 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 93acdbc8-381f-45d5-be6c-0cad066269fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 98584e450bb820dbce05b0f8d2c6d15551586130
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334893"
---
# <a name="fielddefinition-stream-structure"></a>FieldDefinition 流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
FieldDefinition 流结构包含用户定义的字段的字段定义，或内置字段的一组数据绑定设置。
  
如果 FieldDefinition 流结构包含用户定义字段的字段定义，则可以通过编程方式操作该结构。 如果 FieldDefinition 结构包含内置字段的设置，您不应尝试以编程方式创建或修改该结构。 您应该使用 Microsoft Outlook窗体设计器来维护内置字段的此类设置。
  
> [!NOTE]
> Outlook字段定义的两种格式：PropDefV1 和 PropDefV2。 字段定义的 PropDefV1 格式包含以下数据元素：Flags、VT、DispId、NmidNameLength、nmidName、NameANSI、FormulaANSI、ValidationRuleANSI、ValidationTextANSI 和 ErrorANSI。 PropDefV2 格式包含相同的元素以及 InternalType 和 SkipBlocks 元素。 
>
> Outlook PropDefV2 字段定义格式维护 FormulaANSI、ValidationRuleANSI 和 ValidationTextANSI 数据元素的 Unicode 版本。 如果这些元素包含非 ASCII 字符，则根据运行这些字符的计算机的 ANSI 代码页，这些Outlook不一致。 因此，应该只对这些数据元素使用完全由 ASCII 字符组成的字符串值。 
  
此流中的数据元素以小尾序字节顺序存储，并按下面指定的顺序彼此紧接。
  
- Flags： DWORD (4 bytes) ， a combination of zero or more flags whose values and meanings are listed in the following table.
    
    |**标志名称**|**值**|**说明**|
    |:-----|:-----|:-----|
    |PDO_IS_CUSTOM  <br/> |0x00000001  <br/> |FieldDefinition 结构包含用户定义的字段的定义。  <br/> |
    |PDO_REQUIRED  <br/> |0x00000002  <br/> |对于绑定到此字段的窗体控件，在"属性"对话框的"验证"选项卡中选中"此字段需要 A  **值**"复选框。  <br/> |
    |PDO_PRINT_SAVEAS  <br/> |0x00000004  <br/> |对于绑定到此字段的窗体控件，"属性"对话框的"验证"选项卡中选中了"包括此字段 **进行** 打印和另存 **为"复选框**。  <br/> |
    |PDO_CALC_AUTO  <br/> |0x00000008  <br/> |对于绑定到此字段的窗体控件，"属性"对话框的"值"选项卡中选中"自动计算此 **公式"复选框**。  <br/> |
    |PDO_FT_CONCAT  <br/> |0x00000010  <br/> |这是一个 **"** 组合"类型的字段，其"组合公式域"对话框中具有"联接字段"和相互选择的任何文本 **片段选项**。  <br/> |
    |PDO_FT_SWITCH  <br/> |0x00000020  <br/> |此字段的类型为 **"组合** "，并且具有 **"仅** 显示第一个非空字段，忽略后续字段"选项，该选项在"组合公式 **域** "对话框中选中。  <br/> |
    |PDO_PRINT_SAVEAS_DEF  <br/> |0x00000040  <br/> |此标志不由Outlook，但包含用于所有用户定义的字段定义。  <br/> |
   
- VT：WORD (2 个) ，即数据类型字段的常量，它是 [VARENUM](https://msdn.microsoft.com/library/system.runtime.interopservices.varenum.aspx) 枚举中的一个常量。 
    
- DispId：DWORD (4 字节) ，即字段的调度标识符。 对于用户定义的字段，值为 0。
    
- NmidNameLength：WORD (2 字节) ，即 NmidName 数组中的元素数。
    
- NmidName：WCHAR 的数组。 对于用户定义的字段定义，这是字段名称的 Unicode (UTF-16) 表示形式。 此数组的计数等于 NmidNameLength。
    
- NameANSI： [一个 PackedAnsiString](packedansistring-stream-structure.md) 流结构。 这是字段名称的 ANSI 表示形式。 
    
- FormulaANSI：一个 PackedAnsiString 流结构。 这是字段的计算公式的 ANSI 表示形式。 它显示在绑定到此字段的窗体控件的"属性"对话框的"值"选项卡的"初始值"部分。  
    
- ValidationRuleANSI：一个 PackedAnsiString 流结构。 这是字段验证公式的 ANSI 表示形式。 它显示在绑定到此字段的窗体控件的"属性"对话框的"验证"选项卡上的"验证公式"文本框中。  
    
- ValidationTextANSI：一个 PackedAnsiString 流结构。 这是字段的验证失败文本的 ANSI 表示形式。 如果在绑定到此字段的窗体控件的"属性"对话框的"验证"选项卡上验证失败，则显示在"显示此消息"文本框中。  
    
- ErrorANSI：一个 PackedAnsiString 流结构。 Outlook此元素;您应将此元素设置为空字符串。
    
- InternalType：DWORD (4 字节) ，字段的内部类型。 此数据元素仅在字段定义格式为 PropDefV2 时存在。 内部类型是下列值之一，其中每个值对应于用户定义的字段的"新建字段"对话框中的类型。 
    
    |**内部类型名称**|**值**|**"新建 **字段"对话框中的相应** 类型**|
    |:-----|:-----|:-----|
    |iTypeString  <br/> |0  <br/> |**Text** <br/> |
    |iTypeNumber  <br/> |1  <br/> |**Number** <br/> |
    |iTypePercent  <br/> |2  <br/> |**Percent** <br/> |
    |货币  <br/> |3  <br/> |**Currency** <br/> |
    |iTypeBool  <br/> |4   <br/> |**是/否** <br/> |
    |iTypeDateTime  <br/> |5   <br/> |**日期/时间** <br/> |
    |iTypeDuration  <br/> |6   <br/> |**Duration** <br/> |
    |iTypeCombination  <br/> |7   <br/> |**组合**，与" **只显示第一个非空字段，忽略后续字段"** 选项一起在"组合公式域" **对话框中** 选中。  <br/> |
    |iTypeFormula  <br/> |8   <br/> |**公式** <br/> |
    |iTypeResult  <br/> |9   <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeVariant  <br/> |10    <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeFloatResult  <br/> |11  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeConcat  <br/> |12   <br/> |**组合**，"**合并域"和"** 组合公式域"对话框中选择相互选择的任何文本片段。  <br/> |
    |iTypeKeywords  <br/> |13  <br/> |**关键字** <br/> |
    |iTypeInteger  <br/> |14   <br/> |**Integer** <br/> |
   
- SkipBlocks：一系列 [SkipBlock](skipblock-stream-structure.md) 流结构。 此数据元素仅在字段定义格式为 PropDefV2 时存在。 如果字段定义格式为 PropDefV2，则系列应至少包含一个 SkipBlock 结构，Size 数据元素等于 0 的 SkipBlock 结构，并且系列应该以此 SkipBlock 结构开始和终止。 
    
   SkipBlock 结构的用途取决于其在 SkipBlocks 系列中的相对位置。 如果字段定义采用 PropDefV2 格式，并且第一个结构不是终止结构 (则 Size 数据元素大于 0) ，则 Outlook 假定第一个 SkipBlock 结构在 Unicode (UTF-16) 中指定字段名称。 
    
   > [!IMPORTANT]
   > 如果第一个 SkipBlock 是终止结构，则 NameANSI 数据元素用于确定字段名称。 如果该字符串包含任何非 ASCII 字符，则根据运行该字符串的计算机的 ANSI 代码页，这些字符Outlook不一致。 为了防止这种不一致，请确保始终在创建的字段定义中指定第一个 SkipBlock，至少当字段名称包含非 ASCII 字符时。 
  
   如果字段定义格式的未来版本在 FieldDefinition 流中引入其他数据片段，则此数据存储为 SkipBlocks 系列中其他 SkipBlock 流结构，然后再终止 Size 数据元素等于 0 的 SkipBlock 结构。 早期版本的 Outlook可以安全地忽略这些额外的 SkipBlock 结构（一至终止 SkipBlock 结构）并仍正确处理它们支持的所有块。
    
## <a name="see-also"></a>另请参阅

- [Outlook项目和字段](outlook-items-and-fields.md)
- [流结构](stream-structures.md)
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)

