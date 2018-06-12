---
title: Disabled 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251337
localization_priority: Normal
ms.assetid: ebf66729-d794-a398-268a-84d761bf06b6
description: 指示快捷菜单或动作标记菜单上的某项是否被禁用。
ms.openlocfilehash: 3956b6cf5ccb870255d6943e74b4f02650952d09
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780091"
---
# <a name="disabled-cell-actions-section"></a>Disabled 单元格（“Actions”内容）

指示快捷菜单或动作标记菜单上的某项是否被禁用。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |禁用（灰显）命令名。  <br/> |
|FALSE  <br/> |启用命令名（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

若要获取对 Disabled 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *名称*。其中禁用操作。 *name*是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 Disabled 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionDisabled** <br/> |
   

