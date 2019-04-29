---
title: CtrlAsInput 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1225
localization_priority: Normal
ms.assetid: c6fd0aba-7c33-b77f-207b-ba704b3e0756
description: 确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。
ms.openlocfilehash: a530c48156043bec0cd58d79aead1a403c17ddce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422619"
---
# <a name="ctrlasinput-cell-page-layout-section"></a>CtrlAsInput 单元格（“Page Layout”内容）

确定使用带有控制手柄的形状时哪个形状是父级。该单元格设置绘图页上所有形状的行为。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 将控制手柄连接到的形状设置为父级。  <br/> |
| FALSE  <br/> | 默认值。将包含控制手柄的形状设置为父级。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 CtrlAsInput 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CtrlAsInput  <br/> |
   
要从某个程序按索引获取对 CtrlAsInput 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLOCtrlAsInput** <br/> |
   

