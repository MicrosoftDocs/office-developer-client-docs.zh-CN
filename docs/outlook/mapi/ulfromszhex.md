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
ms.openlocfilehash: 950f5513696a9dd9d52db7b7ee912d3f7d12cc48
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315363"
---
# <a name="ulfromszhex"></a>UlFromSzHex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将以 null 结尾的十六进制数字字符串转换为无符号长整数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
ULONG UlFromSzHex(
LPCSTR lpsz
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时指向要转换的以 null 结尾的字符串的指针。 _lpsz_参数不能超过65536个字符。 
    
## <a name="return-value"></a>返回值

 **UlFromSzHex**返回一个无符号的长整型值。 如果字符串不以至少一个十六进制数字开头, 则返回零。 
  
## <a name="remarks"></a>注解

**UlFromSzHex**函数在到达不是十六进制数字的字符串中的第一个字符时停止转换。 例如, 给定字符串 "5a", **UlFromSzHex**返回整数值90。 在给定字符串 "5g5h" 的情况下, 函数返回整数值5。 在给定字符串 "g5h5" 的情况下, **UlFromSzHex**返回零。 
  
 **UlFromSzHex**对变音符的区别是敏感的, 但允许十六进制数字的 "a" 到 "f" 和 "a" 到 "f"。 支持 Unicode 和 DBCS 格式的字符串。 _lpsz_的长度限制是字符, 而不一定是字节。 
  

