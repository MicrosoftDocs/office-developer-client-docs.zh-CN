---
title: DATE 函数 (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251412
localization_priority: Normal
ms.assetid: 2b6c5375-c543-ff2f-f20a-6d92fd65717a
description: 返回以年、月和日表示的日期, 根据系统区域设置中的短日期样式的格式设置。 年、月和日的值反映公历日历。
ms.openlocfilehash: 0175c1f06ec3dbdf89774759546c65994d38105e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360331"
---
# <a name="date-function-visioshapesheet"></a>DATE 函数 (VisioShapeSheet)

返回以*年、月*和*日*表示的日期, 根据系统区域设置中的短日期样式的格式设置。 *年*、*月*和*日*的值反映公历日历。 
  
## <a name="syntax"></a>语法

DATE (* **年** *、* **月** *、* **日** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _year_ <br/> |必需  <br/> |**Integer** <br/> |年份。  <br/> |
| _month_ <br/> |必需  <br/> |**Integer** <br/> |月份。  <br/> |
| _为期_ <br/> |必需  <br/> |**Integer** <br/> |日期。  <br/> |
   
## <a name="example-1"></a>示例 1

日期 (1999、6、7)
  
返回表示 6/7/1999 的值。
  
## <a name="example-2"></a>示例 2

DATE(1999,6,7) + 4 ed.
  
返回表示 6/11/1999 的值。
  
## <a name="example-3"></a>示例 3

FORMAT (DATE (1999、10、14)、"C")
  
返回表示 Tuesday, October 14, 1999 的值。
  

