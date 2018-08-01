---
title: FlyoutChild 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80003
localization_priority: Normal
ms.assetid: b2405457-843c-0d46-5f4f-9c413826c3f1
description: 确定该行是否为不是弹出子菜单的上一行的弹出子菜单。
ms.openlocfilehash: 8a41721f91fa9632246e512cfd4ba1a2d871ece5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780276"
---
# <a name="flyoutchild-cell-actions-section"></a>FlyoutChild 单元格（“Actions”部分）

确定该行是否为不是弹出子菜单的上一行的弹出子菜单。 
  
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 FlyoutChild 单元格的引用，请使用以下内容。 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |操作。 *名称*。FlyoutChildwhere 操作。  *name*是 Actions 行的名称  <br/> |
   
若要从某个程序按索引获取对 FlyoutChild 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionFlyoutChild** <br/> |
   

