---
title: ExtraInfo 单元格（“Hyperlinks”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm360
localization_priority: Normal
ms.assetid: 55834445-8619-f79a-aea0-0f6a1780e016
description: 表示传递解析 URL 所需信息的字符串，如图像映射的坐标。 例如，在 ExtraInfo 单元格中，x=41 &amp; y=7指定图像映射的坐标。
ms.openlocfilehash: df2886ef7911b484cc60e8a476bfa53369fbf646
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409571"
---
# <a name="extrainfo-cell-hyperlinks-section"></a>ExtraInfo 单元格（“Hyperlinks”内容）

表示传递解析 URL 所需信息的字符串，如图像映射的坐标。 例如，在 ExtraInfo 单元格中，"x=41 &amp; y=7"指定图像映射的坐标。
  
## <a name="remarks"></a>备注

只在事件发生后（而非输入公式后）才对事件单元格求值。
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ExtraInfo 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 超链接。  *name*  .ExtraInfo 其中 Hyperlink.  *name*  是行名称  <br/> |
   
要从某个程序按索引获取对 ExtraInfo 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionHyperlink** <br/> |
| 行索引：  <br/> |**visRow1stHyperlink**  +  *i* 其中 *i* = 0、1、2...  <br/> |
| 单元格索引：  <br/> |**visHLinkExtraInfo** <br/> |
   

