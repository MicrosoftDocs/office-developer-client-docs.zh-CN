---
title: DirX / A 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251721
localization_priority: Normal
ms.assetid: 00d87b92-0da7-37d6-e7b5-23f350db0a9b
description: 确定 x-组件所需的对齐向量的匹配连接点。 DirX / A 单元格还用于确定动态连接线的附加的线路。 此单元格采用浮点数据点值。
ms.openlocfilehash: 49feba7cefbccc4efcbd04e8940c1f801563539e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780115"
---
# <a name="dirx--a-cell-connection-points-section"></a>DirX / A 单元格（“Connection Points”部分）

确定*x* -组件所需的对齐向量的匹配连接点。 DirX / A 单元格还用于确定动态连接线的附加的线路。 此单元格采用浮点数据点值。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DirX / A 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Connections.DirX [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 DirX / A 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionConnectionPts** <br/> |
| 行索引：  <br/> |**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2  <br/> |
| 单元格索引：  <br/> |**visCnnctDirX**（非扩展行）          **visCnnctA**（扩展的行）  <br/> |
   
有关扩展行和非扩展行的信息，请参见 Connection Points 行。
  

