---
title: TopMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1015
localization_priority: Normal
ms.assetid: c599b444-4d0e-a855-b04b-dd9dcaedf263
description: 确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。
ms.openlocfilehash: 97d349fd4ddc3c76cda61e1ee7ce25909161e6fa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435570"
---
# <a name="topmargin-cell-text-block-format-section"></a>TopMargin 单元格（“Text Block Format”内容）

确定文本块的上边界和它包含的第一行文本之间的距离。默认值是 4.0000 磅。此值与绘图比例无关。即使对绘图比例进行了调整，上边距仍保持不变。
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TopMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TopMargin  <br/> |
   
要从某个程序按索引获取对 TopMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkTopMargin** <br/> |
   

