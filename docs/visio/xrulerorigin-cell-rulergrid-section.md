---
title: XRulerOrigin 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1170
localization_priority: Normal
ms.assetid: 328f8ab5-217f-0336-0d56-611eff509fe8
description: 指定页面 x 轴标尺上的零点。
ms.openlocfilehash: 78fab70c8489ddcdfe450ef9f9fd88b6c5040211
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781692"
---
# <a name="xrulerorigin-cell-ruler-amp-grid-section"></a>XRulerOrigin 单元格 (标尺&amp;网格部分)

指定页面 x 轴标尺上的零点。
  
## <a name="remarks"></a>备注

此单元格对应于中的水平**标尺零点**选项**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头）。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XRulerOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XRulerOrigin  <br/> |
   
若要从某个程序按索引获取对 XRulerOrigin 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXRulerOrigin** <br/> |
   

