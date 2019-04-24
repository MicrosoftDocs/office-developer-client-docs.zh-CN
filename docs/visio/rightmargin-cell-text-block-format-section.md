---
title: RightMargin 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251266
localization_priority: Normal
ms.assetid: bc8f5469-e79f-4a68-73cb-d11c938353a4
description: 确定文本块的右边框和它所包含的文本之间的距离。 默认值是 0.1 英寸。
ms.openlocfilehash: 7a9d2406792e9e57c6acd0e4291b624633e70dcb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326773"
---
# <a name="rightmargin-cell-text-block-format-section"></a>RightMargin 单元格（“Text Block Format”内容）

确定文本块的右边框和它所包含的文本之间的距离。 默认值是 0.1 英寸。
  
## <a name="remarks"></a>注解

此值与绘图比例无关。即使绘图比例进行调整，右边距仍保持不变。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 RightMargin 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | RightMargin  <br/> |
   
要从某个程序按索引获取对 RightMargin 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkRightMargin** <br/> |
   

