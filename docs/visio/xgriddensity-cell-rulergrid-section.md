---
title: XGridDensity 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1150
localization_priority: Normal
ms.assetid: db7b353f-4379-8865-1c35-36b89cf93257
description: 指定要使用的水平网格的类型。
ms.openlocfilehash: 107cde8e8b0d630a4dc4b43127412de2f6b0115d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781686"
---
# <a name="xgriddensity-cell-ruler-amp-grid-section"></a>XGridDensity 单元格 (标尺&amp;网格部分)

指定要使用的水平网格的类型。
  
|**值**|**说明**|**自动化常量**|
|:-----|:-----|:-----|
|0  <br/> |固定  <br/> |**visGridFixed** <br/> |
|2  <br/> |粗糙  <br/> |**visGridCoarse** <br/> |
|4  <br/> |标准（默认）  <br/> |**visGridNormal** <br/> |
|8  <br/> |精细  <br/> |**visGridFine** <br/> |
   
## <a name="remarks"></a>备注

此单元格对应于水平**网格间距**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XGridDensity 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XGridDensity  <br/> |
   
若要从某个程序按索引获取对 XGridDensity 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXGridDensity** <br/> |
   

