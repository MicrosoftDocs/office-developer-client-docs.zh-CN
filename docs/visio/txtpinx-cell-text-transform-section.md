---
title: TxtPinX 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1040
localization_priority: Normal
ms.assetid: d0c0fe52-6a9e-e40e-394e-83a851db55a4
description: 确定 x-文本块的相对于原点形状的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: df103557d103dbde7e4a1c8d67cabe37a0af9311
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781570"
---
# <a name="txtpinx-cell-text-transform-section"></a>TxtPinX 单元格（“Text Transform”内容）

确定*x* -文本块的相对于原点形状的旋转中心的坐标。 默认公式为： 
  
= 宽度\*0.5
  
## <a name="remarks"></a>备注

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TxtPinX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtPinX  <br/> |
   
若要从某个程序按索引获取对 TxtPinX 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormPinX** <br/> |
   

