---
title: PageBottomMargin 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60060
localization_priority: Normal
ms.assetid: 7a97e97c-278d-2e1e-6c4f-f5f32e2cdeb0
description: 指定打印页底部的边距。
ms.openlocfilehash: f546d89b8761c6c1b7340af69d2b48f16c180767
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334410"
---
# <a name="pagebottommargin-cell-print-properties-section"></a>PageBottomMargin 单元格（“Print Properties”内容）

指定打印页底部的边距。
  
## <a name="remarks"></a>注解

此值表示物理单位并且不受缩放单位或绘图单位的影响。例如，如果此单元格的值为 0.5 in.，那么，即使页面单位是英尺，此边距仍为 0.5 英寸。如果没有明确规定单位，则此值默认为页面单位。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageBottomMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageBottomMargin  <br/> |
   
要从某个程序按索引获取对 PageBottomMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesBottomMargin** <br/> |
   

