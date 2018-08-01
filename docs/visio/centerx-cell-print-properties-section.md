---
title: CenterX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60030
localization_priority: Normal
ms.assetid: 890e2537-66a5-2863-c78d-320b42565ea7
description: 确定该绘图页是否在打印纸上水平居中。
ms.openlocfilehash: a12b60f7d183a27d938bd18a1f571ef01af455d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779870"
---
# <a name="centerx-cell-print-properties-section"></a>CenterX 单元格（“Print Properties”部分）

确定该绘图页是否在打印纸上水平居中。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 使绘图页在打印纸上水平居中。  <br/> |
| FALSE  <br/> | 使绘图页在打印纸上不水平居中（默认值）。  <br/> |
   
## <a name="remarks"></a>注释

默认情况下，绘图页与打印纸的左上角对齐。将 CenterX 单元格和 CenterY 单元格设置为 TRUE，可以将绘图页放置在打印纸的中心（如果需要平铺，则放置在多张打印纸的中心）。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 CenterX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CenterX  <br/> |
   
要从某个程序按索引获取对 CenterX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesCenterX** <br/> |
   

