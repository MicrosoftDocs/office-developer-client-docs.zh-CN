---
title: Y 单元格（“Connection Points”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_SDR.chm1175
localization_priority: Normal
ms.assetid: 3af6c949-d6a0-9560-54d7-b01a2ad99960
description: 表示连接点在本地坐标系中的 y 坐标。
ms.openlocfilehash: b408dc3c07e7bd28c0530b09f649453b4f08c770
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410845"
---
# <a name="y-cell-connection-points-section"></a>Y 单元格（“Connection Points”内容）

表示连接点在本地坐标系中的*y*坐标。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 连接。 Y *i*其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 Y 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionConnectionPts** <br/> |
| 行索引：  <br/> |**visRowConnectionPts** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visY** <br/> |
   

