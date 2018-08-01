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
ms.openlocfilehash: cfd34f17eec597c306b69f76929877013b39015e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781637"
---
# <a name="verticalalign-cell-text-block-format-section"></a>VerticalAlign 单元格（“Text Block Format”部分）

确定文本块内文本的垂直对齐方式。
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 靠上  <br/> |**visVertTop** <br/> |
| 1  <br/> | 居中  <br/> |**visVertMiddle** <br/> |
| 2  <br/> | 靠下  <br/> |**visVertBottom** <br/> |
   
## <a name="remarks"></a>说明

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
   

