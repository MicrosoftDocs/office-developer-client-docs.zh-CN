---
title: MNLS_lstrlenW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d342a956-1164-4c9c-b0bb-7a0b72dc97fc
description: '上次修改时间: 2012 年2月21日'
ms.openlocfilehash: 31f699d1193e55a88e57a0f491658e0d537ef75d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338463"
---
# <a name="mnlslstrlenw"></a>MNLS_lstrlenW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定指定的 Unicode 字符串的长度, 不包括终止的 null 字符。
  
> [!TIP]
> 请考虑改用[StringCchLength](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx) 。 
  
```cpp
int MNLS_lstrlen(
  LPCWSTR lpsz);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时要检查的以 null 结尾的 Unicode 字符串。
    
## <a name="return-value"></a>返回值

函数返回一个包含字符串长度的整数。 它是字符串中的字符数, 不包括终止的 null 字符。 如果_lpsz_为 NULL, 则该函数返回零。 
  
## <a name="remarks"></a>注解

此函数将包装**lstrlen**函数。 有关详细信息, 请参阅[lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)
  
[StringCchLength](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx)

