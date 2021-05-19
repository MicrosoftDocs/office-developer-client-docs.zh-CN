---
title: Invisible 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60046
localization_priority: Normal
ms.assetid: 070b4468-c907-b201-1633-1d3e10ecc2b2
description: 指示动作标记或快捷菜单上是否显示动作。
ms.openlocfilehash: 69bc96e76f27a64d6e1443f045c27566f598c1db
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423872"
---
# <a name="invisible-cell-actions-section"></a>Invisible 单元格（“Actions”内容）

指示动作标记或快捷菜单上是否显示动作。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |菜单上不显示动作。  <br/> |
|FALSE  <br/> |菜单上显示动作（默认值）。  <br/> |
   
## <a name="remarks"></a>备注

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Invisible 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *name*  .在 Actions 中不可见。  *name*  是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction**  +  *i* 其中 *i* = 0、1、2...  <br/> |
|单元格索引：  <br/> |**visActionInvisible** <br/> |
   

