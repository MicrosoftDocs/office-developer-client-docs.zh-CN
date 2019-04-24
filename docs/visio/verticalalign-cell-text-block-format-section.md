---
title: VerticalAlign 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1105
localization_priority: Normal
ms.assetid: ff34a23b-2881-864f-42e4-871c4fde0992
description: 确定文本块内文本的垂直对齐方式。
ms.openlocfilehash: 954a0cf0b80d6b675dcc016997f1923041069eac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356139"
---
# <a name="verticalalign-cell-text-block-format-section"></a>VerticalAlign 单元格（“Text Block Format”内容）

确定文本块内文本的垂直对齐方式。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | Top  <br/> |**visVertTop** <br/> |
| 1  <br/> | 中间  <br/> |**visVertMiddle** <br/> |
| 双面  <br/> | 向下  <br/> |**visVertBottom** <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 VerticalAlign 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | VerticalAlign  <br/> |
   
要从某个程序按索引获取对 VerticalAlign 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkVerticalAlign** <br/> |
   

