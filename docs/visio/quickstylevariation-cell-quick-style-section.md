---
title: 'QuickStyleVariation Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是替代文本、线条和填充颜色的公式和值 (还是使用与图表背景) 来替代这些属性的组合。 值是 0、1、2、4 和 8 的位 OR。
ms.openlocfilehash: 736e2287c00c24774ef8b677613235d642697f4b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433792"
---
# <a name="quickstylevariation-cell-quick-style-section"></a>QuickStyleVariation Cell (Quick Style Section) 

确定是替代文本、线条和填充颜色的公式和值 (还是使用与图表背景) 来替代这些属性的组合。 值是 0、1、2、4 和 8 的位 OR。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |不要更改形状的文本、线条或填充颜色 (或这些属性的任意组合) 主题的给定背景色保持可见。  <br/> |
|1  <br/> |不要更改形状的文本、线条或填充颜色 (或这些属性的任意组合) 主题的给定背景色保持可见。  <br/> |
|2  <br/> |如有必要，请更改形状的文本颜色，以根据主题的给定背景色保持可见。  <br/> |
|4   <br/> |如有必要，请更改形状的线条颜色，以便对主题的给定背景色保持可见。  <br/> |
|8   <br/> |如有必要，请更改形状的填充颜色，以便根据主题的给定背景色保持可见。  <br/> |
   
## <a name="remarks"></a>备注

使用 QuickStyleVariation 单元格可保证文本或线条在任何可见形状几何图形 (例如，文本框位于形状底部下面的形状（如网络图) 中）的可见性。 单元格的默认值为 0，表示其行为处于非活动状态。 任何其他值将触发单元格的行为。
  
QuickStyleVariation 值替代 THEMEVAL 函数生成的值，该值位于 Color (Character Section) 、FillForegnd 或 LineColor 单元格 (中，或者由 THEMEVAL ("CharacterColor") 、THEMEVAL ("FillColor") 和 THEMEVAL ("LineColor") ) 直接引用生成的值。
  
若要从另一个公式、通过获取 **Cell** 元素 **的 N** 属性值或使用 CellsU 属性从某个程序按名称获取对 **QuickStyleVariation** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |QuickStyleVariation  <br/> |
   
若要从程序按索引获取对 **QuickStyleVariation** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
|单元格索引：  <br/> |**visQuickStyleVariation** <br/> |
   

