---
title: X 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251746
localization_priority: Normal
ms.assetid: 11c69600-4e1f-4c52-ff35-b6a7cc6c734c
description: 代表 x-在本地坐标系中的连接点的坐标。
ms.openlocfilehash: 27821f9aa94f97d8e019d7c7307c036549bf807b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781674"
---
# <a name="x-cell-connection-points-section"></a>X 单元格（“Connection Points”部分）

代表*x* -在本地坐标系中的连接点的坐标。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 创建两个*i*其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionConnectionPts** <br/> |
| 行索引：  <br/> |**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visX** <br/> |
   

