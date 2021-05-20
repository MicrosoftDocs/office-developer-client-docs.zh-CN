---
title: DynamicsOff 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251641
localization_priority: Normal
ms.assetid: 055764aa-9681-ffb0-83ce-fdd612fe37af
description: 确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。
ms.openlocfilehash: d1075ab1b0512d5db1c7b7a5f2895305318dae7d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437474"
---
# <a name="dynamicsoff-cell-page-layout-section"></a>DynamicsOff 单元格（“Page Layout”内容）

确定是否移动可放置的形状并让连接线围绕绘图页上的其他形状和连接线重排。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 禁用动态特性。  <br/> |
| FALSE  <br/> | 启用动态特性。  <br/> |
   
## <a name="remarks"></a>备注

您可以禁用动态特性来提高解决方案的性能。例如，如果您的解决方案要将可放置的形状添加到绘图中，而您又不希望应用程序在每添加一个形状后都重排连接线和移动形状的位置，就可以禁用动态特性。在您的解决方案添加完所有形状之后，再重新启用动态特性。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DynamicsOff 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DynamicsOff  <br/> |
   
要从某个程序按索引获取对 DynamicsOff 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPageLayout** <br/> |
| 单元格索引：  <br/> |**visPLODynamicsOff** <br/> |
   

