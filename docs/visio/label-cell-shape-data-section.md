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
description: 指定用户在形状数据窗口中显示的标签。 标签由字母数字字符，包括下划线 (_) 字符组成。
ms.openlocfilehash: 087bcb87a9e47131e6dbcd2d8df5c5da8a06894b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780503"
---
# <a name="label-cell-shape-data-section"></a>Label 单元格（“形状数据”内容）

指定用户在**形状数据**窗口中显示的标签。 标签由字母数字字符，包括下划线 (_) 字符组成。 
  
## <a name="remarks"></a>备注

应用程序会自动将标签字符串用引号将在单元格中，但引号并不会显示在**形状数据**窗口。 
  
如果找到无标签文本，则 Visio 将在**形状数据**窗口中显示行名称 (Prop.Row)。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Label 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |属性。*名称*。标签其中属性。 *Name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Label 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionProp** <br/> |
|行索引：  <br/> |**visRowProp** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCustPropsLabel** <br/> |
   

