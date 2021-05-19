---
title: ObjType 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm745
localization_priority: Normal
ms.assetid: 3afee07b-e91a-a91c-fba2-0e3251dd6385
description: 确定当使用“配置布局”对话框排放形状时对象在图表中是可放置的还是可穿绕的。
ms.openlocfilehash: 7a607fdb53ad569e84976b6f9911fbd89f7f2628
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425727"
---
# <a name="objtype-cell-miscellaneous-section"></a>ObjType 单元格（“Miscellaneous”内容）

确定当使用 **“配置布局”** 对话框排放形状时对象在图表中是可放置的还是可穿绕的。 
  
|**值**|**说明**|**自动常量**|
|:-----|:-----|:-----|
|&amp;H0  <br/> |默认值。应用程序根据绘图上下文决定。  <br/> |**visLOFlagsVisDecides** <br/> |
|&amp;H1  <br/> |形状是可放置的。  <br/> |**visLOFlagsPlacable** <br/> |
|&amp;H2  <br/> |形状是可穿绕的。必须是一维 (1-D) 形状。  <br/> |**visLOFlagsRoutable** <br/> |
|&amp;H4  <br/> |形状是不可放置且不可穿绕的。  <br/> |**visLOFlagsDont** <br/> |
|&amp;H8  <br/> |组合包含可放置/可穿绕的形状。  <br/> |**visLOFlagsPNRGroup** <br/> |
   
## <a name="remarks"></a>备注

默认情况下，形状的 ObjType 单元格设置为“No Formula”，其计算结果为 0，意味着由应用程序根据其上下文决定该形状能否放置。例如，如果您绘制了一个简单的矩形，它的 ObjType 单元格的值为 0。如果您接着用 **“连接线”** 工具将该矩形连接到另一个形状，Visio 就会将该矩形的 ObjType 单元格的值重新设置为 1（可放置）。 
  
ObjType 单元格的值可以是几个值的组合。 但是，如果将不可放置的位设置为 (H4) ，则它优先于除组值 &amp; &amp; H8 (值) 。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 ObjType 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ObjType  <br/> |
   
若要从某个程序按索引获取对 ObjType 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visLOFlags** <br/> |
   

