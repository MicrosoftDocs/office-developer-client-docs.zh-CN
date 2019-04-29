---
title: Checked 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm155
localization_priority: Normal
ms.assetid: 50937e29-eaa1-0cd0-53cc-dc17e7793e55
description: 指示是否在快捷菜单或动作标记菜单上选取了某项。
ms.openlocfilehash: 870823f28d802e7cafa81efbe5617f27b6714885
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438328"
---
# <a name="checked-cell-actions-section"></a>Checked 单元格（“Actions”内容）

指示是否在快捷菜单或动作标记菜单上选取了某项。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |显示复选标记。  <br/> |
|FALSE  <br/> |不显示复选标记（默认值）。  <br/> |
   
## <a name="remarks"></a>说明

若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Checked 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作. *名称*。检查 where 操作。 *name*是操作行的名称  <br/> |
   
要从某个程序按索引获取对 Checked 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visActionChecked** <br/> |
   

