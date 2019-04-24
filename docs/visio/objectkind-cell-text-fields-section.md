---
title: ObjectKind 单元格（“Text Fields”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60058
localization_priority: Normal
ms.assetid: cc4c373c-f073-e3c9-3aaa-a4abf050cd20
description: 指示文本域的类型。
ms.openlocfilehash: c2f891620f704a3c48861124b886e49d356960ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360989"
---
# <a name="objectkind-cell-text-fields-section"></a>ObjectKind 单元格（“Text Fields”内容）

指示文本域的类型。
  
|**Value**|**说明**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 标准  <br/> |**visTFOKStandard** <br/> |
| 1  <br/> |纵横混排  <br/> |**visTFOKHorizontaInVertical** <br/> |
   
## <a name="remarks"></a>注解

文本域可以是以下类型之一：
  
- 标准，指示按照域类别插入该域。
    
- 纵横混排，指示该域中的文本采用纵横混排的方式。
    
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 ObjectKind 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | ObjectKind [ *i* ] 其中*i* = <1>, 2, 3 .。。  <br/> |
   
要从某个程序按索引获取对 ObjectKind 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTextField** <br/> |
| 行索引：  <br/> |**visRowField** +  *i* = ** 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> |**visFieldObjectKind** <br/> |
   

