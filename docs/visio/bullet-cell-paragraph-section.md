---
title: Bullet 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm130
localization_priority: Normal
ms.assetid: 124a5ee1-6dd1-d17d-6f0e-dbaa5d95d9cd
description: 确定项目符号的样式。
ms.openlocfilehash: d3ecdd8e0f3780490f92766351b5ac94e875ae28
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779810"
---
# <a name="bullet-cell-paragraph-section"></a>Bullet 单元格（“Paragraph”内容）

确定项目符号的样式。
  
|**值**|**项目符号样式**|
|:-----|:-----|
|0  <br/> |无  <br/> |
|1  <br/> |![](media/IC_Bullet1_ZA07645847.gif)           <br/> |
|2  <br/> |![](media/IC_Bullet2_ZA07645848.gif)           <br/> |
|3  <br/> |![](media/IC_Bullet3_ZA07645849.gif)           <br/> |
|4  <br/> |![](media/IC_Bullet4_ZA07645851.gif)           <br/> |
|5  <br/> |![](media/IC_Bullet5_ZA07645852.gif)           <br/> |
|6  <br/> |![](media/IC_Bullet6_ZA07645853.gif)           <br/> |
|7  <br/> |![](media/IC_Bullet7_ZA07645854.gif)           <br/> |
   
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionParagraph** <br/> |
|行索引：  <br/> |**visRowParagraph** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visBulletIndex** <br/> |
   
## <a name="remarks"></a>备注

您还可以设置此单元格的值右键单击形状，指向**格式**，单击**文本**，然后单击**项目符号**选项卡。 
  
若要获取对 Bullet 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Para.Bullet [ *i* ] 其中*i* = < 1 >，2，3，...  <br/> |
   
若要从某个程序按索引获取对 Bullet 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  

