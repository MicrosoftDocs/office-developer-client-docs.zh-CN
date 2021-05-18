---
title: UICode 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm1075
localization_priority: Normal
ms.assetid: 1d9717c1-4310-0d62-874f-4df77cd81627
description: 确定在早于 Visio 2000 的 Visio 版本中插入的域的代码。
ms.openlocfilehash: 293451b61def59ccfdf849dc597def9521fd22e5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422213"
---
# <a name="uicode-cell-text-fields-section"></a>UICode 单元格（“Text Fields”内容）

确定在早于 Visio 2000 的 Visio 版本中插入的域的代码。
  
## <a name="remarks"></a>备注

此单元格不显示在 ShapeSheet 窗口中。如果需要处理向后兼容问题，例如以 Visio 5.0 版文件格式保存 Visio 2000 版绘图，则使用此单元格。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 UICode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Fields.UICod[  *i*  ] 其中  *i*  = <1> 2， 3...  <br/> |
   
要从某个程序按索引获取对 UICode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTextField** <br/> |
| 行索引：  <br/> |**visRowField**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visFieldUICode** <br/> |
   

