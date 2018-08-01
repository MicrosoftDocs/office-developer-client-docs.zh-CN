---
title: TxtPinY 单元格（“Text Transform”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1045
localization_priority: Normal
ms.assetid: 88ddf4b5-8248-8c1a-c387-09a607639d26
description: 确定 y-文本块的相对于原点形状的旋转中心的坐标。 默认公式为：
ms.openlocfilehash: e8101463413b177bf8ddd80ed52964d3eeae788f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781576"
---
# <a name="txtpiny-cell-text-transform-section"></a>TxtPinY 单元格（“Text Transform”部分）

确定*y* -文本块的相对于原点形状的旋转中心的坐标。 默认公式为： 
  
= 高度\*0.5
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TxtPinY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TxtPinY  <br/> |
   
要从某个程序按索引获取对 TxtPinY 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowTextXForm** <br/> |
| 单元格索引：  <br/> |**visXFormPinY** <br/> |
   

