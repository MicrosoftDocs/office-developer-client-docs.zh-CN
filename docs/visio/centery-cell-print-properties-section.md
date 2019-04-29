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
ms.openlocfilehash: 858bf41c74fdcbd82d271a379df7c5816a7796fd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437432"
---
# <a name="centery-cell-print-properties-section"></a>CenterY 单元格（“Print Properties”内容）

确定绘图页是否在打印纸上垂直居中。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 使绘图页在打印纸上垂直居中。  <br/> |
| FALSE  <br/> | 使绘图页在打印纸上不垂直居中（默认值）。  <br/> |
   
## <a name="remarks"></a>说明

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
   

