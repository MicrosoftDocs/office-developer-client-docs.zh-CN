---
title: Comment 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm170
localization_priority: Normal
ms.assetid: 6f52ed60-d58b-86e6-f7e2-2ef19d4afa75
description: 包含形状的字符串格式的注释文本。
ms.openlocfilehash: e6f21875928bce31dc2004d88f2d281e31265d65
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357111"
---
# <a name="comment-cell-miscellaneous-section"></a>Comment 单元格（“Miscellaneous”内容）

包含形状的字符串格式的注释文本。
  
## <a name="remarks"></a>注解

也可以通过单击 **“审阅”** 选项卡上的 **“新建批注”** 插入批注。 
  
若要从另一个公式或使用 **CellsU** 属性从某个程序按名称获取对 Comment 单元格的引用，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Comment  <br/> |
   
要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visComment** <br/> |
   

