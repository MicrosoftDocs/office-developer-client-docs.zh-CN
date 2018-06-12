---
title: BulletString 单元格（“Paragraph”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm135
localization_priority: Normal
ms.assetid: 38285824-30ad-0cf2-07cb-0103ab3a415a
description: 允许您创建自定义的项目符号样式。
ms.openlocfilehash: bd55e2c061d8e99e0d9e9fd5d9be459b3daae524
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779817"
---
# <a name="bulletstring-cell-paragraph-section"></a>BulletString 单元格（“Paragraph”内容）

允许您创建自定义的项目符号样式。 
  
## <a name="remarks"></a>注解

将样式作为字符串输入（加上引号）。例如，可输入下面的字符串：“ooo”。
  
您还可以设置此单元格的值右键单击形状，指向**格式**，单击**文本**，然后单击**项目符号**选项卡。 
  
若要获取对 BulletString 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Para.BulletStr [ *i* ] 其中*i* = < 1 >，2，3，...  <br/> |
   
若要从某个程序按索引获取对 BulletString 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionParagraph** <br/> |
|行索引：  <br/> |**visRowParagraph** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visBulletString** <br/> |
   

