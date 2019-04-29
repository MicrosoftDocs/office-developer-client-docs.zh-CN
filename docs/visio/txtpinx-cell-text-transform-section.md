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
description: 确定文本块的旋转中心相对于形状原点的 x 轴坐标值。 默认公式为：
ms.openlocfilehash: 836f5c807d0c0e53efc825f62f60429274282165
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423494"
---
# <a name="txtpinx-cell-text-transform-section"></a>TxtPinX 单元格（“Text Transform”内容）

确定文本块的旋转中心相对于形状原点的*x*轴坐标值。 默认公式为： 
  
= 宽度\* 0。5
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtPinX 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtPinX  <br/> |
   
要从某个程序按索引获取对 TxtPinX 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormPinX** <br/> |
   

