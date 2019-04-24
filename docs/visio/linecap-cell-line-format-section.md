---
title: LineCap 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251231
localization_priority: Normal
ms.assetid: 3519216b-b6cf-2e8c-e20f-adfa373c9028
description: 指示线端形状是圆形、方形还是扩展式。
ms.openlocfilehash: 44de4bff87fd3d121dfce9eec934ec39bc61065a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359316"
---
# <a name="linecap-cell-line-format-section"></a>LineCap 单元格（“Line Format”内容）

指示线端形状是圆形、方形还是扩展式。
  
|**值**|**线端样式**|
|:-----|:-----|
|0  <br/> |四舍五入  <br/> |
|1  <br/> |正方形  <br/> |
|双面  <br/> |扩展  <br/> |
   
## <a name="remarks"></a>注解

您还可以在 **“线条”** 对话框中设置此单元格的值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“箭头”**，然后单击 **“其他箭头”**）。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineCap 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineCap  <br/> |
   
若要从某个程序按索引获取对 LineCap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineEndCap** <br/> |
   

