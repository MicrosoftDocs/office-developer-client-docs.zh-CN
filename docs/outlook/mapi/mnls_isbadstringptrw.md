---
title: MNLS_IsBadStringPtrW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 293a0700-b950-4fc2-a2e5-148d6c846384
description: 上次修改时间：2012 年 2 月 20 日
ms.openlocfilehash: 0e64df38afdb8ecce35eb0151d36dde3da35f0a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356852"
---
# <a name="mnls_isbadstringptrw"></a>MNLS_IsBadStringPtrW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证指向宽字符串的指针是否有效。
  
```cpp
BOOL MNLS_IsBadStringPtrW(
  LPCWSTR lpsz,
  UINT ucchMax);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向宽字符字符串的指针。
    
 _ucchMax_
  
> [in]字符串的最大长度，以字符（包括终止符）表示。
    
## <a name="return-value"></a>返回值

返回一个 Boolean 值，如果字符串错误，则返回 true。
  
## <a name="remarks"></a>备注

此函数包装 [IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。 有关详细信息，请参阅 [IsBadStringPtr](https://msdn.microsoft.com/library/aa366714%28VS.85%29.aspx)。
  

