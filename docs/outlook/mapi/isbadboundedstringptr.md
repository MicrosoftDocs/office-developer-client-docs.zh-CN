---
title: IsBadBoundedStringPtr
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 888c60e3-7376-4d66-8ee2-ce81abafb185
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d5ebb0e16138c3cc65ff6fd7c635e5498c9c1ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278832"
---
# <a name="isbadboundedstringptr"></a>IsBadBoundedStringPtr

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
验证调用进程是否具有对指定范围的内存的读取访问权限。
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapiwin  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序。  <br/> |
   
```cpp
BOOL IsBadBoundedStringPtr(
  const void FAR* lpsz,
  UINT cchMax
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时指向以 null 结尾的 ASCII 字符串的指针。
    
 _cchMax_
  
> 实时字符串的最大大小 (以字符为单位)。 函数在所有字符中检查是否有对字符串的终止 null 字符的读取访问权限, 或最多为此参数指定的字符数 (以较小值为准)。 如果此参数为零, 则返回值为零。
    
## <a name="return-value"></a>返回值

如果调用进程具有对字符串的终止 null 字符的所有字符的读取访问权限, 则返回值为零; 或者读取访问权限由_cchMax_指定的字符数。
  
如果调用进程没有对字符串的终止 null 字符的所有字符的读取访问权限, 则返回值为非零; 或者读取权限的最大值为_cchMax_指定的字符数。
  
## <a name="remarks"></a>注解

**IsBadBoundedStringPtr**函数等效于使用**IsBadStringPtr**。
  
## <a name="see-also"></a>另请参阅



[IsBadStringPtr](https://msdn.microsoft.com/library/windows/desktop/aa366714%28v=vs.85%29.aspx)

