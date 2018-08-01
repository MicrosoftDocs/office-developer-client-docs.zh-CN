---
title: AvoidPageBreaks 单元格（“Page Layout”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm80000
localization_priority: Normal
ms.assetid: 7d2ec869-7ffa-3b41-8126-3f4889501e0c
description: 确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。
ms.openlocfilehash: 045ceca430c6c285ad4e454b9d17f9dbd7492a4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779659"
---
# <a name="avoidpagebreaks-cell-page-layout-section"></a>AvoidPageBreaks 单元格（“Page Layout”部分）

确定当形状是增量对齐和/或增量间距时是否可以将其放在分页符上。
  
## <a name="remarks"></a>说明

若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 AvoidPageBreaks 单元格的引用，请使用以下内容。 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |AvoidPageBreaks  <br/> |
   
若要从某个程序按索引获取对 AvoidPageBreaks 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowPageLayout** <br/> |
|单元格索引：  <br/> |**visPLOAvoidPageBreaks** <br/> |
   

