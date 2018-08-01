---
title: DirY / B 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm240
localization_priority: Normal
ms.assetid: d951c57d-2c22-0289-35af-44e3c2877b2c
description: 确定 y-组件所需的对齐向量的匹配连接点。 此外可用于确定动态连接线的附加的线路的方向。 此单元格采用浮点数据点值。
ms.openlocfilehash: e650e598b1e47d666b2700d683a17300d3a8e67d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780086"
---
# <a name="diry--b-cell-connection-points-section"></a>DirY / B 单元格（“Connection Points”部分）

确定*y* -组件所需的对齐向量的匹配连接点。 此外可用于确定动态连接线的附加的线路的方向。 此单元格采用浮点数据点值。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DirY / B 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Connections.DirY [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 DirY / B 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionConnectionPts** <br/> |
|行索引：  <br/> |**visRowConnectionPts** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visCnnctDirY**（非扩展行）          **visCnnctB**（扩展的行）  <br/> |
   
有关扩展行和非扩展行的信息，请参见 Connection Points 行。
  

