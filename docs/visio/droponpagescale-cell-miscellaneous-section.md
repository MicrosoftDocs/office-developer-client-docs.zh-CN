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
ms.openlocfilehash: a586cca497e1ba04848142917a84c3aa8a25d081
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780141"
---
# <a name="droponpagescale-cell-miscellaneous-section"></a>DropOnPageScale 单元格（“Miscellaneous”部分）

包含形状在绘图页上放下时缩放比例的百分比。
  
## <a name="remarks"></a>注释

在下面两种情况下，Visio 将缩放形状，以使其适当地显示在绘图页上：
  
- 将不可测量的形状放在有比例的绘图上时。
    
- 测量的形状放在上时无比例的绘图。
    
DropOnPageScale 单元格中的百分比指示 Visio 缩放形状，或者 up 因子 (\>100) 或向下 (\<100)。 计算硬编码值时，您可以使用此号码作为因素。 
  
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
   

