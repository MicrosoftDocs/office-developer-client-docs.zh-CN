---
title: LineWeight 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm585
localization_priority: Normal
ms.assetid: 16b0e293-eeef-34b4-aeb0-4472815dd543
description: 确定形状的线条粗细。通过输入具有有效度量单位的数字即可设置线条粗细。
ms.openlocfilehash: 654a93f939226bedab2e40ab591dad0e3f872267
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412245"
---
# <a name="lineweight-cell-line-format-section"></a>LineWeight 单元格（“Line Format”内容）

确定形状的线条粗细。通过输入具有有效度量单位的数字即可设置线条粗细。
  
## <a name="remarks"></a>备注

还可以在 **“线条”** 对话框（在 **“开始”** 选项卡上，**“形状”** 组中，单击 **“线条”**，指向 **“权重”**，然后单击 **“其他线条”**）中设置 LineWeight 的值。
  
如果未输入度量单位，则使用 **"Visio** 选项"对话框中指定的文本的度量单位 ("文件"选项卡，然后单击"选项") 。   线条粗细与绘图比例无关。 即使绘图比例进行调整，线条粗细仍将保持不变。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LineWeight 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LineWeight  <br/> |
   
若要从某个程序按索引获取对 LineWeight 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visLineWeight** <br/> |
   

