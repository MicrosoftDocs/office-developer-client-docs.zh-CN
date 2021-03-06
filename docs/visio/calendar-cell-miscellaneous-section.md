---
title: Calendar 单元格（“Miscellaneous”内容）
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm60028
localization_priority: Normal
ms.assetid: 7406b46d-b42d-187c-70e8-123c4da7e781
description: 确定当单元格公式包含日期信息时所使用的日历。
ms.openlocfilehash: f756b0d445bd3f90b67e0b1412bd7ac51a8cdb7e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421814"
---
# <a name="calendar-cell-miscellaneous-section"></a>Calendar 单元格（“Miscellaneous”内容）

确定当单元格公式包含日期信息时所使用的日历。
  
## <a name="remarks"></a>备注

可能的值为：0（公历）、1（阿拉伯回历）、2（希伯来农历）、3（台历）、4（日本年号）、5（泰国佛历）、6（朝鲜檀纪历）、7（萨卡时代日历）、8（英语转译）和 9（法语转译）。 
  
要从另一个公式或从使用 **CellsU** 属性的某个程序按名称获取对 Calendar 单元格的引用，请使用： 
  
|||
|:-----|:-----|
| 单元格名称：  <br/> | 日历  <br/> |
   
若要从某个程序按索引获取对 Calendar 单元格的引用，请使用带下列参数的 **CellsSRC** 属性： 
  
|||
|:-----|:-----|
| 内容索引：  <br/> |**visSectionObject** <br/> |
| 行索引：  <br/> |**visRowMisc** <br/> |
| 单元格索引：  <br/> |**visObjCalendar** <br/> |
   

