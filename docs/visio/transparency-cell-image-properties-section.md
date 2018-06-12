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
ms.openlocfilehash: 5537cbdcd49c66f3bc28a58051f6e2888a290cd3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781545"
---
# <a name="transparency-cell-image-properties-section"></a>Transparency 单元格（“Image Properties”内容）

确定图层颜色的透明度级别。
  
|**值**|**说明**|
|:-----|:-----|
|0-100  <br/> |表示透明度的百分比。默认值为 0%（完全不透明）。  <br/> |
   
## <a name="remarks"></a>注解

值将四舍五入到最接近半百分比。 值为 100%是完全透明的。 尽管完全透明颜色的图层显示在绘图页上相同为无颜色的图层，它与交互页上的其他对象相同的方式透明度当作 0%。 您还可以通过使用**图层属性**对话框中的滑块控件设置此值 （**主页**选项卡，在**编辑**组中，单击**图层**，，然后单击**图层属性**）。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Transparency 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Transparency  <br/> |
   
若要从某个程序按索引获取对 Transparency 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowImage** <br/> |
|单元格索引：  <br/> |**visImageTransparency** <br/> |
   

