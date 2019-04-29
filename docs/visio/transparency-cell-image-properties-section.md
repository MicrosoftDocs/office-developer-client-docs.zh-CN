---
title: Transparency 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm51095
localization_priority: Normal
ms.assetid: 5b265356-1602-4241-fbe1-4d5a55392a52
description: 确定图层颜色的透明度级别。
ms.openlocfilehash: defe5307e57c433fcf85a4132939d08cb1ddec77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405833"
---
# <a name="transparency-cell-image-properties-section"></a>Transparency 单元格（“Image Properties”内容）

确定图层颜色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|0 - 100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>说明

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然颜色完全透明的图层在绘图页上看起来和没有颜色的图层相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。您还可以使用 **“图层属性”** 对话框（在 **“开始”** 选项卡上的 **“编辑”** 组中，单击 **“图层”**，然后单击 **“图层属性”**）中的滑块控件设置此值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Transparency 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |透明度  <br/> |
   
若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowImage** <br/> |
|单元格索引：  <br/> |**visImageTransparency** <br/> |
   

