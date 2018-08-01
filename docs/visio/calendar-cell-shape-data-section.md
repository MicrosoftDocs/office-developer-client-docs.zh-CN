---
title: Calendar 单元格（“Shape Data”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60027
localization_priority: Normal
ms.assetid: f5dcc6d9-474a-9ecb-21f5-56415d934890
description: 确定当数据类型为日期时用于形状数据的日历。
ms.openlocfilehash: 502ecd8a028c4c0d9841bbd3e0ed369f73bd6b65
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779814"
---
# <a name="calendar-cell-shape-data-section"></a>Calendar 单元格（“Shape Data”部分）

确定当数据类型为日期时用于形状数据的日历。
  
## <a name="remarks"></a>注释

可能的值为：0（公历）、1（阿拉伯回历）、2（希伯来农历）、3（台历）、4（日本年号）、5（泰国佛历）、6（朝鲜檀纪历）、7（萨卡时代日历）、8（英语转译）和 9（法语转译）。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Calendar 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 属性。 *名称*。日历其中属性。 *name*是行名称  <br/> |
   
要从某个程序按索引获取对 Calendar 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionProp** <br/> |
| 行索引：  <br/> |**visRowProp** +  *i*其中*i* = 0、 1、 2...  <br/> |
| 单元格索引：  <br/> |**visCustPropsCalendar** <br/> |
   

