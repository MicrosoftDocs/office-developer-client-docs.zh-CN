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
description: 控制控制手柄的 x 坐标在手柄移动后将表现的行为的类型。
ms.openlocfilehash: 50b08664deec69659ff70a0bf9a17a148ed0e110
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413946"
---
# <a name="x-behavior-cell-controls-section"></a>X Behavior 单元格（“Controls”内容）

控制控制手柄的*x*坐标在手柄移动后将表现的行为的类型。 
  
|**值**|**行为**|**定义**|**自动常量**|
|:-----|:-----|:-----|:-----|
| 0  <br/> | 非  <br/> | 控制手柄可以移动，在伸展时它也随形状按比例移动。  <br/> |**visCtlProportional** <br/> |
| 1  <br/> | 比例锁定  <br/> | 控制手柄可按比例与形状一起移动，但控制手柄本身不能移动。  <br/> |**visCtlLocked** <br/> |
| 双面  <br/> | 左侧偏移  <br/> | 控制手柄与形状左侧偏移固定距离。  <br/> |**visCtlOffsetMin** <br/> |
| 第三章  <br/> | 中心偏移  <br/> | 控制手柄与形状中心偏移固定距离。  <br/> |**visCtlOffsetMid** <br/> |
| 4  <br/> | 右侧偏移  <br/> | 控制手柄与形状右侧偏移固定距离。  <br/> |**visCtlOffsetMax** <br/> |
| 5  <br/> | 成比例，隐藏  <br/> | 与值 0 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlProportionalHidden** <br/> |
| 型  <br/> | 比例锁定，隐藏  <br/> | 与值 1 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlLockedHiddenv** <br/> |
| 步  <br/> | 左侧偏移，隐藏  <br/> | 与值 2 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMinHidden** <br/> |
| utf-8  <br/> | 中心偏移，隐藏  <br/> | 与值 3 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMidHidden** <br/> |
| 第  <br/> | 右侧偏移，隐藏  <br/> | 与值 4 的含义相同，但控制手柄被隐藏起来了。  <br/> |**visCtlOffsetMaxHidden** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X Behavior 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 措施.  *名称*。XConwhere 控件。  *名称*是控件行的名称。  <br/> |
   
要从某个程序按索引获取对 X Behavior 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCtlXCon** <br/> |
   

