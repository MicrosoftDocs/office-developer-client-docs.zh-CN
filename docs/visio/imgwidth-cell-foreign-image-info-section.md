---
title: ImgWidth 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm460
localization_priority: Normal
ms.assetid: b57fb962-0b3e-f2e5-3b88-3edf33e40496
description: 确定对象的图像在其边框内的宽度。默认公式为：
ms.openlocfilehash: 3aab65d27d426287060f7572dad15174acb93199
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780441"
---
# <a name="imgwidth-cell-foreign-image-info-section"></a>ImgWidth 单元格（“Foreign Image Info”部分）

确定对象的图像在其边框内的宽度。默认公式为：
  
= 宽度\*1
  
剪裁对象将更改与 Width 相乘的乘数。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgWidth 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ImgWidth  <br/> |
   
要从某个程序按索引获取对 ImgWidth 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgWidth** <br/> |
   

