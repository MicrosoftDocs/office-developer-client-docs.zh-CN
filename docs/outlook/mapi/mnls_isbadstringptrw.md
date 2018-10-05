---
title: MNLS_IsBadStringPtrW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 293a0700-b950-4fc2-a2e5-148d6c846384
description: 上次修改时间： 2012 年 2 月 20 日
ms.openlocfilehash: 0e64df38afdb8ecce35eb0151d36dde3da35f0a4
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25398736"
---
# <a name="mnlsisbadstringptrw"></a>MNLS_IsBadStringPtrW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证为宽字符串的指针有效。
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]一个指向宽字符的字符串。
    
 _ucchMax_
  
> [in]中包括终止符的字符的字符串的最大长度。
    
## <a name="return-value"></a>返回值

返回一个 boolean 类型的值的字符串为错误时为 true。
  
## <a name="remarks"></a>说明

此函数的换行[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。 有关详细信息，请参阅[IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。
  

