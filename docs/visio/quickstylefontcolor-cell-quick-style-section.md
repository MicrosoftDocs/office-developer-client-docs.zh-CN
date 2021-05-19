---
title: 'QuickStyleFontColor Cell (Quick Style Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 31c56d08-19ea-4b8b-8be7-42e1c736fbca
description: 确定形状的文本从活动主题继承的快速样式中的字体颜色，作为 0-1 的整数。
ms.openlocfilehash: bd645383df02260fcf6a2045764d9a1b44126090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415024"
---
# <a name="quickstylefontcolor-cell-quick-style-section"></a>QuickStyleFontColor Cell (Quick Style Section) 

确定形状的文本从活动主题继承的快速样式中的字体颜色，作为 0-1 的整数。 
  
|||
|:-----|:-----|
|值  <br/> |说明  <br/> |
|0  <br/> |形状文本使用深色字体颜色。  <br/> |
|1  <br/> |形状文本使用浅色字体颜色。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **QuickStyleFontColor** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | QuickStyleFontColor  <br/> |
   
若要从程序按索引获取对 **QuickStyleFontColor** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowQuickStyleProperties** <br/> |
| 单元格索引：  <br/> |**visQuickStyleFontColor** <br/> |
   

