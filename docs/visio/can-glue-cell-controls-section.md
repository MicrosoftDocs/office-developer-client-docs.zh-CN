---
title: Can Glue 单元格（“Controls”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251287
localization_priority: Normal
ms.assetid: 1c4c4ae2-b3fa-ed45-c6e5-22bedb2523db
description: 确定控制手柄能否粘附到其他形状上。
ms.openlocfilehash: c7b6764e25deab3345b7b3cecd6cf12dde74a84c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779799"
---
# <a name="can-glue-cell-controls-section"></a>Can Glue 单元格（“Controls”部分）

确定控制手柄能否粘附到其他形状上。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 控制手柄能够粘附。  <br/> |
| FALSE  <br/> | 控制手柄不能粘附。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Can Glue 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 控件。  *名称*。CanGluewhere 控件。  *name*是控制行的名称。  <br/> |
   
要从某个程序按索引获取对 Can Glue 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionControls** <br/> |
| 行索引：  <br/> |**visRowControl** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCtlGlue** <br/> |
   

