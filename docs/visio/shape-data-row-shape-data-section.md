---
title: Shape Data 行（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251344
localization_priority: Normal
ms.assetid: f3a83496-fccc-9d6a-02b9-60ebaf4911ea
description: 包含与形状相关联的单个形状数据项的信息。对于每个形状数据项，形状中都包含一个与之对应的 Shape Data 行。Shape Data 行被命名为 Prop.name 且包含以下单元格。有关详细信息，请参阅特定的单元格主题。
ms.openlocfilehash: 058f8f180a2eca4736d06dfcc533d81f45150c86
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415395"
---
# <a name="shape-data-row-shape-data-section"></a>Shape Data 行（“Shape Data”内容）

包含与形状相关联的单个形状数据项的信息。对于每个形状数据项，形状中都包含一个与之对应的 Shape Data 行。Shape Data 行被命名为 Prop.name 且包含以下单元格。有关详细信息，请参阅特定的单元格主题。
  
|**Cell**|**说明**|
|:-----|:-----|
|[Label](label-cell-shape-data-section.md) <br/> |指定在 **“形状数据”** 对话框或窗口中为用户显示的标签。  <br/> |
|[Prompt](prompt-cell-shape-data-section.md) <br/> |指定说明性文本或指导性文本，这些文本将在用户选择该项后在 **“形状数据”** 对话框或窗口中显示。  <br/> |
|[类型](type-cell-shape-data-section.md) <br/> |指定形状数据项值的数据类型：字符串 (0)、固定列表 (1)、数字 (2)、布尔值 (3)、可变列表 (4)、日期或时间 (5)、持续时间 (6) 或货币 (7)。  <br/> |
|[Format](format-cell-shape-data-section.md) <br/> |指定形状数据项的格式。  <br/> |
|[值](value-cell-shape-data-section.md) <br/> |包含在 **“形状数据”** 对话框或窗口中输入的项的值。  <br/> |
|[SortKey](sortkey-cell-shape-data-section.md) <br/> |指定一个键，**“形状数据”** 对话框或窗口中的项将依据此键列出。  <br/> |
|[不可见](invisible-cell-shape-data-section.md) <br/> |指定形状数据项在 **“形状数据”** 对话框或窗口中是否可见。TRUE = 不可见；FALSE = 可见。<br/> |
|[Ask](ask-cell-shape-data-section.md) <br/> |确定在创建实例或者重复或复制形状时，是否就输入该形状的形状数据信息问题询问用户。  <br/> |
|[LangID](langid-cell-shape-data-section.md) <br/> |指定显示形状数据项值所使用的语言。  <br/> |
|[Calendar](calendar-cell-miscellaneous-section.md) <br/> |指定当形状数据项的类型为“Date”时，使用的日历的类型。  <br/> |
   
## <a name="remarks"></a>备注

 您可以添加多个 Prop。  *命名*  行（如需要）为行指定有意义的名称，并设置单元格值。 若要向现有的“Shape Data”内容添加形状数据项，请右击某一行，然后单击快捷菜单上的 **“插入行”**。 
  
可以通过上述单元格的行名称来引用这些单元格，这些行名称在 ShapeSheet 窗口中显示为红色文本。 若要为 Prop. *name*  行分配有意义的名称，请单击该行，然后键入一个名称（例如  *Price）*  以创建行名称 Prop.Price。 然后，可以使用 Prop.Price.Label 引用 Label 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

