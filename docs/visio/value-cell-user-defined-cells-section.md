---
title: Value 单元格（“User-Defined Cells”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1100
localization_priority: Normal
ms.assetid: 495b2aec-e197-75eb-9974-e7c92d26546f
description: 为相应的用户定义的单元格指定值。
ms.openlocfilehash: d320c35fa8ae65dd0b21a83ad2cf23dbb3af77f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781623"
---
# <a name="value-cell-user-defined-cells-section"></a>Value 单元格（“User-Defined Cells”部分）

为相应的用户定义的单元格指定值。
  
## <a name="remarks"></a>注释

要在其他单元格中引用该值，请指定在行标签 User.Row 中输入的用户定义的名称。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 用户。  *名称*。值的位置用户。  *Name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionUser** <br/> |
| 行索引：  <br/> |**visRowUser** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visUserValue** <br/> |
   

