---
title: BeginArrow 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm51105
localization_priority: Normal
ms.assetid: 0ab4044e-2d77-1fbe-ef20-5d029bc064ba
description: 指明线条的第一个顶点是否有箭头或其他线端格式。 输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用“线条”对话框。
ms.openlocfilehash: cf5a512dabd0e6296b83fa7bfd2a2a6134143d50
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410292"
---
# <a name="beginarrow-cell-line-format-section"></a>BeginArrow 单元格（“Line Format”内容）

指明线条的第一个顶点是否有箭头或其他线端格式。输入介于 0 到 45 之间的数字或带有自定义线端名的 USE 函数，或使用 **“线条”** 对话框。 
  
|**值**|**说明**|
|:-----|:-----|
| 0  <br/> | 无箭头。  <br/> |
| 1 - 45  <br/> | 各种类型的箭头样式，与 **“线条”** 对话框中的索引项相对应。  <br/> |
   
## <a name="remarks"></a>说明

箭头的大小在 BeginArrowSize 单元格中设置。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BeginArrow 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BeginArrow  <br/> |
   
要从某个程序按索引获取对 BeginArrow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visLineBeginArrow** <br/> |
   

