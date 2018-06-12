---
title: Frame 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm405
localization_priority: Normal
ms.assetid: f71d8737-92ef-1124-ba4a-b7e17305bd0a
description: 代表当应用程序作为活动文档在某一容器应用程序中打开时的目标框架名。默认值为空字符串。
ms.openlocfilehash: b94e5efd4a3fdf53e01f7518252852214a72c766
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780322"
---
# <a name="frame-cell-hyperlinks-section"></a>Frame 单元格（“Hyperlinks”内容）

代表当应用程序作为活动文档在某一容器应用程序中打开时的目标框架名。默认值为空字符串。
  
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 Frame 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 超链接。  *名称*。框位置的超链接。  *name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Frame 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visHLinkFrame** <br/> |
   

