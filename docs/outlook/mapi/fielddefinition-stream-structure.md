---
title: FieldDefinition 流结构
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 93acdbc8-381f-45d5-be6c-0cad066269fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a43d4f12aa28de29116d7d074b743d6c0d61d964
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594507"
---
# <a name="fielddefinition-stream-structure"></a>FieldDefinition 流结构

**适用于**：Outlook 2013 | Outlook 2016 
  
FieldDefinition 流结构包含用户定义的字段的字段定义或一组的内置字段的数据绑定设置。
  
如果该结构包含用户定义的字段的字段定义，您可以编程方式处理 FieldDefinition 流结构。 不应尝试以编程方式创建或修改 FieldDefinition 结构，如果该结构包含内置字段的设置。 应使用 Microsoft Outlook 窗体设计器来维护此类设置为内置字段。
  
> [!NOTE]
> Outlook 支持的字段定义的两种格式： PropDefV1 和 PropDefV2。 PropDefV1 格式的字段定义中包含以下数据元素： 标志、 VT、 DispId、 NmidNameLength、 NmidName、 NameANSI、 FormulaANSI、 ValidationRuleANSI、 ValidationTextANSI 和 ErrorANSI。 PropDefV2 格式都包含相同的元素和 InternalType 和 SkipBlocks 元素。 
>
> Outlook 不维护 PropDefV2 字段定义格式的 FormulaANSI、 ValidationRuleANSI 和 ValidationTextANSI 数据元素的 Unicode 版本。 如果这些元素包含非 ASCII 字符，这些字符可能会根据在其运行 Outlook 的计算机的 ANSI 代码页规章解释。 因此，您应使用都是这些数据元素的 ASCII 字符的字符串值。 
  
此流中的数据元素存储在-little-endian 字节的顺序，紧跟彼此下面指定的顺序。
  
- 标志： DWORD （4 个字节），其值和含义下表中列出的零个或多个标志的组合。
    
    |**代表标志名称**|**值**|**说明**|
    |:-----|:-----|:-----|
    |PDO_IS_CUSTOM  <br/> |0x00000001  <br/> |FieldDefinition 结构包含用户定义的字段的定义。  <br/> |
    |PDO_REQUIRED  <br/> |0x00000002  <br/> |对于窗体控件绑定到此字段，在**属性**对话框的**验证**选项卡中选中的**一个值，则需要此字段的**复选框。  <br/> |
    |PDO_PRINT_SAVEAS  <br/> |0x00000004  <br/> |对于窗体控件绑定到此字段中，对应的复选框**包含打印该字段和另存为**中的**属性**对话框的**验证**选项卡选择。  <br/> |
    |PDO_CALC_AUTO  <br/> |0x00000008  <br/> |对于窗体控件绑定到此字段，在**属性**对话框的**值**选项卡中选中**自动计算该公式**对应的复选框。  <br/> |
    |PDO_FT_CONCAT  <br/> |0x00000010  <br/> |这是类型**组合**的字段，它具有其**组合公式字段**对话框中所选中的**互相合并字段及与每个其他任何文本片段**选项。  <br/> |
    |PDO_FT_SWITCH  <br/> |0x00000020  <br/> |此字段的类型**组合**是具有**仅显示第一个非空字段，忽略后续字段**选项在并选择**合并公式字段**对话框。  <br/> |
    |PDO_PRINT_SAVEAS_DEF  <br/> |0x00000040  <br/> |此标志不使用 Outlook 中，但它并包含所有用户定义的字段定义。  <br/> |
   
- VT： 单词 （2 个字节） 的字段，即[VARENUM](http://msdn.microsoft.com/en-us/library/system.runtime.interopservices.varenum.aspx)枚举中的常量的数据类型。 
    
- DispId: DWORD （4 个字节），字段的调度标识符。 对于用户定义的字段，则值为 0。
    
- NmidNameLength： 单词 （2 个字节），NmidName 数组中的元素的数目。
    
- NmidName: WCHAR 数组。 有关用户定义的字段定义，这是字段名称的 Unicode (utf-16) 表示形式。 此数组的计数等于 NmidNameLength。
    
- NameANSI: [PackedAnsiString](packedansistring-stream-structure.md)流结构。 这是 ANSI 表示形式的字段名称。 
    
- FormulaANSI: PackedAnsiString stream 结构。 这是 ANSI 表示形式字段的计算公式。 它将显示在窗体控件绑定到该域的**属性**对话框的**值**选项卡的**初始值**部分。 
    
- ValidationRuleANSI: PackedAnsiString stream 结构。 这是该字段的验证公式 ANSI 表示形式。 它是窗体控件绑定到该域的**属性**对话框的**验证**选项卡上的**验证公式**显示在文本框中。 
    
- ValidationTextANSI: PackedAnsiString stream 结构。 这是 ANSI 文本的表示形式的字段验证失败。 它是窗体控件绑定到该域的**属性**对话框的**验证**选项卡上显示**此消息验证失败时**显示在文本框中。 
    
- ErrorANSI: PackedAnsiString stream 结构。 Outlook 不使用此元素;应将此元素设置为空字符串。
    
- InternalType: DWORD （4 个字节），内部域的类型。 仅当字段定义格式是 PropDefV2 存在此数据元素。 内部类型是每种对应于**新建域**对话框中的用户定义的字段类型的下列值之一。 
    
    |**内部类型名称**|**值**|**在**新建域**对话框中的相应类型**|
    |:-----|:-----|:-----|
    |iTypeString  <br/> |0  <br/> |**Text** <br/> |
    |iTypeNumber  <br/> |1  <br/> |**编号** <br/> |
    |iTypePercent  <br/> |2  <br/> |**Percent** <br/> |
    |货币  <br/> |3  <br/> |**Currency** <br/> |
    |iTypeBool  <br/> |4  <br/> |**Yes/No** <br/> |
    |iTypeDateTime  <br/> |5  <br/> |**日期/时间** <br/> |
    |iTypeDuration  <br/> |6  <br/> |**持续时间** <br/> |
    |iTypeCombination  <br/> |7  <br/> |**组合**，**组合公式字段**对话框中选择**仅显示第一个非空字段，忽略后续字段**选项。  <br/> |
    |iTypeFormula  <br/> |8  <br/> |**Formula** <br/> |
    |iTypeResult  <br/> |9  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeVariant  <br/> |10  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeFloatResult  <br/> |11  <br/> |此类型不用于用户定义的字段。  <br/> |
    |iTypeConcat  <br/> |12  <br/> |**组合**，在**组合公式字段**对话框中选择了**互相合并字段及与每个其他任何文本片段**选项。  <br/> |
    |iTypeKeywords  <br/> |13  <br/> |**关键字** <br/> |
    |iTypeInteger  <br/> |14  <br/> |**Integer** <br/> |
   
- SkipBlocks： 一个或多个[SkipBlock](skipblock-stream-structure.md)流结构的一系列。 仅当字段定义格式是 PropDefV2 存在此数据元素。 如果字段定义格式，PropDefV2 系列应包含至少一个 SkipBlock 结构，它等于 0，大小数据元素的 SkipBlock 结构和系列应开始与此 SkipBlock 结构终止。 
    
   SkipBlock 结构的目的取决于它 SkipBlocks 系列中的相对位置。 如果字段定义为 PropDefV2 格式，并且的第一个结构不是终止结构 （大小 data 元素为大于 0），Outlook 将假定的第一个 SkipBlock 结构 Unicode (utf-16) 中指定的字段名称。 
    
   > [!IMPORTANT]
   > 如果第一个 SkipBlock，终止结构 NameANSI data 元素用于确定的字段名称。 如果该字符串包含任何非 ASCII 字符，这些字符可能会根据在其上运行 Outlook 的计算机的 ANSI 代码页规章解释。 若要防止此类不一致，请确保您始终在您创建的字段定义中指定第一个 SkipBlock，至少时的字段名称包含非 ASCII 字符。 
  
   如果字段定义格式的未来版本介绍 FieldDefinition 流中的数据的其他部分，可以将此数据存储为之前已终止 SkipBlock 结构 SkipBlocks 系列中的其他 SkipBlock 流结构等于 0 的大小数据元素。 Outlook 的早期版本可以放心地忽略这些额外的 SkipBlock 结构最多为终止 SkipBlock 结构和仍正确处理它们支持的所有块。
    
## <a name="see-also"></a>另请参阅

- [Outlook 项和字段](outlook-items-and-fields.md)
- [流结构](stream-structures.md)
- [PropertyDefinition 流结构](propertydefinition-stream-structure.md)

