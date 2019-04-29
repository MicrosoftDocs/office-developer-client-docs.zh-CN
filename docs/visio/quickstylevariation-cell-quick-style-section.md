---
title: QuickStyleVariation 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是否使用与图表背景对比的颜色来替代文本、线条和填充颜色的公式和值 (或这些属性的组合)。 值为0、1、2、4和8的按位 "或"。
ms.openlocfilehash: 736e2287c00c24774ef8b677613235d642697f4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433792"
---
# <a name="quickstylevariation-cell-quick-style-section"></a>QuickStyleVariation 单元格 ("快速样式" 部分)

确定是否使用与图表背景对比的颜色来替代文本、线条和填充颜色的公式和值 (或这些属性的组合)。 值为0、1、2、4和8的按位 "或"。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |请勿改变形状的文本、线条或填充颜色 (或这些属性的任何组合), 使其对给定的背景色保持可见。  <br/> |
|1  <br/> |请勿改变形状的文本、线条或填充颜色 (或这些属性的任何组合), 使其对给定的背景色保持可见。  <br/> |
|双面  <br/> |如有必要, 请更改形状的文本颜色, 使其对特定主题的背景色保持可见。  <br/> |
|4  <br/> |如有必要, 请改变形状的线条颜色, 以使其对特定主题的背景色保持可见。  <br/> |
|utf-8  <br/> |如有必要, 请更改形状的填充颜色, 以使其对特定主题的背景色保持可见。  <br/> |
   
## <a name="remarks"></a>说明

当文本或行位于任何可见的形状几何图形之外时 (例如, 在其 textbox 位于形状底部下方的形状中, 例如网络图中的形状), 使用 QuickStyleVariation 单元格保证可见性。 单元格的默认值为 0, 表示其行为处于非活动状态。 任何其他值将触发单元格的行为。
  
QuickStyleVariation 值将覆盖 THEMEVAL 函数驻留在 Color (Character)、FillForegnd 或 LineColor 单元格 (或通过直接引用通过 THEMEVAL 的这三个属性生成) 生成的值 ("CharacterColor ")、THEMEVAL (" FillColor ") 和 THEMEVAL (" LineColor "))。
  
若要从另一个公式按名称获取对**QuickStyleVariation**单元格的引用, 通过获取**cell**元素的**N**属性的值, 或使用**CellsU**属性从某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |QuickStyleVariation  <br/> |
   
若要从某个程序按索引获取对**QuickStyleVariation**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
|单元格索引：  <br/> |**visQuickStyleVariation** <br/> |
   

