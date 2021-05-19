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
ms.openlocfilehash: bd42b069e6796b107aafaea3080f6970c4f678c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410348"
---
# <a name="noshow-cell-geometry-section"></a>NoShow 单元格（“Geometry”内容）

指明路径是否显示在绘图页上。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 隐藏本内容所表示的路径的划线和填充。  <br/> |
| FALSE  <br/> | 显示路径的划线和填充。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoShow 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry  *i*  .NoShow where  *i*  = <1>， 2， 3...  <br/> |
   
要从某个程序按索引获取对 NoShow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 行索引：  <br/> |**visRowComponent** <br/> |
| 单元格索引：  <br/> |**visCompNoShow** <br/> |
   

