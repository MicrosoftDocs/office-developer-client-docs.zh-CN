---
title: X 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251281
localization_priority: Normal
ms.assetid: b7aea554-f491-6a9a-4d07-feeab739a9df
description: 代表 x-指示形状的控制手柄在本地坐标系中的位置的坐标。
ms.openlocfilehash: e47b26c72709a2ee74675e73b8e8424bbfb325e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781679"
---
# <a name="x-cell-controls-section"></a>X 单元格（“Controls”部分）

代表*x* -指示形状的控制手柄在本地坐标系中的位置的坐标。 
  
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 X 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 控件。  *名称*。其中 x 控件。  *name*是控制行的名称。  <br/> |
   
要从某个程序按索引获取对 X 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCtlX** <br/> |
   

