---
title: ShdwForegndTrans 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82253253
localization_priority: Normal
ms.assetid: c42d4d2e-f8f0-bc5b-6018-4bb4ffa81b64
description: 确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。
ms.openlocfilehash: 0ef3ce525edcce4ccd61f36649ead512545eef58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349096"
---
# <a name="shdwforegndtrans-cell-fill-format-section"></a>ShdwForegndTrans 单元格（“Fill Format”内容）

确定用于形状的投影填充图案的前景（划线）颜色的透明度级别。
  
|**Value**|**说明**|
|:-----|:-----|
|0 - 100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

这些值被四舍五入为最接近的 0.5 个百分点。 值 100% 是完全透明。 虽然具有完全透明填充的阴影在绘图页上显示为没有填充的阴影, 但它与页面上的其他对象进行交互的方式与它的透明度为 0% 的方式相同。
  
您还可以使用 **“阴影”** 对话框（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“阴影”**，然后单击 **“阴影选项”**）中的滑块控件设置此值。此值同时控制背景和前景阴影透明度的值。若要单独设置上述值，必须在 ShapeSheet 窗口中输入它们。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ShdwForegndTrans 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ShdwForegndTrans  <br/> |
   
若要从某个程序按索引获取对 ShdwForegndTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowFill** <br/> |
|单元格索引：  <br/> |**visFillShdwForegndTrans** <br/> |
   

