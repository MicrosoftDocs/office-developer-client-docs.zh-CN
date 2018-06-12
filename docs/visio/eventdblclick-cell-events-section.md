---
title: EventDblClick 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251312
localization_priority: Normal
ms.assetid: ca949013-f998-1bce-39e5-ac6f68ab2392
description: 一种事件单元格，双击某个形状后会对其求值。
ms.openlocfilehash: 623d1d095d3269cd9c82fa8d0d6601933a163f92
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780192"
---
# <a name="eventdblclick-cell-events-section"></a>EventDblClick 单元格（“Events”内容）

一种事件单元格，双击某个形状后会对其求值。
  
## <a name="remarks"></a>注释

只在事件发生后（而非输入公式后）才对事件单元格求值。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 EventDblClick 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | EventDblClick  <br/> |
   
若要从某个程序按索引获取对 EventDblClick 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowEvent** <br/> |
| 单元格索引：  <br/> |**visEvtCellDblClick** <br/> |
   

