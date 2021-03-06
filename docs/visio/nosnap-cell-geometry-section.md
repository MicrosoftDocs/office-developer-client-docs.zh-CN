---
title: NoSnap 单元格（“Geometry”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm740
localization_priority: Normal
ms.assetid: 0e6c8621-868c-9eac-926b-3049f18023b0
description: 确定其他形状是否与路径对齐。
ms.openlocfilehash: 60a6532aee0f391eb38609f6ed87577e5558d5c2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408542"
---
# <a name="nosnap-cell-geometry-section"></a>NoSnap 单元格（“Geometry”内容）

确定其他形状是否与路径对齐。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 不允许其他形状与该路径对齐。  <br/> |
| FALSE  <br/> | 允许其他形状与该路径对齐。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NoSnap 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Geometry  *i*  .NoSnap 其中  *i*  = <1>、2、3...  <br/> |
   
要从某个程序按索引获取对 NoSnap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionFirstComponent**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 行索引：  <br/> |**visRowComponent** <br/> |
| 单元格索引：  <br/> |**visCompNoSnap** <br/> |
   

