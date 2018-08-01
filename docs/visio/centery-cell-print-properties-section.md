---
title: CenterY 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033792
localization_priority: Normal
ms.assetid: 7ce0bf66-dc8b-9646-7b04-50c969ecd67a
description: 确定绘图页是否在打印纸上垂直居中。
ms.openlocfilehash: 2fde1d6301d7b9de4540cd12f21e5af01d7a6239
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779889"
---
# <a name="centery-cell-print-properties-section"></a>CenterY 单元格（“Print Properties”部分）

确定绘图页是否在打印纸上垂直居中。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 使绘图页在打印纸上垂直居中。  <br/> |
| FALSE  <br/> | 使绘图页在打印纸上不垂直居中（默认值）。  <br/> |
   
## <a name="remarks"></a>注释

默认情况下，绘图页与打印纸的左上角对齐。将 CenterX 单元格和 CenterY 单元格设置为 TRUE，可以将绘图页放置在打印纸的中心（如果需要平铺，则放置在多张打印纸的中心）。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 CenterY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | CenterY  <br/> |
   
要从某个程序按索引获取对 CenterY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesCenterY** <br/> |
   

