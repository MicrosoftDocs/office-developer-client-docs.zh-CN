---
title: ShapePermeableY 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251666
localization_priority: Normal
ms.assetid: 90701ecf-3d34-2eac-9ee9-7965e16c0f7c
description: 确定连接线是否可以垂直穿绕形状。
ms.openlocfilehash: 62f8bfa0fdfb5c483836f344e8b784dc9092fded
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417516"
---
# <a name="shapepermeabley-cell-shape-layout-section"></a>ShapePermeableY 单元格（“Shape Layout”内容）

确定连接线是否可以垂直穿绕形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |允许连接线垂直穿绕形状。  <br/> |
|FALSE  <br/> |不允许连接线垂直穿绕形状。  <br/> |
   
## <a name="remarks"></a>备注

您还可以在"行为"对话框的"放置"选项卡上设置此单元格的值 (其中选择了一个形状;在"开发工具"[](run-in-developer-mode-display-the-developer-tab.md)选项卡上的"形状设计"组中，单击"行为"，然后单击"放置"选项卡) 。   
  
在 Visio 2000 之前的版本中，您可以使用“Miscellaneous”内容中的 ObjInteract 单元格设置此行为。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShapePermeableY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShapePermeableY  <br/> |
   
若要从某个程序按索引获取对 ShapePermeableY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOPermY** <br/> |
   

