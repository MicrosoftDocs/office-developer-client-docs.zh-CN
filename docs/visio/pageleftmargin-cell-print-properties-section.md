---
title: PageLeftMargin 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60061
localization_priority: Normal
ms.assetid: 7ecdfc37-c9d4-2fde-ed3e-be81657c24e2
description: 指定打印页左侧的边距。
ms.openlocfilehash: 289bd0bf16c6dcd9b26ec1a8c7920a29dab724a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435668"
---
# <a name="pageleftmargin-cell-print-properties-section"></a>PageLeftMargin 单元格（“Print Properties”内容）

指定打印页左侧的边距。
  
## <a name="remarks"></a>说明

此值表示物理单位并且不受缩放单位或绘图单位的影响。例如，如果此单元格的值为 0.25 in.，那么，即使页面单位是英尺，此边距仍为 0.25 英寸。如果没有明确规定单位，则此值默认为页面单位。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PageLeftMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLeftMargin  <br/> |
   
要从某个程序按索引获取对 PageLeftMargin 单元格的引用，请使用带下列参数的  **CellsSRC**  属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesLeftMargin** <br/> |
   

