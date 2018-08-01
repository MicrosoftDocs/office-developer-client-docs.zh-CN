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
ms.openlocfilehash: 2b9c2c5b03da98b30e338a250b56091479067955
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780083"
---
# <a name="defaulttabstop-cell-text-block-format-section"></a>DefaultTabstop 单元格（“Text Block Format”部分）

确定默认制表位在文本块中的间隔。 
  
## <a name="remarks"></a>注解

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
   

