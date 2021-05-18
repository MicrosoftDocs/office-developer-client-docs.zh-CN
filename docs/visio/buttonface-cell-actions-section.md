---
title: ButtonFace 单元格（“Actions”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60025
localization_priority: Normal
ms.assetid: cf15b879-a47e-a5a5-bfdd-1d7ea423742f
description: 标识在快捷菜单或动作标记菜单上的项旁边显示的图标。
ms.openlocfilehash: 7ee9c4e7e857acb34ce75429aa0aaf679320b0e8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407373"
---
# <a name="buttonface-cell-actions-section"></a>ButtonFace 单元格（“Actions”内容）

标识在快捷菜单或动作标记菜单上的项旁边显示的图标。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>备注

ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。值为零 (0) 或空白表示不显示图标。 
  
ButtonFace 单元格中可以使用的 ID 与用于 **CommandBarButton** 对象的 **FaceID** 属性的 ID 相同。 有关这些 ID 的更多详细信息，请搜索 MSDN 上的"使用命令栏按钮图像"。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称来获取对 ButtonFace 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |**操作**。  *name*  . **ButtonFace**         其中 **Actions**.  *name*  是 actions 行的名称  <br/> |
   
要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction**  +  *i* 其中 **i** = 0、1、2...  <br/> |
|单元格索引：  <br/> |**visActionButtonFace** <br/> |
   

