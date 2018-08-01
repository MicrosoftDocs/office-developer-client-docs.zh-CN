---
title: NOW Function (VisioShapeSheet)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251470
localization_priority: Normal
ms.assetid: 96cac1f6-cc17-466f-23d8-a9006e7de05f
description: 返回当前的日期和时间值。
ms.openlocfilehash: 387425369b1f1d6313502b3679a72cfd23038834
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780823"
---
# <a name="now-function-visioshapesheet"></a>NOW Function (VisioShapeSheet)

返回当前的日期和时间值。
  
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

NOW()+2EW.
  
返回当前的日期和时间加上两周时间后的结果，如 10/11/10 12:03:30 PM。
  

