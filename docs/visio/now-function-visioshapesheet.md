---
title: NOW 函数 (VisioShapeSheet)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251470
localization_priority: Normal
ms.assetid: 96cac1f6-cc17-466f-23d8-a9006e7de05f
description: 返回当前日期和时间值。
ms.openlocfilehash: 9e28f51b0e1d1c09a70e54e432a865968c721940
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340990"
---
# <a name="now-function-visioshapesheet"></a>NOW 函数 (VisioShapeSheet)

返回当前日期和时间值。
  
## <a name="syntax"></a>语法

NOW ( )
  
### <a name="return-value"></a>返回值

Datetime
  
## <a name="remarks"></a>注解

NOW 每分钟自动重新计算。 
  
## <a name="example-1"></a>示例 1

NOW( )
  
返回当前的日期和时间，如 9/27/2010 12:03:30 PM。
  
## <a name="example-2"></a>示例 2

FORMAT(NOW(),"dd MMM., yyyy hh:mm")
  
以“27 Sep., 2010 12:03”格式返回当前的日期和时间。
  
## <a name="example-3"></a>示例 3

NOW () + 2EW。
  
返回当前的日期和时间加上两周时间后的结果，如 10/11/10 12:03:30 PM。
  

