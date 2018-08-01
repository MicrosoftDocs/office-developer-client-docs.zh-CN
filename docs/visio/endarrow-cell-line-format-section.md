---
title: EndArrow 单元格（“Line Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm320
localization_priority: Normal
ms.assetid: 2f9c11ba-a316-bc34-60d4-0a41b2af486f
description: 指出线条末端是箭头还是其他线端格式。
ms.openlocfilehash: fa37e4896fdab0f2e8fee6d94aa38c72519a7e6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780176"
---
# <a name="endarrow-cell-line-format-section"></a>EndArrow 单元格（“Line Format”部分）

指出线条末端是箭头还是其他线端格式。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |无箭头。  <br/> |
|1-45  <br/> |各种类型的箭头样式，与 **“线条”** 对话框中的索引项相对应。  <br/> |
   
## <a name="remarks"></a>说明

您还可以在 **“线条”** 对话框中设置此值（在 **“开始”** 选项卡上的 **“形状”** 组中，单击 **“线条”**，指向 **“箭头”**，然后单击 **“其他箭头”**）。 EndArrowSize 单元格中设置箭头的大小。
  
您可以使用 USE 函数在此单元格中指定自定义线端。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 EndArrow 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |EndArrow  <br/> |
   
若要从某个程序按索引获取对 EndArrow 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowLine** <br/> |
|单元格索引：  <br/> |**visLineEndArrow** <br/> |
   

