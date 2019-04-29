---
title: BeginGroup 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60022
localization_priority: Normal
ms.assetid: 1ae7f629-fb9f-1a11-1194-b381d6c9de5b
description: 指示是否在此动作之上的菜单中插入分隔符。
ms.openlocfilehash: 115dbfe051201dc3ec2b127ff129b077e1067865
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407835"
---
# <a name="begingroup-cell-actions-section"></a>BeginGroup 单元格（“Actions”内容）

指示是否在此动作之上的菜单中插入分隔符。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |在此动作之上的菜单中插入分隔符。  <br/> |
|FALSE  <br/> |未在此动作之上的菜单中插入分隔符（默认值）。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BeginGroup 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作. *名称*。BeginGroup 其中的操作。 *name* 是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 BeginGroup 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visActionBeginGroup** <br/> |
   

