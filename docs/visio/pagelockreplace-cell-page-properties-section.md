---
title: PageLockReplace 单元格（“Page Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应为该页禁用替换形状按钮。
ms.openlocfilehash: b3956b3e2f2fcd5c4f82089e08a6e32200374778
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780833"
---
# <a name="pagelockreplace-cell-page-properties-section"></a>PageLockReplace 单元格（“Page Properties”部分）

指示是否应为该页禁用**替换形状**按钮。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |此页处于活动状态时，**更改形状**按钮为灰显状态。  <br/> |
|FALSE  <br/> |此页不禁用**更改形状**按钮。 该按钮仍可能灰色如果： **DocLockReplace** **DocumentSheet**上设置为**TRUE**;选中形状的**LockReplace**单元格设置为**TRUE**。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**PageLockReplace**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLockReplace  <br/> |
   
若要从某个程序按索引获取对**PageLockReplace**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageLockReplace** <br/> |
   

