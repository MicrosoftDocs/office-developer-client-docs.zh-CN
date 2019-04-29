---
title: BeginArrowSize 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251629
localization_priority: Normal
ms.assetid: bfddb829-6e13-7d74-b9b9-2cb5c0937bae
description: 确定线条起始处的箭头大小。
ms.openlocfilehash: 9c1288ced747c4e16090013cc043b040f1fbb59c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412280"
---
# <a name="beginarrowsize-cell-line-format-section"></a>BeginArrowSize 单元格（“Line Format”内容）

确定线条起始处的箭头大小。
  
|**值**|**Size**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 非常小  <br/> |**visArrowSizeVerySmall** <br/> |
| 1  <br/> | 小型  <br/> |**visArrowSizeSmall** <br/> |
| 双面  <br/> | 中等  <br/> |**visArrowSizeMedium** <br/> |
| 第三章  <br/> | 大型  <br/> |**visArrowSizeLarge** <br/> |
| 4  <br/> | 非常大  <br/> |**visArrowSizeVeryLarge** <br/> |
| 5  <br/> | 超长  <br/> |**visArrowSizeJumbo** <br/> |
| 型  <br/> | Colossal  <br/> |**visArrowSizeColossal** <br/> |
   
## <a name="remarks"></a>说明

您还可以在 **“线条”** 对话框中设置箭头的大小。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BeginArrowSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BeginArrowSize  <br/> |
   
要从某个程序按索引获取对 BeginArrowSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowLine** <br/> |
| 单元格索引：  <br/> |**visLineBeginArrowSize** <br/> |
   

