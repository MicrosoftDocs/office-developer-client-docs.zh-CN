---
title: Alignment 单元格（“Tabs”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm35
localization_priority: Normal
ms.assetid: 84234177-a2df-6acc-2761-230bc5d12627
description: 指定制表位的对齐方式。
ms.openlocfilehash: 461357c9c838fb4c0e5b0159bf027dd6adce26f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341536"
---
# <a name="alignment-cell-tabs-section"></a>Alignment 单元格（“Tabs”内容）

指定制表位的对齐方式。
  
|**值**|**Alignment**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | Left  <br/> |**visTabStopLeft** <br/> |
| 1  <br/> | 居中  <br/> |**visTabStopCenter** <br/> |
| 双面  <br/> | 右侧  <br/> |**visTabStopRight** <br/> |
| 第三章  <br/> | 小数  <br/> |**visTabStopDecimal** <br/> |
| 4  <br/> | 逗号  <br/> |**visTabStopComma** <br/> |
   
## <a name="remarks"></a>注解

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Alignment 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 张.  *ij*其中*i 和 j =* <1>, 2, 3  <br/> |
   
要从某个程序按索引获取对 Alignment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTab** <br/> |
| 行索引：  <br/> |**visRowTab +***i*其中*i* = 0、1、2 .。。  <br/> |
| 单元格索引：  <br/> | (*j* * 3) **+ visTabAlign** <br/> |
   

