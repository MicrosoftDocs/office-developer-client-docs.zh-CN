---
title: NoFill 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm710
localization_priority: Normal
ms.assetid: 0ba7f6da-681b-b749-fe72-afbca23d7e16
description: 指示是否可以填充路径。
ms.openlocfilehash: 301f30b644e338ff9e597a7a7d8226b9c8a4462f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357251"
---
# <a name="nofill-cell-geometry-section"></a>NoFill 单元格（“Geometry”内容）

指示是否可以填充路径。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不填充该路径，即使可填充形状中的其他路径。  <br/> |
| FALSE  <br/> | 形状的填充适用于该路径，即使它不是封闭的路径。  <br/> |
   
## <a name="remarks"></a>注解

如果将形状的填充图案设置为非 (0)，则不填充该形状的任何路径。此单元格用于选择性地禁用形状中路径的填充方式。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoFill 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 几何图形*i* 。NoFill 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 NoFill 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i* = ** 0、1、2 .。。  <br/> |
| 行索引：  <br/> |**visRowComponent** <br/> |
| 单元格索引：  <br/> |**visCompNoFill** <br/> |
   

