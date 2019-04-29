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
ms.openlocfilehash: 137d22430829f96a9c6ad69a73a6b44e964d5f4f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422986"
---
# <a name="value-cell-user-defined-cells-section"></a>Value 单元格（“User-Defined Cells”内容）

为相应的用户定义的单元格指定值。
  
## <a name="remarks"></a>说明

要在其他单元格中引用该值，请指定在行标签 User.Row 中输入的用户定义的名称。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Value 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | User.  *名称*。用户的值。  *名称*是行名称  <br/> |
   
要从某个程序按索引获取对 Value 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionUser** <br/> |
| 行索引：  <br/> |**visRowUser** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visUserValue** <br/> |
   

