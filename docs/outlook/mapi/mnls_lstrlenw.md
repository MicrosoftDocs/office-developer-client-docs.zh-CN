---
title: MNLS_lstrlenW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d342a956-1164-4c9c-b0bb-7a0b72dc97fc
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: 31f699d1193e55a88e57a0f491658e0d537ef75d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392086"
---
# <a name="mnlslstrlenw"></a>MNLS_lstrlenW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定指定的 Unicode 字符串，不包括 null 终止符的长度。
  
> [!TIP]
> 考虑使用[StringCchLength](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx) 。 
  
```cpp
int MNLS_lstrlen(
  LPCWSTR lpsz);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]Null 结尾的 Unicode 字符串要检查。
    
## <a name="return-value"></a>返回值

此函数返回字符串的长度为之间的整数。 它是在字符串中，不包括 null 终止符的字符数。 如果_lpsz_为 NULL，则此函数将返回零。 
  
## <a name="remarks"></a>说明

此函数的换行**lstrlen**函数。 有关详细信息，请参阅[lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[lstrlen](https://msdn.microsoft.com/library/ms647492%28VS.85%29.aspx)
  
[StringCchLength](https://msdn.microsoft.com/library/ms647539%28VS.85%29.aspx)

