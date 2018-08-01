---
title: LineColorTrans 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm50120
localization_priority: Normal
ms.assetid: b68054b5-7efd-1156-9dc1-5ec94e18d227
description: 确定形状的线条颜色的透明度级别。
ms.openlocfilehash: 81c23b77c4663158819f9d5fe53765860183e039
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780571"
---
# <a name="linecolortrans-cell-line-format-section"></a>LineColorTrans 单元格（“Line Format”部分）

确定形状的线条颜色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|
          0 - 100
  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

这些值被四舍五入为最接近的 0.5 个百分点。值 100% 是完全透明。虽然线条颜色完全透明的形状在绘图页上看起来和没有线条的形状相同，但是它与该页上其他对象的交互方式和透明度为 0% 的形状相同。 
  
还可以使用 **“线条”** 对话框中的滑块控件设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“粗细”**，然后单击 **“其他线条”**）。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineColorTrans 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineColorTrans  <br/> |
   
若要从某个程序按索引获取对 LineColorTrans 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineColorTrans** <br/> |
   

