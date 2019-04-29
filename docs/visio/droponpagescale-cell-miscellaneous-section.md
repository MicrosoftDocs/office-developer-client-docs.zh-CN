---
title: DropOnPageScale 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60042
localization_priority: Normal
ms.assetid: 8927f811-7d8e-ed54-9eec-b86a781168dd
ms.openlocfilehash: 17c597df3d9e7e741d902fd566cc9a5de1f31ea0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423760"
---
# <a name="droponpagescale-cell-miscellaneous-section"></a>DropOnPageScale 单元格（“Miscellaneous”内容）

包含形状在绘图页上放下时缩放比例的百分比。
  
## <a name="remarks"></a>说明

在下面两种情况下，Visio 将缩放形状，以使其适当地显示在绘图页上：
  
- 将不可测量的形状放在有比例的绘图上时。
    
- 将已测量的形状放在不成比例的绘图上时。
    
DropOnPageScale 单元格中的百分比指示 Visio 将形状放大 (\>100) 或下移 (\<100) 的因子。 在计算硬编码值时，您可以使用此数字作为因数。 
  
对于有比例绘图上的可测量形状或无比例绘图上的不可测量形状，此值是 100%。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 DropOnPageScale 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | DropOnPageScale  <br/> |
   
要从某个程序按索引获取对 DropOnPageScale 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visObjDropOnPageScale** <br/> |
   

