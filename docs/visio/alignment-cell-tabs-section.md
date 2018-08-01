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
ms.openlocfilehash: a2178c63d0005ee8b2f0c8ebcfbc25854a5b1567
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779631"
---
# <a name="alignment-cell-tabs-section"></a>Alignment 单元格（“Tabs”部分）

指定制表位的对齐方式。
  
|**值**|**Alignment**|**自动常量**|
|:-----|:-----|:-----|
| 0  <br/> | 左对齐  <br/> |**visTabStopLeft** <br/> |
| 1  <br/> | 居中  <br/> |**visTabStopCenter** <br/> |
| 2  <br/> | 右侧  <br/> |**visTabStopRight** <br/> |
| 3  <br/> | 小数点对齐  <br/> |**visTabStopDecimal** <br/> |
| 4  <br/> | 逗号对齐  <br/> |**visTabStopComma** <br/> |
   
## <a name="remarks"></a>说明

要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Alignment 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 选项卡。  *ij*其中*i 和 j =* < 1 >，2，3  <br/> |
   
要从某个程序按索引获取对 Alignment 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionTab** <br/> |
| 行索引：  <br/> |**visRowTab +***i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> | (*j* * 3) **+ visTabAlign** <br/> |
   

