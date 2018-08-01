---
title: Blur 单元格（“Image Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm115
localization_priority: Normal
ms.assetid: 8b077cdb-6036-4f77-dc20-a476bb75b0f7
description: 虚化或柔化位图图像。默认值是 0%。
ms.openlocfilehash: 14a50f2015b2b24d7e41f5d11018a749d089fc37
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779785"
---
# <a name="blur-cell-image-properties-section"></a>Blur 单元格（“Image Properties”部分）

虚化或柔化位图图像。默认值是 0%。
  
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Blur 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Blur  <br/> |
   
要从某个程序按索引获取对 Blur 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowImage** <br/> |
| 单元格索引：  <br/> |**visImageBlur** <br/> |
   

