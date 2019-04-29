---
title: Label 单元格（“形状数据”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm510
localization_priority: Normal
ms.assetid: 6d328b1c-8d92-eb1a-7317-7dd85c674ff9
description: 指定在“形状数据”窗口中向用户显示的标签。 标签由字母数字字符组成，包括下划线 (_) 字符。
ms.openlocfilehash: d341acfbd47446a5b6dbee51ed821d1e1f34e15d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420176"
---
# <a name="label-cell-shape-data-section"></a>Label 单元格（“形状数据”内容）

指定在 **“形状数据”** 窗口中向用户显示的标签。 标签由字母数字字符组成，包括下划线 (_) 字符。 
  
## <a name="remarks"></a>说明

该应用程序会自动将标签字符串用引号引起来放在单元格中，但引号并不显示在 **“形状数据”** 窗口中。 
  
如果没有找到标签文本，Visio 将在 **“形状数据”** 窗口中显示行名称 (Prop.Row)。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Label 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |片.*名称*。标签 where。 *名称*是行名称  <br/> |
   
若要从某个程序按索引获取对 Label 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionProp** <br/> |
|行索引：  <br/> |**visRowProp** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCustPropsLabel** <br/> |
   

