---
title: DocLockDuplicatePage 单元格（“Document Properties”部分）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b08a6558-519f-44e0-aeff-9919544d515e
description: 确定是否在文档中的页面可以进行复制，作为一个布尔值。
ms.openlocfilehash: 97bca23a7dc9150f66eb0c87834fca72c215448b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780116"
---
# <a name="doclockduplicatepage-cell-document-properties-section"></a>DocLockDuplicatePage 单元格（“Document Properties”部分）

确定是否在文档中的页面可以进行复制，作为一个布尔值。
  
|||
|:-----|:-----|
|TRUE  <br/> |页面的快捷菜单和**Page.Duplicate**自动化方法中的**重复**将被禁用。  <br/> |
|FALSE  <br/> |可以复制页面。  <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式，由**N** **单元格**元素的属性的值或使用**CellsU**属性从某个程序按名称获取对**DocLockDuplicatePage**单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DocLockDuplicatePage  <br/> |
   
若要从某个程序按索引获取对**DocLockDuplicatePage**单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocLockDuplicatePage** <br/> |
   

