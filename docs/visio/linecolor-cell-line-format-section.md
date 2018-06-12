---
title: LineColor 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm535
localization_priority: Normal
ms.assetid: d857b48b-9a3d-a1e1-5ad2-6816a492c8ab
description: 确定形状的线条颜色。
ms.openlocfilehash: 6086a45108b88475e250c4d833ab4b740f33b8e7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780574"
---
# <a name="linecolor-cell-line-format-section"></a>LineColor 单元格（“Line Format”内容）

确定形状的线条颜色。
  
## <a name="remarks"></a>注解

要设置的线条颜色，请输入介于 0 到 23 数字，这是集合中的线条颜色的索引。 在**线条**对话框中，可以查看线条颜色集合 （在**主页**选项卡，**形状**组中，单击**线条**，指向**权重**，，然后单击**多行**）。 您还可以在**线条**对话框来设置线条颜色的值。 
  
若要输入自定义颜色，使用 RGB 或 HSL 函数。 自定义颜色的值为 RGB 颜色，并且 RGB （ *r、 g、 b*），而不是一个号码，将显示在 ShapeSheet 窗口中。 当使用中的数字运算，自定义颜色具有值将大于或等于，共 24 部分。 
  
您可以在 LineColorTrans 单元格中设置线条颜色的透明度。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 LineColor 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |LineColor  <br/> |
   
若要从某个程序按索引获取对 LineColor 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineColor** <br/> |
   

