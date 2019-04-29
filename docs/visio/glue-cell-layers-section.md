---
title: Glue 单元格（“Layers”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm415
localization_priority: Normal
ms.assetid: 75f2ea45-52ac-ddfa-14ea-402933ae2449
description: 指定是否可粘附属于图层的形状。
ms.openlocfilehash: 55886a7e96bd2c08966cb85f5edad6a7174e30cd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408514"
---
# <a name="glue-cell-layers-section"></a>Glue 单元格（“Layers”内容）

指定是否可粘附属于图层的形状。
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |启用粘附。  <br/> |
|FALSE  <br/> |禁用粘附。  <br/> |
   
## <a name="remarks"></a>说明

此单元格对应于 "**图层属性**" 对话框 (在 "**开始**" 选项卡上的 "**编辑**" 组中, 单击 "**层**", 然后单击 "**图层属性**") 中的 "**粘附**" 选项。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Glue 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |图: 粘附 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Glue 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionLayer** <br/> |
|行索引：  <br/> |**visRowLayer** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visLayerGlue** <br/> |
   

