---
title: BulletSize 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033780
localization_priority: Normal
ms.assetid: 6ff5d07b-17e2-f6ca-1860-5d498a9ebf06
description: 指定项目符号的大小。
ms.openlocfilehash: 8671bc6f5ec40814b13727bc458f74eb2893f839
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405420"
---
# <a name="bulletsize-cell-paragraph-section"></a>BulletSize 单元格（“Paragraph”内容）

指定项目符号的大小。 
  
## <a name="remarks"></a>说明

可为预定义项目符号或自定义项目符号指定此值，该值可以是百分比值也可以是具体的值。 
  
如果值为零 (0), 则项目符号与段落中的第一个字符的字号相同。 如果该值是百分比，则项目符号的字体大小是段落中第一个字符大小的相应百分比。 负数将视为百分比。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 BulletSize 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | BulletFontSize [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 BulletSize 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionParagraph** <br/> |
| 行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visBulletFontSize** <br/> |
   

