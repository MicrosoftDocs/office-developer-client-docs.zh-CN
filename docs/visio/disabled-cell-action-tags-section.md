---
title: Disabled 单元格（“Action Tags”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60038
localization_priority: Normal
ms.assetid: bf0a80c9-0fdb-e2cf-3ab0-74cb6338fdce
description: 指示动作标记是否在绘图窗口中显示。
ms.openlocfilehash: 409327365f3daf78dba20b1874be5911a517df0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780095"
---
# <a name="disabled-cell-action-tags-section"></a>Disabled 单元格（“Action Tags”部分）

指示动作标记是否在绘图窗口中显示。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 禁用动作标记。  <br/> |
| FALSE  <br/> | 启用动作标记（默认值）。  <br/> |
   
## <a name="remarks"></a>注释

动作标记被禁用后，在重新启用之前完全不显示。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Disabled 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 智能标记。  *名称*。其中禁用智能标记。 *name*是动作标记行的名称  <br/> |
   
要从某个程序按索引获取对 Disabled 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visSmartTagDisabled** <br/> |
   

