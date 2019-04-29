---
title: Flags 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033782
localization_priority: Normal
ms.assetid: 898bf89d-d00f-9769-a89d-787ef708eca5
description: 指示文本方向是从左到右还是从右到左。
ms.openlocfilehash: af1e79b13d3d8bab2e7271eb79e68cf931871806
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413113"
---
# <a name="flags-cell-paragraph-section"></a>Flags 单元格（“Paragraph”内容）

指示文本方向是从左到右还是从右到左。
  
|**值**|**说明**|
|:-----|:-----|
|0  <br/> |文本方向从左到右（默认值）。  <br/> |
|1  <br/> |文本方向从右到左。  <br/> |
   
## <a name="remarks"></a>说明

此单元格中的值对应于 "**文本**" 对话框 (在 "**开始**" 选项卡上, 单击 "**字体**" 箭头) 中 "**段落**" 选项卡上的 "**方向**" 设置, 仅当使用复杂文种文本的语言被在 " **Microsoft Office 语言首选项**" 对话框中添加。 (依次单击 "**开始**"、"**所有程序**"、" **microsoft office**"、" **microsoft office 工具**" 和 " **microsoft office 语言首选项**"。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Flags 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |段落标记 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Flags 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionParagraph** <br/> |
|行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visFlags** <br/> |
   

