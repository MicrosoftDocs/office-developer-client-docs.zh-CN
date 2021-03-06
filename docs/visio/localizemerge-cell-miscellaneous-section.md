---
title: LocalizeMerge 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm1033773
localization_priority: Normal
ms.assetid: 734d4415-05dd-4c4d-763e-e035fa56dcec
description: 确定在文档间复制时是否本地化形状。
ms.openlocfilehash: ddd6041ec6531652deb38a0c16be2c741bac91a6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405672"
---
# <a name="localizemerge-cell-miscellaneous-section"></a>LocalizeMerge 单元格（“Miscellaneous”内容）

确定在文档间复制时是否本地化形状。
  
|**值**|**说明**|
|:-----|:-----|
| TRUE  <br/> | 使用目标文档的语言本地化形状。  <br/> |
| FALSE  <br/> | 不要根据目标文档的语言本地化形状， (默认) 。  <br/> |
   
## <a name="remarks"></a>备注

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 LocalizeMerge 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | LocalizeMerge  <br/> |
   
要从某个程序按索引获取对 LocalizeMerge 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visObjLocalizeMerge** <br/> |
   

