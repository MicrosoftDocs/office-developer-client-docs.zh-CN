---
title: ConLineJumpCode 单元格（“Shape Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251652
localization_priority: Normal
ms.assetid: af85588e-8e83-5168-7a8c-d7e8b4af5c27
description: 确定连接线何时跨线。
ms.openlocfilehash: 002f628841356ec8a22afbb9d4aeca8236058222
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779958"
---
# <a name="conlinejumpcode-cell-shape-layout-section"></a>ConLineJumpCode 单元格（“Shape Layout”部分）

确定连接线何时跨线。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |
          按照页面上指定的那样：在 **“设计”** 选项卡上，单击 **“页面设置”** 组中的箭头，然后单击 **“布局与排列”** 选项卡，查看页面规格
  <br/> |**visSLOJumpDefault** <br/> |
|1  <br/> |从不  <br/> |**visSLOJumpNever** <br/> |
|2  <br/> |两者都显示  <br/> |**visSLOJumpAlways** <br/> |
|3  <br/> |其他连接线跨线  <br/> |**visSLOJumpOther** <br/> |
|4  <br/> |
          两条连接线都不跨线
  <br/> |**visSLOJumpNeither** <br/> |
   
## <a name="remarks"></a>说明

您还可以设置此单元格的值选择动态连接线，在[开发人员](run-in-developer-mode-display-the-developer-tab.md)选项卡上的**形状设计**组中单击**行为**，然后单击**连接器**选项卡。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ConLineJumpCode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ConLineJumpCode  <br/> |
   
若要从某个程序按索引获取对 ConLineJumpCode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowShapeLayout** <br/> |
|单元格索引：  <br/> |**visSLOJumpCode** <br/> |
   

