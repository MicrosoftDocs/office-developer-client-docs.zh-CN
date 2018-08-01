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
ms.openlocfilehash: c238b6b2a47c968809869f8eb3e38b6f0db1dcad
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781513"
---
# <a name="textdirection-cell-text-block-format-section"></a>TextDirection 单元格（“Text Block Format”部分）

确定文本块中字符的方向。
  
|**值**|**Direction**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 水平  <br/> |**visTxtBlkLeftToRight** <br/> |
| 1  <br/> | 垂直  <br/> |**visTxtBlkTopToBottom** <br/> |
   
## <a name="remarks"></a>注释

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
   

