---
title: ViewMarkup 单元格（“Document Properties”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1030802
localization_priority: Normal
ms.assetid: 6c956266-8266-3312-5a68-cc9d8bdb8cd9
description: 确定绘图窗口中是否显示标记。
ms.openlocfilehash: dda908595b243878ec755cf73351ec1fd672dc55
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781649"
---
# <a name="viewmarkup-cell-document-properties-section"></a>ViewMarkup 单元格（“Document Properties”内容）

确定绘图窗口中是否显示标记。 
  
|**值**|**说明**|
|:-----|:-----|
|TRUE  <br/> |在绘图上显示标记。  <br/> |
|FALSE  <br/> |不显示标记（默认值）。  <br/> |
   
## <a name="remarks"></a>注解

 当打开标记跟踪 （AddMarkup 单元格为 TRUE），ViewMarkup 单元格会自动设置为 TRUE，并且保留为 TRUE，即使已禁用跟踪标记 （AddMarkup 单元格为 FALSE）。 AddMarkup 单元格为 TRUE 时，将忽略 ViewMarkup 单元格中的值。 
  
在绘图中插入注释时，ViewMarkup 单元格也将设置为 TRUE（无论是否启用标记跟踪），并且必须设置为 TRUE 才能在绘图中看到注释。
  
此单元格对应于**审阅**选项卡上的**标记**组中的**显示标记**命令。 
  
若要获取对 ViewMarkup 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |ViewMarkup  <br/> |
   
若要从某个程序按索引获取对 ViewMarkup 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowDoc** <br/> |
|单元格索引：  <br/> |**visDocViewMarkup** <br/> |
   

