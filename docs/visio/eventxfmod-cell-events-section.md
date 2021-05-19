---
title: EventXFMod 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251313
localization_priority: Normal
ms.assetid: b88588a2-c651-7eab-9c7a-ed78f20d1ba3
description: 一个事件单元格，当形状在页面上的位置或方向通过 XF 转换时 (计算) 。
ms.openlocfilehash: c4ed4ddd9b255a9a52fc81349b514dbd25772c98
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418531"
---
# <a name="eventxfmod-cell-events-section"></a>EventXFMod 单元格（“Events”内容）

一种事件单元格，当形状的位置或方向在绘图页上发生变化时会对它求值（“XF”）。
  
## <a name="remarks"></a>备注

只在事件发生后（而非输入公式后）才对事件单元格求值。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EventXFMod 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | EventXFMod  <br/> |
   
要从某个程序按索引获取对 EventXFMod 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowEvent** <br/> |
| 单元格索引：  <br/> |**visEvtCellXFMod** <br/> |
   

