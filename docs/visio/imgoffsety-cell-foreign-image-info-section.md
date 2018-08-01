---
title: ImgOffsetY 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm455
localization_priority: Normal
ms.assetid: 3b2991aa-4722-fe3b-39c5-02d38c4c7efc
description: 确定对象垂直偏离对象边框的原点的距离。默认值为 0。使用“剪裁”工具扫视对象将更改该值。
ms.openlocfilehash: 2930aa092a2b776ceb0c9c4677f7e5da7f5dcdda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780435"
---
# <a name="imgoffsety-cell-foreign-image-info-section"></a>ImgOffsetY 单元格（“Foreign Image Info”部分）

确定对象垂直偏离对象边框的原点的距离。默认值为 0。使用 **“剪裁”** 工具扫视对象将更改该值。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgOffsetY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ImgOffsetY  <br/> |
   
要从某个程序按索引获取对 ImgOffsetY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgOffsetY** <br/> |
   

