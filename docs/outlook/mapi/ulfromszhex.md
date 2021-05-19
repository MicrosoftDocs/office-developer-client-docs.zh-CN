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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433050"
---
# <a name="ulfromszhex"></a>UlFromSzHex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将以 null 结尾的十六进制数字字符串转换为无符号长整型。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlFromSzHex(
LPCSTR lpsz
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向要转换的以 null 结尾的字符串的指针。 _lpsz_ 参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **UlFromSzHex** 返回一个无符号长整型。 如果字符串不以至少一个十六进制数字开头，则返回零。 
  
## <a name="remarks"></a>备注

**UlFromSzHex** 函数在到达字符串中不是十六进制数字的第一个字符时停止转换。 例如，在给定字符串"5a"时 **，UlFromSzHex** 将返回整数值 90。 如果给定字符串"5g5h"，函数将返回整数值 5。 在给定字符串"g5h5"后 **，UlFromSzHex** 将返回零。 
  
 **UlFromSzHex** 对音调差异敏感，但允许对十六进制数字使用"a"到"f"和"A"到"F"。 支持 Unicode 和 DBCS 格式的字符串。 _lpsz_ 的长度限制为字符，不一定是字节。 
  

