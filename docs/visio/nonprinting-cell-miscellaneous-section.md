---
title: NonPrinting 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251321
localization_priority: Normal
ms.assetid: 59fe0887-2092-4fad-ea38-2aba354f3b92
description: 切换选中形状的打印状态 - 启用或禁用。
ms.openlocfilehash: c3e1fc1b2d91fa4808f8ea89c904218c2236f5b0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437257"
---
# <a name="nonprinting-cell-miscellaneous-section"></a>NonPrinting 单元格（“Miscellaneous”内容）

切换选中形状的打印状态 - 启用或禁用。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 禁用打印，但形状将显示在绘图窗口中。  <br/> |
| FALSE  <br/> | 启用打印。  <br/> |
   
## <a name="remarks"></a>说明

可以通过先选中参考线，再将其 NonPrinting 单元格的值设置为 FALSE 来打印参考线。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 NonPrinting 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 打印  <br/> |
   
要从某个程序按索引获取对 NonPrinting 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visNonPrinting** <br/> |
   

