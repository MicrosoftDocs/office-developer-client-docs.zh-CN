---
title: Initials 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60045
localization_priority: Normal
ms.assetid: 8f5d34f0-4c4b-5265-83c1-5b86b73d464f
description: 包含文档审阅者的姓名首字母缩写。
ms.openlocfilehash: ddca3697dfcf1f422efacbe395c18f1a6b8ac48c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335292"
---
# <a name="initials-cell-reviewer-section"></a>Initials 单元格（“Reviewer”内容）

包含文档审阅者的姓名首字母缩写。
  
## <a name="remarks"></a>注解

此值默认为 " **Visio 选项**" 对话框 (单击 "**文件**" 选项卡, 单击 "**选项**", 然后单击 "**常规**") 中 "**常规**" 选项卡上 "**缩写**" 框中的缩写。 
  
若要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Initials 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 审阅者. 缩写 [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
若要从某个程序按索引获取对 Initials 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionReviewer** <br/> |
| 行索引：  <br/> |**visRowReviewer** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visReviewerInitials** <br/> |
   

