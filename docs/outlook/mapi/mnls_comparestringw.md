---
title: MNLS_CompareStringW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8d0b7b9-2798-4d29-99e4-17da99039361
description: '上次修改时间: 2012 年2月20日'
ms.openlocfilehash: dbb18ce712d7900106f2c8dd18404e47d8bdbdb7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356845"
---
# <a name="mnlscomparestringw"></a>MNLS_CompareStringW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
比较两个 Unicode 字符串。
  
```cpp
int MNLS_CompareStringW (
  LCID lcid,
  DWORD dwFlags,
  LPCWSTR pstr1,
  int cch1,
  LPCWSTR pstr2,
  int cch2);
```

## <a name="parameters"></a>参数

 _lcid_
  
> 实时区域设置标识符。 有关详细的定义, 请参阅[CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)的_Locale_参数。
    
 _dwFlags_
  
> 实时用于忽略大小写和音调符号的标志。 有关详细的定义, 请参阅[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)的_dwCmpFlags_参数。
    
 _pstr1_
  
> 实时指向要比较的第一个 Unicode 字符串的指针。
    
 _cch1_
  
> 实时第一个 Unicode 字符串的长度 (以字符为单位), 不包括终止的 null 字符。 如果字符串是以 null 结尾的, 则应用程序可以提供一个负值值。 在这种情况下, **MNLS_CompareStringW**函数将自动确定长度。 
    
 _pstr2_
  
> 实时指向要比较的第二个 Unicode 字符串的指针。
    
 _cch2_
  
> 实时第二个 Unicode 字符串的长度 (以字符为单位), 不包括终止的 null 字符。 如果字符串是以 null 结尾的, 则应用程序可以提供一个负值值。 在这种情况下, 函数将自动确定长度。
    
## <a name="return-value"></a>返回值

返回为[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)描述的值。
  
## <a name="remarks"></a>注解

此函数将包装[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。 **MNLS_CompareStringW**采用相同的参数, 并具有与[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)相同的行为。
  
## <a name="see-also"></a>另请参阅



[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)
  
[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)

