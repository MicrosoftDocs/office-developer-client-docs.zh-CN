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
ms.openlocfilehash: 599810d126c853e37552045d0ef83cb580606ae2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427904"
---
# <a name="blur-cell-image-properties-section"></a>Blur 单元格（“Image Properties”内容）

虚化或柔化位图图像。默认值是 0%。
  
## <a name="remarks"></a>备注

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
   

