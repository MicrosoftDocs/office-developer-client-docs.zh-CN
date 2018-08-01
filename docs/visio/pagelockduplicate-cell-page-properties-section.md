---
title: PageLockDuplicate 单元格（“Page Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fbaa7d64-06ef-46d6-81d5-9d7af1c14b65
description: 确定是否页面可以进行复制，作为一个布尔值。
ms.openlocfilehash: 6cfe8f7a33942f51130ef103b8aba70a5c38b37d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780827"
---
# <a name="pagelockduplicate-cell-page-properties-section"></a>PageLockDuplicate 单元格（“Page Properties”部分）

确定是否页面可以进行复制，作为一个布尔值。
  
|||
|:-----|:-----|
|TRUE  <br/> |页面的快捷菜单和**Page.Duplicate**自动化方法中的**重复**会同时禁用页面。  <br/> |
|FALSE  <br/> |可以复制页面。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**PageLockDuplicate**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | PageLockDuplicate  <br/> |
   
若要从某个程序按索引获取对**PageLockDuplicate**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowPage** <br/> |
| 单元格索引：  <br/> |**visPageLockDuplicate** <br/> |
   

