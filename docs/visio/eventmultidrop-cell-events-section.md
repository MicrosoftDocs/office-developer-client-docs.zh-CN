---
title: EventMultiDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f496d698-7f08-69cc-4379-df18a2c2fd7e
ms.openlocfilehash: e44cd18c3f7673761f457db9cd4bfe00a8ab89bc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780207"
---
# <a name="eventmultidrop-cell-events-section"></a>EventMultiDrop 单元格（“Events”部分）

一种事件单元格的多个形状放在绘图页上，或者作为实例时复制或粘贴形状时计算。
  
只在事件发生后（而非输入公式后）才对事件单元格求值。
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称引用 EventMultiDrop 单元格，请使用：

 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EventMultiDrop  <br/> |
   
若要从某个程序按索引引用 EventMultiDrop 单元格，请使用带下列参数的 **CellsSRC** 属性：

 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowEvent** <br/> |
|单元格索引：  <br/> |**visEvtCellMultiDrop** <br/> |
   

