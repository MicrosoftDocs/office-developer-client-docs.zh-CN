---
title: Invisible 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033755
localization_priority: Normal
ms.assetid: e67dcd83-4a88-a0f8-5c6a-dae51424edbd
description: 指示超链接是否出现在形状或页面的快捷菜单上。
ms.openlocfilehash: e269c5e907afa0d49f1fc6115b7a031835467c2e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780471"
---
# <a name="invisible-cell-hyperlinks-section"></a>Invisible 单元格（“Hyperlinks”部分）

指示超链接是否出现在形状或页面的快捷菜单上。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |超链接不显示为快捷菜单上的菜单项。  <br/> |
|FALSE  <br/> |超链接显示为快捷菜单上的菜单项（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Invisible 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |超链接。 *名称*。不可见，其中超链接 *.name*是行名称  <br/> |
   
若要从某个程序按索引获取对 Invisible 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionHyperlink** <br/> |
|行索引：  <br/> |**visRow1stHyperlink** +  *i*其中*i* = 0、 1、 2...  <br/> |
|单元格索引：  <br/> |**visHLinkInvisible** <br/> |
   

