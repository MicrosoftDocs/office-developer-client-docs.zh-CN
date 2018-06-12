---
title: X Behavior 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251285
localization_priority: Normal
ms.assetid: 82423d08-b6ce-0f23-8b61-354c3e5f323e
description: 控制的行为 x 的类型的控制手柄的坐标在手柄移动后将表现。
ms.openlocfilehash: 004ad407941aa15cec3ae94188f590ec6513c4da
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781671"
---
# <a name="x-behavior-cell-controls-section"></a>X Behavior 单元格（“Controls”内容）

控制的行为*x*的类型的控制手柄的坐标在手柄移动后将表现。 
  
|**值**|**行为**|**定义**|**自动化常量**|
|:-----|:-----|:-----|:-----|
| 0  <br/> | 成比例  <br/> | 控制手柄可以移动，在伸展时它也随形状按比例移动。  <br/> |**visCtlProportional** <br/> |
| 1  <br/> | 比例锁定  <br/> | 控制手柄可按比例与形状一起移动，但控制手柄本身不能移动。  <br/> |**visCtlLocked** <br/> |
| 2  <br/> | 左侧偏移  <br/> | 控制手柄与形状左侧偏移固定距离。  <br/> |**visCtlOffsetMin** <br/> |
| 3  <br/> | 中心偏移  <br/> | 控制手柄与形状中心偏移固定距离。  <br/> |**visCtlOffsetMid** <br/> |
| 4  <br/> | 右侧偏移  <br/> | 控制手柄与形状右侧偏移固定距离。  <br/> |**visCtlOffsetMax** <br/> |
| 5  <br/> | 成比例，隐藏  <br/> | 与值 0 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlProportionalHidden** <br/> |
| 6  <br/> | 比例锁定，隐藏  <br/> | 与值 1 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlLockedHiddenv** <br/> |
| 7  <br/> | 左侧偏移，隐藏  <br/> | 与值 2 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMinHidden** <br/> |
| 8  <br/> | 中心偏移，隐藏  <br/> | 与值 3 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMidHidden** <br/> |
| 9  <br/> | 右侧偏移，隐藏  <br/> | 与值 4 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMaxHidden** <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 X Behavior 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 控件。  *名称*。XConwhere 控件。  *name*是控制行的名称。  <br/> |
   
若要从某个程序按索引获取对 X Behavior 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCtlXCon** <br/> |
   

