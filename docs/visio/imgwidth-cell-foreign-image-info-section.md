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
description: 确定对象的图像在其边框内的宽度。 默认公式为：
ms.openlocfilehash: 9da5e06a7fbf6ae77a49fb0410aefb406e2afecb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422829"
---
# <a name="imgwidth-cell-foreign-image-info-section"></a>ImgWidth 单元格（“Foreign Image Info”内容）

确定对象的图像在其边框内的宽度。 默认公式为：
  
= Width \* 1
  
剪裁对象将更改与 Width 相乘的乘数。
  
## <a name="remarks"></a>说明

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
   

