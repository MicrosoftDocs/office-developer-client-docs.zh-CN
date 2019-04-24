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
ms.openlocfilehash: b7a1d7f845c7b9945670240361a4ac66efa80786
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337560"
---
# <a name="bulletstring-cell-paragraph-section"></a>BulletString 单元格（“Paragraph”内容）

允许您创建自定义的项目符号样式。 
  
## <a name="remarks"></a>注解

将样式作为字符串输入（加上引号）。例如，可输入下面的字符串：“ooo”。
  
您还可以通过以下方法设置此单元格的值：右键单击形状，指向 **“格式”**，单击 **“文本”**，然后单击 **“项目符号”** 选项卡。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 BulletString 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |BulletStr [ *i* ] 其中*i* = <1>, 2, 3, .。。  <br/> |
   
若要从某个程序按索引获取对 BulletString 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionParagraph** <br/> |
|行索引：  <br/> |**visRowParagraph** +  *i* = ** 0、1、2 .。。  <br/> |
|单元格索引：  <br/> |**visBulletString** <br/> |
   

