---
title: 'PageLockReplace Cell (Page Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应该为此页禁用"替换形状"按钮。
ms.openlocfilehash: c0495d47a81ed7a23e758c531f7d754291c47852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433099"
---
# <a name="pagelockreplace-cell-page-properties-section"></a>PageLockReplace Cell (Page Properties Section) 

指示是否应该 **为此页** 禁用"替换形状"按钮。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |此页面 **处于活动状态** 时，"更改形状"按钮灰显。  <br/> |
|FALSE  <br/> |此页面 **不会** 禁用"更改形状"按钮。 如果 **DocumentSheet** 上的 **DocLockReplace** 设置为 **TRUE，** 该按钮可能仍显示为灰色;所选 **形状的 LockReplace** 单元格设置为 **TRUE**。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **PageLockReplace** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLockReplace  <br/> |
   
若要从程序按索引获取对 **PageLockReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageLockReplace** <br/> |
   

