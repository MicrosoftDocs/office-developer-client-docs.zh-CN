---
title: UIFormat 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1080
localization_priority: Normal
ms.assetid: 0dddef20-c58e-2306-ab8e-6cac8e159f61
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的格式。
ms.openlocfilehash: e9506404e8ccd6ae4452c10ecdcce2d4dfd7ac2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781609"
---
# <a name="uiformat-cell-text-fields-section"></a>UIFormat 单元格（“Text Fields”部分）

确定在早于 Visio 2000 的 Visio 版本中插入的域的格式。
  
## <a name="remarks"></a>注释

此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UIFormat 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Fields.UIFmt [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
要从某个程序按索引获取对 UIFormat 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTextField** <br/> |
| 行索引：  <br/> |**visRowField** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visFieldUIFormat** <br/> |
   

