---
title: EventMultiDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f496d698-7f08-69cc-4379-df18a2c2fd7e
ms.openlocfilehash: caa86e33d0d7aa9ca31cbbf8939e17b581877669
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337189"
---
# <a name="eventmultidrop-cell-events-section"></a>EventMultiDrop 单元格（“Events”内容）

当多个形状作为实例放置在绘图页上或者在复制或粘贴形状时计算的事件单元格。
  
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
   

