---
title: ButtonFace 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60026
localization_priority: Normal
ms.assetid: 26f370e1-5193-f47d-7b60-3597975be650
description: 包含动作标记按钮上显示的按钮外表图像的 ID。
ms.openlocfilehash: ca6be0a95b33e173219f4bdc1ba042c7162941b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779807"
---
# <a name="buttonface-cell-action-tags-section"></a>ButtonFace 单元格（“Action Tags”内容）

包含动作标记按钮上显示的按钮外表图像的 ID。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注释

ButtonFace 单元格中包含的字符串表示的 Microsoft Office 按钮外表图像的 ID。 值为 0 （零） 或空白默认标准动作标记"i"信息按钮![](media/InfoPS_ZA10180114.gif)。
  
可在 ButtonFace 单元格的 Id 是与**CommandBarButton**对象的**FaceID**属性一起使用的 Id 相同。 关于这些 Id 的详细信息，请在 MSDN 上中搜索"命令栏按钮图像处理"。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 ButtonFace 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 智能标记。  *名称*。ButtonFace 其中智能标记。 *name*是动作标记行的名称  <br/> |
   
若要从某个程序按索引获取对 ButtonFace 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visSmartTagButtonFace** <br/> |
   

