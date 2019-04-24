---
title: PagesX 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60064
localization_priority: Normal
ms.assetid: a10bf4c2-24f4-4c53-39ba-2b8cd5b50d2c
description: 确定从横向适合绘图页的打印纸的数目。
ms.openlocfilehash: e912aef2277f5a7d2af5352897654ee986836c48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340136"
---
# <a name="pagesx-cell-print-properties-section"></a>PagesX 单元格（“Print Properties”内容）

确定从横向适合绘图页的打印纸的数目。 
  
## <a name="remarks"></a>注解

只有在 OnPage 单元格设置为 TRUE 后才使用此值。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PagesX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PagesX  <br/> |
   
要从某个程序按索引获取对 PagesX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesPagesX** <br/> |
   

