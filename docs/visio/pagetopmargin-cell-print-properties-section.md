---
title: PageTopMargin 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033785
localization_priority: Normal
ms.assetid: 2ba0fd22-65a6-6cb6-da00-08f391705544
description: 指定打印页顶部的边距。
ms.openlocfilehash: ff2bffffed39c5571386e792d2ffc8d20d6b291e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327361"
---
# <a name="pagetopmargin-cell-print-properties-section"></a>PageTopMargin 单元格（“Print Properties”内容）

指定打印页顶部的边距。
  
## <a name="remarks"></a>注解

此值表示物理单位并且不受缩放单位或绘图单位的影响。例如，如果此单元格的值为 0.25 in.，那么，即使页面单位是英尺，此边距仍为 0.25 英寸。如果没有明确规定单位，则此值默认为页面单位。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageTopMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageTopMargin  <br/> |
   
要从某个程序按索引获取对 PageTopMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesTopMargin** <br/> |
   

