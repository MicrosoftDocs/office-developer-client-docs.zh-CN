---
title: FtSubFt
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FtSubFt
api_type:
- COM
ms.assetid: 6619fc41-5518-44ce-85c1-6b0077ed5cb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: edd789a586adc71289ff821aa7cf7a33f79fb738
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300390"
---
# <a name="ftsubft"></a>FtSubFt

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
从一个不带符号的64位整数中减去另一个。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
FILETIME FtSubFt(
  FILETIME Minuend,
  FILETIME Subtrahend
);
```

## <a name="parameters"></a>参数

 _Minuend_
  
> 实时一个[FILETIME](filetime.md)结构, 其中包含要从中减去_Subtrahend_参数中的值的无符号64位整数。 
    
 _Subtrahend_
  
> 实时一个**FILETIME**结构, 其中包含从_Minuend_参数指示的值中减去的无符号64位整数。 
    
## <a name="return-value"></a>返回值

**FtSubFt**函数返回一个**FILETIME**结构, 其中包含减法的结果。 这两个输入参数保持不变。 
  

