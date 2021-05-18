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
ms.openlocfilehash: 956bc478604fd19d8dfdbb7079e092e9e8a16e7b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411195"
---
# <a name="imgheight-cell-foreign-image-info-section"></a>ImgHeight 单元格（“Foreign Image Info”内容）

确定对象的图像在其边框内的高度。默认公式为：
  
= 高度 \* 1
  
## <a name="remarks"></a>备注

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
   

