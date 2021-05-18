---
title: 'DocLockReplace Cell (Document Properties Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 74eae5e5-80ab-4e10-b292-e58a6d7607d2
description: 确定是否应禁用此文档的替换形状 UI。
ms.openlocfilehash: cfec9b3c51a170c549fdd0d1b0b3597c030c410c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413421"
---
# <a name="doclockreplace-cell-document-properties-section"></a>DocLockReplace Cell (Document Properties Section) 

确定是否应禁用此文档的替换形状 UI。 
  
|||
|:-----|:-----|
|TRUE  <br/> |" **替换形状"** 按钮在 UI 中灰显。  <br/> |
|FALSE  <br/> |" **替换形状"** 按钮在 UI 中处于活动状态。 用户可以使用本文档中的"替换形状"功能。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式 **、Cell** 元素 **的 N** 属性值或使用 **CellsU** 属性从某个程序按名称获取对 **DocLockReplace** 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DocLocReplace  <br/> |
   
若要从程序按索引获取对 **DocLocReplace** 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowDoc** <br/> |
| 单元格索引：  <br/> |**visDocLockReplace ** <br/> |
   

