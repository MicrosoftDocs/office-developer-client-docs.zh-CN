---
title: PrintPageOrientation 单元格（“Print Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033795
localization_priority: Normal
ms.assetid: f8354d0d-0ce2-fb33-ddf7-611a2c24a8be
description: 确定是纵向打印页面还是横向打印页面。
ms.openlocfilehash: f7e73bea5120d878a1b2dbf553a66b349d247fce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315181"
---
# <a name="printpageorientation-cell-print-properties-section"></a>PrintPageOrientation 单元格（“Print Properties”内容）

确定是纵向打印页面还是横向打印页面。
  
|**值**|**Orientation**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 同于打印机  <br/> |**visPPOSameAsPrinter** <br/> |
| 1  <br/> | Portrait  <br/> |**visPPOPortrait** <br/> |
|双面  <br/> |现状  <br/> |**visPPOLandscape** <br/> |
   
## <a name="remarks"></a>注解

当您在文档中插入新页面时, 此设置默认为活动页面中的设置。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 PrintPageOrientation 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PrintPageOrientation  <br/> |
   
要从某个程序按索引获取对 PrintPageOrientation 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPrintProperties** <br/> |
| 单元格索引：  <br/> |**visPrintPropertiesPageOrientation** <br/> |
   

