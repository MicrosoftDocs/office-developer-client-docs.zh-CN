---
title: UlFromSzHex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlFromSzHex
api_type:
- COM
ms.assetid: e2d6b6bf-f96d-460c-859a-21961ac9237c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e6de4be29811dafaf5288b2ccb39c0342a314bad
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584623"
---
# <a name="ulfromszhex"></a>UlFromSzHex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
十六进制数字组成的以 null 结尾的字符串转换为无符号的长整数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlFromSzHex(
LPCSTR lpsz
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向以 null 结尾的字符串，要转换的指针。 _Lpsz_参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **UlFromSzHex**返回无符号的长整数。 如果字符串未开始与至少一个十六进制数字，将返回零。 
  
## <a name="remarks"></a>注解

**UlFromSzHex**函数将停止转换时到达不是一个十六进制数字字符串中的第一个字符。 **UlFromSzHex**给定"5a"的字符串，例如，返回 90 的整数值。 给定字符串"5g5h"，则函数返回 5 的整数值。 **UlFromSzHex**给定字符串"g5h5"，将返回零。 
  
 **UlFromSzHex**非常重视发音差异，但允许同时 a 到 f 和 A 到 F 的十六进制数字。 支持 Unicode 和 DBCS 格式的字符串。 以字符为单位，不必字节_lpsz_的长度限制。 
  

