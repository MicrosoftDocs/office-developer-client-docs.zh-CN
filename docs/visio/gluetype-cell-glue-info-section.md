---
title: GlueType 单元格（“Glue Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm420
localization_priority: Normal
ms.assetid: fffbefd6-8b0b-0023-6b03-026d1c6e885e
description: 确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。
ms.openlocfilehash: ae4eddf17c6e7b5e56cb3397f03d0721d965c9b7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410670"
---
# <a name="gluetype-cell-glue-info-section"></a>GlueType 单元格（“Glue Info”内容）

确定将一维形状粘附到另一个形状时是使用静态粘附（点到点）还是动态粘附（形状到形状）。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| &amp;H0  <br/> | 默认值。只有动态连接线可使用动态粘附；其他形状均使用静态粘附。  <br/> |**visGlueTypeDefault** <br/> |
| &amp;H1  <br/> | 允许动态粘附。  <br/> | 在 Visio 2002 中已经放弃该功能。  <br/> |
| &amp;H2  <br/> | 允许动态粘附。  <br/> |**visGlueTypeWalking** <br/> |
| &amp;H4  <br/> | 不允许动态粘附。  <br/> |**visGlueTypeNoWalking** <br/> |
| &amp;H8  <br/> | 不允许使用动态粘附连接此二维形状。  <br/> |**visGlueTypeNoWalkingTo** <br/> |
   
## <a name="remarks"></a>备注

如果此单元格包含值 1、2 或 3，则只要出现以下二者之一就将建立动态粘附：
  
- 在用户界面中动态粘附形状。
    
- 从某个程序中将形状粘附到另一个形状的 PinX 或 PinY 单元格。
    
如果从某个程序将形状粘附到 PinX 或 PinY 之外的其他形状单元格，则使用静态粘附。
  
将此值由允许动态粘附更改为不允许动态粘附并不会切断或更改现有的动态粘附。即便在 GlueType 单元格中禁用了动态粘附，程序仍然可以建立动态粘附。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 GlueType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | GlueType  <br/> |
   
要从某个程序按索引获取对 GlueType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visGlueType** <br/> |
   

