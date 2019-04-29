---
title: Y Dynamics 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251284
localization_priority: Normal
ms.assetid: cb221974-2f1a-edb0-477b-39a3c4a64c56
description: 表示控制手柄的锚点在本地坐标系中的 y 坐标。 锚点用于动态过程中类似橡皮筋的固定点。
ms.openlocfilehash: 13d463ebccd9cc7a23641a036dc5dd967513b07f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404825"
---
# <a name="y-dynamics-cell-controls-section"></a>Y Dynamics 单元格（“Controls”内容）

表示控制手柄的锚点在本地坐标系中的*y*坐标。 锚点用于动态过程中类似橡皮筋的固定点。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Y Dynamics 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 措施.  *名称*。YDynwhere 控件。  *名称*是控件行的名称。  <br/> |
   
要从某个程序按索引获取对 Y Dynamics 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visCtlYDyn** <br/> |
   

