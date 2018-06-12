---
title: XGridOrigin 单元格 (标尺&amp;网格部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1155
localization_priority: Normal
ms.assetid: 2b1a8902-b1d4-c3d9-8c9f-1a28fddacc59
description: 指定网格原点的水平坐标。
ms.openlocfilehash: 0cc6ff10f9bb4ba7ee0a13a48cb55b7dcd0fa013
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781691"
---
# <a name="xgridorigin-cell-ruler-amp-grid-section"></a>XGridOrigin 单元格 (标尺&amp;网格部分)

指定网格原点的水平坐标。
  
## <a name="remarks"></a>注解

此单元格对应于水平**网格原点**选项中**标尺&amp;网格**对话框 （在**视图**选项卡上，单击**显示**箭头。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 XGridOrigin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |XGridOrigin  <br/> |
   
若要从某个程序按索引获取对 XGridOrigin 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowRulerGrid** <br/> |
|单元格索引：  <br/> |**visXGridOrigin** <br/> |
   

