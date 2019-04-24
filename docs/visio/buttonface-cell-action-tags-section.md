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
ms.openlocfilehash: e74b3281d894cebd8491112181198d427f0d337f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337534"
---
# <a name="buttonface-cell-action-tags-section"></a>ButtonFace 单元格（“Action Tags”内容）

包含动作标记按钮上显示的按钮外表图像的 ID。 
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
## <a name="remarks"></a>注解

ButtonFace 单元格中包含的字符串表示 Microsoft Office 按钮外表图像的 ID。 值为 0 (零) 或空白默认值为标准操作标记 "i" 信息按钮 ![标准操作标记 "i" 信息按钮](media/InfoPS_ZA10180114.gif).
  
ButtonFace 单元格中可以使用的 ID 与用于 **CommandBarButton** 对象的 **FaceID** 属性的 ID 相同。 有关这些 id 的更多详细信息, 请在 MSDN 上搜索 "使用命令栏按钮图像"。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取有关 ButtonFace 单元格的参考内容，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SmartTags.  *名称*。ButtonFace 其中的智能标记。 *name*是操作标记行的名称  <br/> |
   
要从某个程序按索引获取有关 ButtonFace 单元格的参考内容，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visSmartTagButtonFace** <br/> |
   

