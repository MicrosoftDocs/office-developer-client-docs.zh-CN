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
description: 确定匹配连接点所需的对齐向量的 y 分量。 它还用于确定动态连接线所附引线的方向。 此单元格采用浮点值。
ms.openlocfilehash: b0dc3c9f7e1a9e87b2ecdace21c8fa1658b1388d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332583"
---
# <a name="diry--b-cell-connection-points-section"></a>DirY / B 单元格（“Connection Points”内容）

确定匹配连接点所需的对齐向量的*y*分量。 它还用于确定动态连接线所附引线的方向。 此单元格采用浮点值。 
  
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DirY / B 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DirY [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 DirY / B 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionConnectionPts** <br/> |
|行索引：  <br/> |**visRowConnectionPts** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visCnnctDirY**(非扩展行)          **visCnnctB**(扩展行)  <br/> |
   
有关扩展行和非扩展行的信息，请参见 Connection Points 行。
  

