---
title: Y Dynamics 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251284
localization_priority: Normal
ms.assetid: cb221974-2f1a-edb0-477b-39a3c4a64c56
description: 代表 y-控制手柄的锚点在本地坐标系中的坐标。 锚点用于动态过程中类似橡皮筋的固定点。
ms.openlocfilehash: 162f062d382f3f303ae39db725f3fbfa0790bfc4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781733"
---
# <a name="y-dynamics-cell-controls-section"></a>Y Dynamics 单元格（“Controls”内容）

代表*y* -控制手柄的锚点在本地坐标系中的坐标。 锚点用于动态过程中类似橡皮筋的固定点。 
  
## <a name="remarks"></a>备注

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Y Dynamics 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 控件。  *名称*。YDynwhere 控件。  *name*是控制行的名称。  <br/> |
   
若要从某个程序按索引获取对 Y Dynamics 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCtlYDyn** <br/> |
   

