---
title: ImgOffsetX 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251308
localization_priority: Normal
ms.assetid: c079fb10-4db7-4657-75d2-2fb953c86670
description: 确定对象水平偏离对象边框的原点的距离。 默认值为 0。 使用“剪裁”工具扫视对象将更改该值。
ms.openlocfilehash: d9b3e97a07bc1cadc0276905c4199861ab0590ca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405231"
---
# <a name="imgoffsetx-cell-foreign-image-info-section"></a>ImgOffsetX 单元格（“Foreign Image Info”内容）

确定对象水平偏离对象边框的原点的距离。默认值为 0。使用 **“剪裁”** 工具扫视对象将更改该值。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgOffsetX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ImgOffsetX  <br/> |
   
要从某个程序按索引获取对 ImgOffsetX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgOffsetX** <br/> |
   

