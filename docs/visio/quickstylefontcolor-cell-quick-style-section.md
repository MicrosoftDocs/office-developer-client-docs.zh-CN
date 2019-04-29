---
title: QuickStyleFontColor 单元格 ("快速样式" 部分)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31c56d08-19ea-4b8b-8be7-42e1c736fbca
description: 确定从活动主题中的形状的文本继承的快速样式中的字体颜色, 以0-1 形式的整数表示。
ms.openlocfilehash: bd645383df02260fcf6a2045764d9a1b44126090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415024"
---
# <a name="quickstylefontcolor-cell-quick-style-section"></a>QuickStyleFontColor 单元格 ("快速样式" 部分)

确定从活动主题中的形状的文本继承的快速样式中的字体颜色, 以0-1 形式的整数表示。 
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状文本使用深字体颜色。  <br/> |
|1  <br/> |形状文本使用浅色字体颜色。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**QuickStyleFontColor**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFontColor  <br/> |
   
若要从某个程序按索引获取对**QuickStyleFontColor**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFontColor** <br/> |
   

