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
ms.openlocfilehash: 29ff71bc04e94f97f1526b28bd52c2846327eff1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779806"
---
# <a name="buttonface-cell-actions-section"></a>ButtonFace 单元格（“Actions”部分）

标识在快捷菜单或动作标记菜单上的项旁边显示的图标。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注解

ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。值为零 (0) 或空白表示不显示图标。 
  
可在 ButtonFace 单元格的 Id 是与**CommandBarButton**对象的**FaceID**属性一起使用的 Id 相同。 关于这些 Id 的详细信息，请在 MSDN 上中搜索"命令栏按钮图像处理"。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称来获取对 ButtonFace 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |**操作**。  *名称*。 **ButtonFace**其中**操作**。  *name*是 actions 行的名称  <br/> |
   
要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionAction** <br/> |
|行索引：  <br/> |**visRowAction** +  *i*其中**i** = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visActionButtonFace** <br/> |
   

