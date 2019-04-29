---
title: EventDrop 单元格（“Events”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm350
localization_priority: Normal
ms.assetid: f84afe83-8391-0c13-f442-ea8794b38642
description: 一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。
ms.openlocfilehash: f1433394dbd58c7c4422c6bca1e79a4f2c8e0c4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408591"
---
# <a name="eventdrop-cell-events-section"></a>EventDrop 单元格（“Events”内容）

一种事件单元格，在绘图页上放下某个形状时（或者作为实例，或者在复制或粘贴该形状时）会对其求值。
  
## <a name="remarks"></a>说明

只在事件发生后（而非输入公式后）才对事件单元格求值。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 EventDrop 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | EventDrop  <br/> |
   
要从某个程序按索引获取对 EventDrop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowEvent** <br/> |
| 单元格索引：  <br/> |**visEvtCellDrop** <br/> |
   

