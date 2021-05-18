---
title: TextDirection 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm995
localization_priority: Normal
ms.assetid: 1df3a50e-7ea5-9244-1286-c1d00c217a9a
description: 确定文本块中字符的方向。
ms.openlocfilehash: 559a2930d9ef62612cabab79ccf55ca2c30e877b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406225"
---
# <a name="textdirection-cell-text-block-format-section"></a>TextDirection 单元格（“Text Block Format”内容）

确定文本块中字符的方向。
  
|**值**|**方向**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 水平  <br/> |**visTxtBlkLeftToRight** <br/> |
| 1  <br/> | 垂直  <br/> |**visTxtBlkTopToBottom** <br/> |
   
## <a name="remarks"></a>备注

在 Visio 5.0 日语版产品中，此单元格的值存储在“Miscellaneous”内容的 VerticalText 单元格中。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TextDirection 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TextDirection  <br/> |
   
要从某个程序按索引获取对 TextDirection 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowText** <br/> |
| 单元格索引：  <br/> |**visTxtBlkDirection** <br/> |
   

