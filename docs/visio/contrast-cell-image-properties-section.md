---
title: Contrast 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm200
localization_priority: Normal
ms.assetid: f0e4c644-c646-9649-c697-82feb02f5e29
description: 调整位图图像的对比度。输入 0% 到 49% 之间的值，可以减小图像的对比度；输入 51% 到 100% 之间的值，可以增加图像的对比度。默认值是 50%。
ms.openlocfilehash: 74a82fd9be49fcb9126c2b52bfcf25e0deb0e782
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779981"
---
# <a name="contrast-cell-image-properties-section"></a>Contrast 单元格（“Image Properties”部分）

调整位图图像的对比度。输入 0% 到 49% 之间的值，可以减小图像的对比度；输入 51% 到 100% 之间的值，可以增加图像的对比度。默认值是 50%。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Contrast 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Contrast  <br/> |
   
要从某个程序按索引获取对 Contrast 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowImage** <br/> |
| 单元格索引：  <br/> |**visImageContrast** <br/> |
   

