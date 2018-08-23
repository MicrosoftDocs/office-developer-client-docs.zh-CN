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
ms.openlocfilehash: 39b4474bcc6bd71993fb5dc42bb2bfc1bf9f5f48
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573402"
---
# <a name="isbadboundedstringptr"></a>IsBadBoundedStringPtr

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
验证调用进程具有读取访问权限指定范围的内存。
  
|||
|:-----|:-----|
|头文件：  <br/> |mapiwin.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商。  <br/> |
   
```cpp
BOOL IsBadBoundedStringPtr(
  const void FAR* lpsz,
  UINT cchMax
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]以 null 结尾的 ASCII 字符串的指针。
    
 _cchMax_
  
> [in]字符串，以字符为单位的最大大小。 该函数检查的字符串的 null 终止符之前的所有字符中的读取访问或最多为此参数所指定的字符数，两者中较小。 如果此参数为零，则返回的值为零。
    
## <a name="return-value"></a>返回值

调用进程具有读取访问权限之前字符串的 null 终止符的所有字符或最_cchMax_由指定的字符数多的读取访问权限时，返回值为零。
  
调用进程不具有对所有字符，最多为字符串的 null 终止符的读取权限或最_cchMax_由指定的字符数多的读取访问权限时，返回的值将为非零。
  
## <a name="remarks"></a>注解

**IsBadBoundedStringPtr**函数等效于使用**IsBadStringPtr**。
  
## <a name="see-also"></a>另请参阅



[IsBadStringPtr](http://msdn.microsoft.com/en-us/library/windows/desktop/aa366714%28v=vs.85%29.aspx)

