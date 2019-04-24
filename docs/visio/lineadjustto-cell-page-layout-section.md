---
title: LineAdjustTo 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm525
localization_priority: Normal
ms.assetid: 81cd9670-8a6f-824b-528c-e9b88c86f525
description: 确定哪些动态连接线要彼此重叠。
ms.openlocfilehash: e4fb32c0fcb488173324ea597edc2c9d13f6bfca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359309"
---
# <a name="lineadjustto-cell-page-layout-section"></a>LineAdjustTo 单元格（“Page Layout”内容）

确定哪些动态连接线要彼此重叠。
  
|**值**|**调**|**自动常量**|
|:-----|:-----|:-----|
|0  <br/> |默认的排列样式  <br/> |**visPLOLineAdjustToDefault** <br/> |
|1  <br/> |彼此紧邻的线条  <br/> |**visPLOLineAdjustToAll** <br/> |
|双面  <br/> |无线条  <br/> |**visPLOLineAdjustToNone** <br/> |
|第三章  <br/> |相关线条  <br/> |**visPLOLineAdjustToRelated** <br/> |
   
## <a name="remarks"></a>注解

还可以在 **“页面设置”** 对话框中的 **“布局与排列”** 选项卡（在 **“设计”** 选项卡上，单击 **“页面设置”** 箭头，然后单击 **“布局与排列”**）上设置此单元格的值。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 LineAdjustTo 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineAdjustTo  <br/> |
   
若要从某个程序按索引获取对 LineAdjustTo 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOLineAdjustTo** <br/> |
   

