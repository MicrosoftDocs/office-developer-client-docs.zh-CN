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
description: 表示控制手柄的锚点在本地坐标系中的 x 坐标。
ms.openlocfilehash: 7aef1fe779ae9b862e88eccf0112eb8696377858
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322300"
---
# <a name="x-dynamics-cell-controls-section"></a>X Dynamics 单元格（“Controls”内容）

表示控制手柄的锚点在本地坐标系中的*x*坐标。 
  
## <a name="remarks"></a>注解

锚点用于动态过程中类似橡皮筋的固定点。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Dynamics 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 措施.  *名称*。XDynwhere 控件。  *名称*是控件行的名称。  <br/> |
   
要从某个程序按索引获取对 X Dynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCtlXDyn** <br/> |
   

