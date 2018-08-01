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
ms.openlocfilehash: 2adc7dadcb3702e6c5307bb569b2ae1df7aee54e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780984"
---
# <a name="printpageorientation-cell-print-properties-section"></a>PrintPageOrientation 单元格（“Print Properties”部分）

确定是纵向打印页面还是横向打印页面。
  
|**值**|**Orientation**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 同于打印机  <br/> |**visPPOSameAsPrinter** <br/> |
| 1  <br/> | 纵向  <br/> |**visPPOPortrait** <br/> |
|2  <br/> |横向  <br/> |**visPPOLandscape** <br/> |
   
## <a name="remarks"></a>说明

当在文档中插入新的页面时，此设置将默认为活动页中的设置。
  
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
   

