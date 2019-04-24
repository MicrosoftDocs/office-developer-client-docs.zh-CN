---
title: QuickStyleFontMatrix 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 304ee083-e9c8-45df-b411-ba5e7db4c086
description: 确定每个快速样式的字体样式 (从1到6的整数)。
ms.openlocfilehash: 0708a243b001c7b4e03158b5a332a3166727cabc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360072"
---
# <a name="quickstylefontmatrix-cell-quick-style-section"></a>QuickStyleFontMatrix 单元格 ("快速样式" 部分)

确定每个快速样式的字体样式 (从1到6的整数)。
  
## <a name="remarks"></a>注解

若要从另一个公式按名称获取对**QuickStyleFontMatrix**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFontMatrix  <br/> |
   
若要从某个程序按索引获取对**QuickStyleFontMatrix**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFontMatrix** <br/> |
   

