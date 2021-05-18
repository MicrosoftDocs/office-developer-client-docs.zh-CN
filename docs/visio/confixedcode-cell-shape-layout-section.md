---
title: ConFixedCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm175
localization_priority: Normal
ms.assetid: 8e7c9080-7ef1-0696-a3d2-d8f57ea5ab9b
description: 确定何时重排连接线。
ms.openlocfilehash: b2b9cde309c720493f0e46962b2fe6c2e79545d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404181"
---
# <a name="confixedcode-cell-shape-layout-section"></a>ConFixedCode 单元格（“Shape Layout”内容）

确定何时重排连接线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |自由重排  <br/> |**visSLOConFixedRerouteFreely** <br/> |
|1  <br/> |根据需要重排（手动重排）  <br/> |**visSLOConFixedRerouteAsNeeded** <br/> |
|2  <br/> |从不重排  <br/> |**visSLOConFixedRerouteNever** <br/> |
|3  <br/> |在交点上重排  <br/> |**visSLOConFixedRerouteOnCrossover** <br/> |
|4   <br/> |仅供内部使用  <br/> |**visSLOConFixedByAlgFrom** <br/> |
|5   <br/> |仅供内部使用  <br/> |**visSLOConFixedByAlgTo** <br/> |
|6   <br/> |仅供内部使用  <br/> |**visSLOConFixedByAlgFromTo** <br/> |
   
## <a name="remarks"></a>备注

您还可以通过选择动态连接线、单击"开发工具"选项卡上的"形状设计"组中的行为，然后单击"连接 [](run-in-developer-mode-display-the-developer-tab.md)线"选项卡来设置此 **单元格** 的值。  
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConFixedCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ConFixedCode  <br/> |
   
若要从某个程序按索引获取对 ConFixedCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOConFixedCode** <br/> |
   

