---
title: ImgHeight 单元格（“Foreign Image Info”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm445
localization_priority: Normal
ms.assetid: decb86a4-b711-35e1-b9dc-744a84ee177c
description: 确定对象的图像在其边框内的高度。默认公式为：
ms.openlocfilehash: 983bb919dbfada65b6d9af464ecfa17c04e970c6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780443"
---
# <a name="imgheight-cell-foreign-image-info-section"></a>ImgHeight 单元格（“Foreign Image Info”部分）

确定对象的图像在其边框内的高度。默认公式为：
  
= 高度\*1
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ImgHeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ImgHeight  <br/> |
   
要从某个程序按索引获取对 ImgHeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowForeign** <br/> |
| 单元格索引：  <br/> |**visFrgnImgHeight** <br/> |
   

