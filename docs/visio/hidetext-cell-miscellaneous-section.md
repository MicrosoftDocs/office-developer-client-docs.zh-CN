---
title: HideText 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251323
localization_priority: Normal
ms.assetid: 3d23647a-e567-da71-50df-336a0f2f4071
description: 隐藏形状的文本。您可以查看文本块中的文本、编辑属性并将样式应用到文本，但是所做的更改需要等到您将 HideText 重置为 FALSE (0) 之后才会显现。
ms.openlocfilehash: e2d220e9d7874382f2aaeade5488bd4809f3a9dd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780405"
---
# <a name="hidetext-cell-miscellaneous-section"></a>HideText 单元格（“Miscellaneous”部分）

隐藏形状的文本。您可以查看文本块中的文本、编辑属性并将样式应用到文本，但是所做的更改需要等到您将 HideText 重置为 FALSE (0) 之后才会显现。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 隐藏文本且不能打印。  <br/> |
| FALSE  <br/> | 不隐藏文本。  <br/> |
   
## <a name="remarks"></a>注释

要从另一个公式或使用**CellsU**属性从某个程序按名称获取对 HideText 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | HideText  <br/> |
   
若要从某个程序按索引获取对 HideText 单元格的引用，请使用带下列参数的**CellsSRC**属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visHideText** <br/> |
   

