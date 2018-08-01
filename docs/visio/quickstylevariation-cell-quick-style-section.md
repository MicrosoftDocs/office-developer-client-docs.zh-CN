---
title: QuickStyleVariation 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e3b58a19-9f1a-4f2b-9fe2-45cbb7ec6898
description: 确定是否覆盖的公式和的文本、 行和填充颜色 （或这些属性的组合） 通过使用颜色的值与图背景的对比度。 值为 0、 1、 2、 4、 8 的按位 OR。
ms.openlocfilehash: fe6462798b61a0713f98196974876144cf4606e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781009"
---
# <a name="quickstylevariation-cell-quick-style-section"></a>QuickStyleVariation 单元格（“Quick Style”部分）

确定是否覆盖的公式和的文本、 行和填充颜色 （或这些属性的组合） 通过使用颜色的值与图背景的对比度。 值为 0、 1、 2、 4、 8 的按位 OR。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |不要更改形状的文本、 线条或填充颜色 （或这些属性的任意组合） 保持可见针对主题的给定的背景色。  <br/> |
|1  <br/> |不要更改形状的文本、 线条或填充颜色 （或这些属性的任意组合） 保持可见针对主题的给定的背景色。  <br/> |
|2  <br/> |如有必要，仍可见主题的针对给定的背景颜色更改形状的文本颜色。  <br/> |
|4  <br/> |如有必要，仍可见主题的针对给定的背景颜色更改形状的线条颜色。  <br/> |
|8  <br/> |如有必要，仍可见主题的针对给定的背景颜色更改形状的填充颜色。  <br/> |
   
## <a name="remarks"></a>说明

使用 QuickStyleVariation 单元格时 （例如，在其 textbox 是该形状，例如网络图表中的底形状） 的任何可见的形状几何图形外部保证文本或行中的可见性。 单元格的默认值为 0，表示其行为处于非活动状态。 任何其他值触发单元格的行为。
  
QuickStyleVariation 值将覆盖它驻留在颜色 （Character 内容）、 FillForegnd 或 LineColor 单元格时产生的 THEMEVAL 函数的值 (或通过 THEMEVAL 产生直接引用这三个属性 ("CharacterColor")，THEMEVAL("FillColor") 和 THEMEVAL("LineColor"))。
  
要获取的**单元格**元素中，或从某个程序**N**属性的值使用**CellsU**属性获取按名称从另一个公式， **QuickStyleVariation**单元格的引用，使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |QuickStyleVariation  <br/> |
   
若要从某个程序按索引获取对**QuickStyleVariation**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
|单元格索引：  <br/> |**visQuickStyleVariation** <br/> |
   

