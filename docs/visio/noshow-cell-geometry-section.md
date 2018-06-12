---
title: NoShow 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm735
localization_priority: Normal
ms.assetid: 831075ff-2875-b598-00bb-eb8481fee57b
description: 指明路径是否显示在绘图页上。
ms.openlocfilehash: ad4d9cf1aa3e541f512bc09ffc38cf03204b3c94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780826"
---
# <a name="noshow-cell-geometry-section"></a>NoShow 单元格（“Geometry”内容）

指明路径是否显示在绘图页上。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 隐藏本内容所表示的路径的划线和填充。  <br/> |
| FALSE  <br/> | 显示路径的划线和填充。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 NoShow 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry *i* 。NoShow 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 NoShow 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 行索引：  <br/> |**visRowComponent** <br/> |
| 单元格索引：  <br/> |**visCompNoShow** <br/> |
   

