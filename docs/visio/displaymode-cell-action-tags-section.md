---
title: 'DisplayMode Cell (Action Tags Section) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60039
localization_priority: Normal
ms.assetid: 0dfad40b-f97e-0c4a-2102-7344d1317b82
description: 确定当用户将指针移动到标记上时、选择形状时还是所有时间都显示动作标记。
ms.openlocfilehash: 0254ad361c63dfdeddaf8a1c2173e99aa1c05398
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415815"
---
# <a name="displaymode-cell-action-tags-section"></a>DisplayMode Cell (Action Tags Section) 

确定当用户将指针移动到标记上时、选择形状时还是所有时间都显示动作标记。
  
> [!NOTE]
> 在以前版本的 Microsoft Visio 中，动作标记称为“智能标记”。 
  
|**值**|**显示模式**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 将鼠标暂停到默认标记的标记 (显示) 。  <br/> |**visSmartTagDispModeMouseOver** <br/> |
| 1  <br/> | 选择形状后显示。  <br/> |**visSmartTagDispModeShapeSelected** <br/> |
| 2  <br/> | 始终显示。  <br/> |**visSmartTagDispModeAlways** <br/> |
   
## <a name="remarks"></a>备注

打印输出或发布输出上不显示动作标记。 
  
如果为某一页定义了动作标记，并且此单元格包含值 1，则此标记永远也不会显示，因为不能选择页。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DisplayMode 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | SmartTags。  *name*  .其中 SmartTags 的 DisplayMode。 *name*  是动作标记行的名称  <br/> |
   
要从某个程序按索引获取对 DisplayMode 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionSmartTag** <br/> |
| 行索引：  <br/> |**visRowSmartTag**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visSmartTagDisplayMode** <br/> |
   

