---
title: FillForegndTrans 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253231
localization_priority: Normal
ms.assetid: 8b1b3904-6635-3fd1-31a9-ff32c19394af
description: 确定形状的填充图案的前景（填充）颜色的透明度级别。
ms.openlocfilehash: d05a83f83ea3d95ac3d42a2bfb3996917119f580
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322447"
---
# <a name="fillforegndtrans-cell-fill-format-section"></a>FillForegndTrans 单元格（“Fill Format”内容）

确定形状的填充图案的前景（填充）颜色的透明度级别。
  
|**Value**|**说明**|
|:-----|:-----|
|0 - 100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然填充色完全透明的形状在绘图页上看起来和没有填充的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。
  
您还可以使用 **“填充”** 对话框中的滑块控件设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“填充”**，然后单击 **“填充选项”**）。此值可以控制背景和前景填充透明度的值。若要单独设置上述值，必须在 ShapeSheet 窗口中输入它们。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FillForegndTrans 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |FillForegndTrans  <br/> |
   
若要从某个程序按索引获取对 FillForegndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillForegndTrans** <br/> |
   

