---
title: PageLockReplace 单元格 ("Page Properties" 内容)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 59c36555-42af-4729-aea7-0332d1da6e3b
description: 指示是否应对此页面禁用 "替换形状" 按钮。
ms.openlocfilehash: c0495d47a81ed7a23e758c531f7d754291c47852
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433099"
---
# <a name="pagelockreplace-cell-page-properties-section"></a>PageLockReplace 单元格 ("Page Properties" 内容)

指示是否应对此页面禁用 "**替换形状**" 按钮。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |当此页面处于活动状态时, "**更改形状**" 按钮将变灰。  <br/> |
|FALSE  <br/> |此页面未禁用 "**更改形状**" 按钮。 如果: **DocumentSheet**上的**DocLockReplace**设置为**TRUE**, 则该按钮可能仍为灰色;选定形状的**LockReplace**单元格设置为**TRUE**。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式按名称获取对**PageLockReplace**单元格的引用、 **cell**元素的**N**属性值, 或从使用**CellsU**属性的某个程序获取对该单元格的引用, 请使用: 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLockReplace  <br/> |
   
若要从某个程序按索引获取对**PageLockReplace**单元格的引用, 请使用带下列参数的**CellsSRC**属性: 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageLockReplace** <br/> |
   

