---
title: LineAdjustFrom 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251887
localization_priority: Normal
ms.assetid: 6949c717-dc69-1d17-5215-eb6efce56fcb
description: 确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。
ms.openlocfilehash: ee3a107f7e19b53017c2ea24c94babceb49620d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780559"
---
# <a name="lineadjustfrom-cell-page-layout-section"></a>LineAdjustFrom 单元格（“Page Layout”部分）

确定在出现动态连接线彼此重叠的情况下应用程序将分隔哪些动态连接线。
  
|**值**|**调整**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |无关的线条  <br/> |**visPLOLineAdjustFromNotRelated** <br/> |
|1  <br/> |所有线条  <br/> |**visPLOLineAdjustFromAll** <br/> |
|2  <br/> |无线条  <br/> |**visPLOLineAdjustFromNone** <br/> |
|3  <br/> |默认的排列样式  <br/> |**visPLOLineAdjustFromRoutingDefault** <br/> |
   
## <a name="remarks"></a>说明

还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineAdjustFrom 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineAdjustFrom  <br/> |
   
若要从某个程序按索引获取对 LineAdjustFrom 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineAdjustFrom** <br/> |
   

