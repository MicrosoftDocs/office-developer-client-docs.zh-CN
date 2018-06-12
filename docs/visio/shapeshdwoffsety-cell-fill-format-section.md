---
title: ShapeShdwOffsetY 单元格（“Fill Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60077
localization_priority: Normal
ms.assetid: ef200f41-7b69-1291-f9df-a7035239a033
description: 确定形状的阴影与该形状垂直偏移的距离（按页面单位）。
ms.openlocfilehash: 669e15fd1badf9cf76decb117a9c4fb91e731271
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781288"
---
# <a name="shapeshdwoffsety-cell-fill-format-section"></a>ShapeShdwOffsetY 单元格（“Fill Format”内容）

确定形状的阴影与该形状垂直偏移的距离（按页面单位）。
  
## <a name="remarks"></a>注解

此值对应于**阴影**对话框中的**y 轴偏移**设置中的值 （在**主页**选项卡，**形状**组中，单击**阴影**，然后单击**阴影选项**）。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ShapeShdwOffsetY 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ShapeShdwOffsetY  <br/> |
   
若要从某个程序按索引获取对 ShapeShdwOffsetY 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowFill** <br/> |
| 单元格索引：  <br/> |**visFillShdwOffsetY** <br/> |
   

