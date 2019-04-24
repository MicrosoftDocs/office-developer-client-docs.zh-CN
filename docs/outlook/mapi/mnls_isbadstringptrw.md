---
title: MNLS_IsBadStringPtrW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 293a0700-b950-4fc2-a2e5-148d6c846384
description: '上次修改时间: 2012 年2月20日'
ms.openlocfilehash: 0e64df38afdb8ecce35eb0151d36dde3da35f0a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356852"
---
# <a name="mnlsisbadstringptrw"></a>MNLS_IsBadStringPtrW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证指向宽字符串的指针是否有效。
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时指向宽字符字符串的指针。
    
 _ucchMax_
  
> 实时包含终止符在内的字符串的最大长度 (以字符数为单位)。
    
## <a name="return-value"></a>返回值

返回一个 Boolean 类型的值, 如果字符串不正确。
  
## <a name="remarks"></a>注解

此函数将包装[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。 有关详细信息, 请参阅[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。
  

