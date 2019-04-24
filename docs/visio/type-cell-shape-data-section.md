---
title: Type 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1055
localization_priority: Normal
ms.assetid: 1e24a906-83ce-32d2-5d7b-ba6dd6eea2d3
description: 指定形状数据值的数据类型。
ms.openlocfilehash: c2d38b521a8597a4582a4145ad808b0c0e26ff0a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350895"
---
# <a name="type-cell-shape-data-section"></a>Type 单元格（“Shape Data”内容）

指定形状数据值的数据类型。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |字符串。此为默认值。  <br/> |**visPropTypeString** <br/> |
|1  <br/> |固定列表。在 **“定义形状数据”** 对话框中的下拉组合框中显示列表项。在 Format 单元格中指定列表项。用户只能从该列表中选择一项。<br/> |**visPropTypeListFix** <br/> |
|双面  <br/> |数字。包括日期、时间、持续时间和货币值，以及标量、尺寸和角度。在 Format 单元格中指定格式图片。  <br/> |**visPropTypeNumber** <br/> |
|第三章  <br/> |布尔值。显示 FALSE 和 TRUE 项，这两项正是用户可以从 **“定义形状数据”** 对话框中的下拉列表框中选择的项。<br/> |**visPropTypeBool** <br/> |
|4  <br/> |变量列表。在 **“定义形状数据”** 对话框中的下拉组合框中显示列表项。在 Format 单元格中指定列表项。用户可以选择列表项或在 Format 单元格中输入添加到当前列表中的新项。<br/> |**visPropTypeListVar** <br/> |
|5  <br/> |日期或时间值。显示日、月和年，或者秒、分钟和小时，或者日期和时间的组合值。在 Format 单元格中指定格式图片。  <br/> |**visPropTypeDate** <br/> |
|型  <br/> |持续时间值。显示已经过去的时间。在 Format 单元格中指定格式图片。  <br/> |**visPropTypeDuration** <br/> |
|步  <br/> |货币值。使用系统的当前“区域设置”。在 Format 单元格中指定格式图片。  <br/> |**visPropTypeCurrency** <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Type 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |片.*名称*。键入 where。 *名称*是行名称  <br/> |
   
若要从某个程序按索引获取对 Type 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionProp** <br/> |
|行索引：  <br/> |**visRowProp** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCustPropsType** <br/> |
   

