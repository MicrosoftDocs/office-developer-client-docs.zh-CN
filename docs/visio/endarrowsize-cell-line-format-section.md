---
title: EndArrowSize 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251630
localization_priority: Normal
ms.assetid: e2ecf7c0-a0e9-951f-676a-8e5857bb6544
description: 确定线条末端的箭头大小。
ms.openlocfilehash: 768a2b2adb05248049377eaee07194cdb89ed810
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438076"
---
# <a name="endarrowsize-cell-line-format-section"></a>EndArrowSize 单元格（“Line Format”内容）

确定线条末端的箭头大小。
  
|**值**|**Size**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |非常小  <br/> |**visArrowSizeVerySmall** <br/> |
|1  <br/> |小型  <br/> |**visArrowSizeSmall** <br/> |
|双面  <br/> |中等  <br/> |**visArrowSizeMedium** <br/> |
|第三章  <br/> |大型  <br/> |**visArrowSizeLarge** <br/> |
|4  <br/> |特大  <br/> |**visArrowSizeVeryLarge** <br/> |
|5  <br/> |超长  <br/> |**visArrowSizeJumbo** <br/> |
|型  <br/> |Colossal  <br/> |**visArrowSizeColossal** <br/> |
   
## <a name="remarks"></a>说明

您还可以在 **“线条”** 对话框中设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“箭头”**，然后单击 **“其他箭头”**）。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 EndArrowSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EndArrowSize  <br/> |
   
若要从某个程序按索引获取对 EndArrowSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineEndArrowSize** <br/> |
   

