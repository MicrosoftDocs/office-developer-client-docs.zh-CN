---
title: Denoise 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm225
localization_priority: Normal
ms.assetid: e305585f-f0d8-0494-91d4-0c76929dc170
description: 删除位图图像中的杂色（颜色级别随机分布的像素）。默认值是 0%。
ms.openlocfilehash: f08d09126a24935c0dd4dcda5e88fdd559c8d176
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780097"
---
# <a name="denoise-cell-image-properties-section"></a>Denoise 单元格（“Image Properties”部分）

删除位图图像中的杂色（颜色级别随机分布的像素）。默认值是 0%。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Denoise 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Denoise  <br/> |
   
要从某个程序按索引获取对 Denoise 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowImage** <br/> |
| 单元格索引：  <br/> |**visImageDenoise** <br/> |
   

