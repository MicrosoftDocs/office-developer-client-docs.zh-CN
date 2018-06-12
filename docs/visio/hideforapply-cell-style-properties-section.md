---
title: HideForApply 单元格（“Style Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251698
localization_priority: Normal
ms.assetid: 62d87db9-b8ca-60b6-bf27-5168c718ec96
description: 确定其中 Microsoft Visio 用户界面中显示样式。
ms.openlocfilehash: 5b0221c54c17a3b9957cce5e890842def0ba7525
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780410"
---
# <a name="hideforapply-cell-style-properties-section"></a>HideForApply 单元格（“Style Properties”内容）

确定其中 Microsoft Visio 用户界面中显示样式。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 仅在**绘图资源管理器**中显示样式。  <br/> |
| FALSE  <br/> | 在**绘图资源管理器**中显示样式。  <br/> |
   
## <a name="remarks"></a>注解

如果您基于某个隐藏的样式创建新样式，则新样式并不会继承此属性。
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 HideForApply 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | HideForApply  <br/> |
   
若要从某个程序按索引获取对 HideForApply 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowStyle** <br/> |
| 单元格索引：  <br/> |**visStyleHidden** <br/> |
   

