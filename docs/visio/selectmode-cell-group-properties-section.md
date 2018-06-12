---
title: SelectMode 单元格（“Group Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm875
localization_priority: Normal
ms.assetid: 5ba68e05-f394-d7b7-390d-f0a9fdad011e
description: 确定如何选择组合形状及其组成部分。
ms.openlocfilehash: 426b4a18bbd54887e4f60b92860a6c3846386671
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781232"
---
# <a name="selectmode-cell-group-properties-section"></a>SelectMode 单元格（“Group Properties”内容）

确定如何选择组合形状及其组成部分。
  
|**值**|**选择模式**|**自动化常量**|
|:-----|:-----|:-----|
|0  <br/> |仅选择组合形状。  <br/> |**visGrpSelModeGroupOnly** <br/> |
|1  <br/> |首先选择组合形状。  <br/> |**visGrpSelModeGroup1st** <br/> |
|2  <br/> |首先选择组合的组成部分。  <br/> |**visGrpSelModeMembers1st** <br/> |
   
## <a name="remarks"></a>备注

您还可以在**行为**对话框来设置此值 （组选定形状，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡的**形状设计**组中，单击**行为**，，然后单击**组下的**选择**列表中的模式行为**)。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 SelectMode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |SelectMode  <br/> |
   
若要从某个程序按索引获取对 SelectMode 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowGroup** <br/> |
|单元格索引：  <br/> |**visGroupSelectMode** <br/> |
   

