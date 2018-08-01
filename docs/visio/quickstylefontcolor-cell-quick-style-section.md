---
title: QuickStyleFontColor 单元格（“Quick Style”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31c56d08-19ea-4b8b-8be7-42e1c736fbca
description: 确定从形状的文本为从 0 1 的整数继承的活动主题的快速样式的字体颜色。
ms.openlocfilehash: 8f2d77508dccffccf472f8ab80517e840f860541
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781001"
---
# <a name="quickstylefontcolor-cell-quick-style-section"></a>QuickStyleFontColor 单元格（“Quick Style”部分）

确定从形状的文本为从 0 1 的整数继承的活动主题的快速样式的字体颜色。 
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状文本使用深色字体颜色。  <br/> |
|1  <br/> |形状文本使用浅字体颜色。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**QuickStyleFontColor**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFontColor  <br/> |
   
若要从某个程序按索引获取对**QuickStyleFontColor**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFontColor** <br/> |
   

