---
title: Name 单元格（“Reviewer”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030992
localization_priority: Normal
ms.assetid: be39cd0b-56bf-a070-f5d8-c9a440d81ee2
description: 包含文档审阅者的姓名。
ms.openlocfilehash: 6bc1629c51fc4dcb3fe7e2d6576e8f1f096144ae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780786"
---
# <a name="name-cell-reviewer-section"></a>Name 单元格（“Reviewer”部分）

包含文档审阅者的姓名。
  
## <a name="remarks"></a>注解

 该值默认为**Visio 选项**对话框的**常规**选项卡上的**用户名**框中找到的名称 （单击**文件**选项卡，单击**选项**，然后单击**常规**）。 
  
若要获取对 Name 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | Reviewer.Name [ *i* ] 其中*i* = < 1 >，2，3...  <br/> |
   
若要从某个程序按索引获取对 Name 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionReviewer** <br/> |
| 行索引：  <br/> |**visRowReviewer** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visReviewerName** <br/> |
   

