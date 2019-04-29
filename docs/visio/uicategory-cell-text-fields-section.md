---
title: UICategory 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1070
localization_priority: Normal
ms.assetid: 365f7005-ba34-2311-4c5c-16344962fc3f
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的类别。
ms.openlocfilehash: c67ced9e4f731e66bce0589929ac90fb9bb8d67c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434023"
---
# <a name="uicategory-cell-text-fields-section"></a>UICategory 单元格（“Text Fields”内容）

确定在早于 Visio 2000 的 Visio 版本中插入的域的类别。
  
## <a name="remarks"></a>说明

此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UICategory 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | UICat [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 UICategory 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTextField** <br/> |
| 行索引：  <br/> |**visRowField** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visFieldUICategory** <br/> |
   

