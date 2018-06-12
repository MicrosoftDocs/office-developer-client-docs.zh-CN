---
title: X Dynamics 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1145
localization_priority: Normal
ms.assetid: 9757dfb4-6d37-0517-17fe-7593ff12bbfe
description: 代表 x 的控制手柄的锚点在本地坐标系中的坐标。
ms.openlocfilehash: 9dee2381c15ed2817df9f89ebc830cf31bf64c1f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781703"
---
# <a name="x-dynamics-cell-controls-section"></a>X Dynamics 单元格（“Controls”内容）

代表*x*的控制手柄的锚点在本地坐标系中的坐标。 
  
## <a name="remarks"></a>注释

锚点用于动态过程中类似橡皮筋的固定点。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 X Dynamics 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 控件。  *名称*。XDynwhere 控件。  *name*是控制行的名称。  <br/> |
   
若要从某个程序按索引获取对 X Dynamics 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCtlXDyn** <br/> |
   

