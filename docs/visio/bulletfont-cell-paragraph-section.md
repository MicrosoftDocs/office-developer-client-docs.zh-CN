---
title: BulletFont 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60023
localization_priority: Normal
ms.assetid: a75ff1f3-2f4d-89e3-108b-e16a34f5184f
description: 表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。
ms.openlocfilehash: 1cf04917bb7dfa68ee9395abb66ffe9e150f0273
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438461"
---
# <a name="bulletfont-cell-paragraph-section"></a>BulletFont 单元格（“Paragraph”内容）

表示当指定了自定义项目符号字符串并且 Bullet 单元格中的值不为零时，用于设置文字格式的字体编号。 
  
## <a name="remarks"></a>说明

根据您的系统上安装的字体，字体编号会有所不同。如果该值是 0 并且有自定义项目符号字符串，则所使用的字体与该段落的第一个字符的字体相同。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BulletFont 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BulletFont [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 BulletFont 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visBulletFont** <br/> |
   

