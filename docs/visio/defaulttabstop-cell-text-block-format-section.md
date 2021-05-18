---
title: DefaultTabstop 单元格（“Text Block Format”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm220
localization_priority: Normal
ms.assetid: 3b3e458a-206c-8699-8bf7-da80f4350706
description: 确定默认制表位在文本块中的间隔。
ms.openlocfilehash: 1ae923f6373b9cee76238b1fb27ec5eb3acb43ce
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407828"
---
# <a name="defaulttabstop-cell-text-block-format-section"></a>DefaultTabstop 单元格（“Text Block Format”内容）

确定默认制表位在文本块中的间隔。 
  
## <a name="remarks"></a>备注

对于以英制单位创建的文档，默认值是 0.5 英寸；对于以公制单位创建的文档，默认值是 1.5 厘米。
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 DefaultTabstop 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |DefaultTabstop  <br/> |
   
若要从某个程序按索引获取对 DefaultTabstop 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowText** <br/> |
|单元格索引：  <br/> |**visTxtBlkDefaultTabStop** <br/> |
   

