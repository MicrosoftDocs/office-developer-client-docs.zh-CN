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
description: 删除位图图像中的杂色（颜色级别随机分布的像素）。 默认值是 0%。
ms.openlocfilehash: f970fde22e864239ea3f3f9bcb704e7f4692e9cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415801"
---
# <a name="denoise-cell-image-properties-section"></a>Denoise 单元格（“Image Properties”内容）

删除位图图像中的杂色（颜色级别随机分布的像素）。 默认值是 0%。
  
## <a name="remarks"></a>说明

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
   

