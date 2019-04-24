---
title: TextPosAfterBullet 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60089
localization_priority: Normal
ms.assetid: 08958abb-9d66-5a83-dac3-4cbfd1f6d85e
description: 表示段落的第一行和项目符号之间的距离。
ms.openlocfilehash: a98967cb5f9541434745c3b3d6afafde0878074a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332283"
---
# <a name="textposafterbullet-cell-paragraph-section"></a>TextPosAfterBullet 单元格（“Paragraph”内容）

表示段落的第一行和项目符号之间的距离。 
  
## <a name="remarks"></a>注解

此距离将与 IndFirst 单元格中包含的距离（默认的左缩近）相加。此值与绘图比例无关。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 TextPosAfterBullet 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | TextPosAfterBullet [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 TextPosAfterBullet 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visTextPosAfterBullet** <br/> |
   

