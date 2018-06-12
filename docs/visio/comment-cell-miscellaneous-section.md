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
ms.openlocfilehash: f5222836b29a26cc26ca8093576d0962f0592fae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779904"
---
# <a name="comment-cell-miscellaneous-section"></a>Comment 单元格（“Miscellaneous”内容）

包含形状的字符串格式的注释文本。
  
## <a name="remarks"></a>注解

您还可以通过单击**审阅**选项卡上的**新批注**中插入注释。 
  
若要获取对 Comment 单元格的引用按名称从另一个公式或从程序使用**CellsU**属性，请使用： 
  
|||
|:-----|:-----|
|单元格名称：  <br/> |Comment  <br/> |
   
若要从某个程序按索引获取对 Comment 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
|内容索引：  <br/> |**visSectionObject** <br/> |
|行索引：  <br/> |**visRowMisc** <br/> |
|单元格索引：  <br/> |**visComment** <br/> |
   

