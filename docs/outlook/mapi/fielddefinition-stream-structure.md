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
  
FieldDefinition 流结构包含用户定义字段的字段定义, 或内置字段的一组数据绑定设置。
  
如果结构包含用户定义字段的字段定义, 则可以以编程方式操作 FieldDefinition 流结构。 如果结构包含内置域的设置, 则不应尝试以编程方式创建或修改 FieldDefinition 结构。 应使用 Microsoft Outlook 窗体设计器来维护内置字段的此类设置。
  
> [!NOTE]
> Outlook 支持两种格式的字段定义: PropDefV1 和 PropDefV2。 字段定义的 PropDefV1 格式包含以下数据元素: Flags、VT、DispId、NmidNameLength、NmidName、NameANSI、FormulaANSI、ValidationRuleANSI、ValidationTextANSI 和 ErrorANSI。 PropDefV2 格式包含相同的元素以及 InternalType 和 SkipBlocks 元素。 
>
> Outlook 不会在 PropDefV2 字段定义格式中维护 FormulaANSI、ValidationRuleANSI 和 ValidationTextANSI 数据元素的 Unicode 版本。 如果这些元素包含非 ASCII 字符, 则根据运行 Outlook 的计算机的 ANSI 代码页, 这些字符的解释可能不一致。 因此, 对于这些数据元素, 应仅使用完全由 ASCII 字符组成的字符串值。 
  
此流中的数据元素存储在小端字节序的字节顺序中, 紧跟在下面指定的顺序依次后续。
  
- Flags: DWORD (4 个字节), 是下表中列出的值和含义的零个或多个标志的组合。
    
    |**标记名称**|**Value**|**说明**|
    |:-----|:-----|:-----|
    |PDO_IS_CUSTOM  <br/> |0x00000001  <br/> |FieldDefinition 结构包含用户定义的字段的定义。  <br/> |
    |PDO_REQUIRED  <br/> |0x00000002  <br/> |对于绑定到此字段的窗体控件, 在 "**属性**" 对话框的 "**验证**" 选项卡上选择了 "**此字段必须具有值**的复选框" 复选框。  <br/> |
    |PDO_PRINT_SAVEAS  <br/> |0x00000004  <br/> |对于绑定到此字段的窗体控件, 在 "**属性**" 对话框的 "**验证**" 选项卡中选中 "将**此字段包含在 ' 打印 ' 和 ' 另存为**' 的" 复选框。  <br/> |
    |PDO_CALC_AUTO  <br/> |0x00000008  <br/> |对于绑定到此字段的窗体控件, 将在 "**属性**" 对话框的 "**值**" 选项卡中选择 "**自动计算此公式**" 复选框。  <br/> |
    |PDO_FT_CONCAT  <br/> |0x00000010  <br/> |这是**组合**类型的字段, 它的**联接字段和任何文本片段**在其 "**组合公式字段**" 对话框中选择了每个其他选项。  <br/> |
    |PDO_FT_SWITCH  <br/> |0x00000020  <br/> |此字段的类型为**组合**, 并具有**仅显示第一个非空字段,** 并且将忽略在 "**组合公式字段**" 对话框中选择的后续选项。  <br/> |
    |PDO_PRINT_SAVEAS_DEF  <br/> |0x00000040  <br/> |Outlook 不使用此标志, 但它包含在所有用户定义的字段定义中。  <br/> |
   
- VT: WORD (2 个字节), 字段的数据类型, 这是[VARENUM](https://msdn.microsoft.com/library/system.runtime.interopservices.varenum.aspx)枚举中的常量。 
    
- DispId: DWORD (4 个字节), 字段的调度标识符。 对于用户定义的字段, 该值为0。
    
- NmidNameLength: WORD (2 个字节), NmidName 数组中的元素数。
    
- NmidName: WCHAR 的数组。 对于用户定义的字段定义, 这是字段名称的 Unicode (UTF-16) 表示形式。 此数组的计数等于 NmidNameLength。
    
- NameANSI: [PackedAnsiString](packedansistring-stream-structure.md)流结构。 这是字段名称的 ANSI 表示形式。 
    
- FormulaANSI: PackedAnsiString 流结构。 这是域的计算公式的 ANSI 表示形式。 它显示在绑定到此字段的窗体控件的 "**属性**" 对话框的 "**值**" 选项卡的 "**初始值**" 部分中。 
    
- ValidationRuleANSI: PackedAnsiString 流结构。 这是域的验证公式的 ANSI 表示形式。 它显示在绑定到此字段的窗体控件的 "**属性**" 对话框的 "**验证**" 选项卡上的 "**验证公式**" 文本框中。 
    
- ValidationTextANSI: PackedAnsiString 流结构。 这是域的验证失败文本的 ANSI 表示形式。 如果在绑定到此字段的窗体控件的 "**属性**" 对话框的 "**验证**" 选项卡上验证失败, 则该示例将显示在 "**显示此消息**的文本" 框中。 
    
- ErrorANSI: PackedAnsiString 流结构。 Outlook 不使用此元素;应将此元素设置为空字符串。
    
- InternalType: DWORD (4 个字节), 字段的内部类型。 仅当字段定义格式为 PropDefV2 时, 才会显示此数据元素。 内部类型是下列值之一, 其中每个值对应于用户定义的字段的 "**新建字段**" 对话框中的一个类型。 
    
    |**内部类型名称**|**值**|**"**新域**中对应的类型" 对话框**|
    |:-----|:-----|:-----|
    |iTypeString  <br/> |0  <br/> |**Text** <br/> |
    |iTypeNumber  <br/> |1  <br/> |**Number** <br/> |
    |iTypePercent  <br/> |双面  <br/> |**Percent** <br/> |
    |货币  <br/> |第三章  <br/> |**Currency** <br/> |
    |iTypeBool  <br/> |4  <br/> |**是/否** <br/> |
    |iTypeDateTime  <br/> |5  <br/> |**日期/时间** <br/> |
    |iTypeDuration  <br/> |型  <br/> |**Duration** <br/> |
    |iTypeCombination  <br/> |步  <br/> |**组合**, 并**显示仅显示第一个非空字段, 并忽略**"**组合公式字段**" 对话框中的后续选择的选项。  <br/> |
    |iTypeFormula  <br/> |utf-8  <br/> |**Formula** <br/> |
    |iTypeResult  <br/> |第  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeVariant  <br/> |10  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeFloatResult  <br/> |11x17  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeConcat  <br/> |12  <br/> |**组合**, 并在 "**合并公式域**" 对话框中选中**与每个其他选项一起使用的 "联接字段和任何文本片段**"。  <br/> |
    |iTypeKeywords  <br/> |13  <br/> |**关键字** <br/> |
    |iTypeInteger  <br/> |日  <br/> |**Integer** <br/> |
   
- SkipBlocks: 一个或多个[SkipBlock](skipblock-stream-structure.md)流结构的系列。 仅当字段定义格式为 PropDefV2 时, 才会显示此数据元素。 如果字段定义格式为 PropDefV2, 则该系列应至少包含一个 SkipBlock 结构, 该结构的 Size data 元素等于 0, 并且该系列应在此 SkipBlock 结构中开始和终止。 
    
   SkipBlock 结构的用途取决于其在 SkipBlocks 系列中的相对位置。 如果字段定义的格式为 PropDefV2, 并且第一个结构不是终止结构 (Size data 元素大于 0), Outlook 将假定第一个 SkipBlock 结构指定 Unicode (utf-16) 中的字段名称。 
    
   > [!IMPORTANT]
   > 如果第一个 SkipBlock 是终止结构, 则使用 NameANSI 数据元素来确定字段名称。 如果该字符串包含任何非 ASCII 字符, 则根据运行 Outlook 的计算机的 ANSI 代码页, 这些字符的解释可能不一致。 若要防止这样的不一致, 请确保始终在您创建的字段定义中指定第一个 SkipBlock, 至少在字段名称中包含非 ASCII 字符时指定。 
  
   如果字段定义格式的未来版本在 FieldDefinition 流中引入了其他数据片段, 则可以将此数据作为其他 SkipBlock 流结构存储在 SkipBlocks 系列中, 在终止 SkipBlock 结构之前, 该Size data 元素等于0。 早期版本的 Outlook 可以安全地忽略对终止 SkipBlock 结构的这些额外的 SkipBlock 结构, 并且仍能正确处理它们支持的所有块。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项目和字段](outlook-items-and-fields.md)
- [流结构](stream-structures.md)
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)

