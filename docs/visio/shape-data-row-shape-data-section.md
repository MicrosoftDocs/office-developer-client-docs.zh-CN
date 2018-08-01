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
ms.openlocfilehash: 7bf7eafd1869aa3c3ee03efbde30560cdaaeb302
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781244"
---
# <a name="shape-data-row-shape-data-section"></a>Shape Data 行（“Shape Data”部分）

包含与形状相关联的单个形状数据项的信息。对于每个形状数据项，形状中都包含一个与之对应的 Shape Data 行。Shape Data 行被命名为 Prop.name 且包含以下单元格。有关详细信息，请参阅特定的单元格主题。
  
|**Cell**|**说明**|
|:-----|:-----|
|[标签](label-cell-shape-data-section.md) <br/> |指定在 **“形状数据”** 对话框或窗口中为用户显示的标签。  <br/> |
|[Prompt](prompt-cell-shape-data-section.md) <br/> |指定说明性文本或指导性文本，这些文本将在用户选择该项后在 **“形状数据”** 对话框或窗口中显示。  <br/> |
|[类型](type-cell-shape-data-section.md) <br/> |指定形状数据项值的数据类型：字符串 (0)、固定列表 (1)、数字 (2)、布尔值 (3)、可变列表 (4)、日期或时间 (5)、持续时间 (6) 或货币 (7)。  <br/> |
|[Format](format-cell-shape-data-section.md) <br/> |指定形状数据项的格式。  <br/> |
|[值](value-cell-shape-data-section.md) <br/> |包含在 **“形状数据”** 对话框或窗口中输入的项的值。  <br/> |
|[SortKey](sortkey-cell-shape-data-section.md) <br/> |指定一个键，**“形状数据”** 对话框或窗口中的项将依据此键列出。  <br/> |
|[不可见](invisible-cell-shape-data-section.md) <br/> |指定形状数据项在 **“形状数据”** 对话框或窗口中是否可见。TRUE = 不可见；FALSE = 可见。<br/> |
|[提出](ask-cell-shape-data-section.md) <br/> |确定在创建实例或者重复或复制形状时，是否就输入该形状的形状数据信息问题询问用户。  <br/> |
|[LangID](langid-cell-shape-data-section.md) <br/> |指定显示形状数据项值所使用的语言。  <br/> |
|[日历](calendar-cell-miscellaneous-section.md) <br/> |指定当形状数据项的类型为“Date”时，使用的日历的类型。  <br/> |
   
## <a name="remarks"></a>注解

 您可以添加任意多个属性。 *名称*行根据需要为这些行中，指定有意义的名称，并设置单元格的值。 将形状数据项添加到现有的形状数据部分，右键单击某一行，然后单击快捷菜单上的**插入行**。 
  
可通过，这些行名称在 ShapeSheet 窗口中显示为红色文本来引用这些单元格。 分配给属性的有意义的名称。*名称*行中，单击该行，，然后键入名称，例如*价格*，例如，创建行名称 Prop.Price。 然后，您可以通过使用 Prop.Price.Label 引用 Label 单元格。 
  
您输入的行名称在该内容中必须是唯一的。
  

