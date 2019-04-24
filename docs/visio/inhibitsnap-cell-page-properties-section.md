---
title: InhibitSnap 单元格（“Page Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251620
localization_priority: Normal
ms.assetid: ab9fcebc-1550-3b9e-e3b4-e8b92424390b
description: 确定前景页中的形状是否与该页中的其他对象和背景页中的形状对齐。
ms.openlocfilehash: 665130e9f9f938349028ffa1d1c06224e746de5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335320"
---
# <a name="inhibitsnap-cell-page-properties-section"></a>InhibitSnap 单元格（“Page Properties”内容）

确定前景页中的形状是否与该页中的其他对象和背景页中的形状对齐。
  
|**Value**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 除对齐标尺和网格外，不对齐该页中的任何对象。  <br/> |
| FALSE  <br/> | 启用对齐。  <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 InhibitSnap 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | InhibitSnap  <br/> |
   
要从某个程序按索引获取对 InhibitSnap 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageInhibitSnap** <br/> |
   

