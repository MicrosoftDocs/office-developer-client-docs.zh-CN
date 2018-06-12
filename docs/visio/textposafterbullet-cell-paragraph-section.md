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
ms.openlocfilehash: fe22b81113ab6537922ad4627aa53f34f2e62c48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781500"
---
# <a name="textposafterbullet-cell-paragraph-section"></a>TextPosAfterBullet 单元格（“Paragraph”内容）

表示段落的第一行和项目符号之间的距离。 
  
## <a name="remarks"></a>注释

此距离将与 IndFirst 单元格中包含的距离（默认的左缩近）相加。此值与绘图比例无关。 
  
要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 TextPosAfterBullet 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Para.TextPosAfterBullet [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 TextPosAfterBullet 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visTextPosAfterBullet** <br/> |
   

