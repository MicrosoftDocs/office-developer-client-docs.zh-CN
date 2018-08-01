---
title: DATE Function (VisioShapeSheet)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251412
localization_priority: Normal
ms.assetid: 2b6c5375-c543-ff2f-f20a-6d92fd65717a
description: 返回表示由年、 月和日的日期根据系统的区域设置中的短日期样式设置格式。 为年、 月和日值反映公历。
ms.openlocfilehash: 7a19d97f70f9314ecdbd2228078e1e18b1ac9146
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780058"
---
# <a name="date-function-visioshapesheet"></a>DATE Function (VisioShapeSheet)

返回表示*年、 月*和*日*的日期根据系统的区域设置中的短日期样式设置格式。 为*年*、*月*和*日*值反映公历。 
  
## <a name="syntax"></a>语法

日期 (* **年** *，* **月** *，* **天** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _year_ <br/> |必需  <br/> |**Integer** <br/> |年份。  <br/> |
| _month_ <br/> |必需  <br/> |**Integer** <br/> |月份。  <br/> |
| _一天_ <br/> |必需  <br/> |**Integer** <br/> |日期。  <br/> |
   
## <a name="example-1"></a>示例 1

DATE(1999,6,7)
  
返回表示 6/7/1999 的值。
  
## <a name="example-2"></a>示例 2

DATE(1999,6,7) + 4 ed.
  
返回表示 6/11/1999 的值。
  
## <a name="example-3"></a>示例 3

FORMAT(DATE(1999,10,14),"C")
  
返回表示 Tuesday, October 14, 1999 的值。
  

