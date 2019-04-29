---
title: FontSchemeIndex 单元格 ("主题属性" 部分
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b832d75b-dac2-495f-b86e-d7fc5a484cab
description: 确定应用于形状的主题的字体方案, 以整数形式表示。
ms.openlocfilehash: 3a527b93b95f86dc1b9b92c931f3877ef28523ec
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420498"
---
# <a name="fontschemeindex-cell-theme-properties-section"></a>FontSchemeIndex 单元格 ("主题属性" 部分

确定应用于形状的主题的字体方案, 以整数形式表示。 
  
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**FontSchemeIndex**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | FontSchemeIndex  <br/> |
   
若要从某个程序按索引获取对**FontSchemeIndex**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowThemeProperties** <br/> |
| 单元格索引：  <br/> |**visFontSchemeIndex** <br/> |
   

