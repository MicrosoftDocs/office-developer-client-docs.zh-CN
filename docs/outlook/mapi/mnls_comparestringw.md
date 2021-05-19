---
title: MNLS_CompareStringW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8d0b7b9-2798-4d29-99e4-17da99039361
description: 上次修改时间：2012 年 2 月 20 日
ms.openlocfilehash: dbb18ce712d7900106f2c8dd18404e47d8bdbdb7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356845"
---
# <a name="mnls_comparestringw"></a>MNLS_CompareStringW

  
  
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
  
> [in]区域设置标识符。 有关详细定义，请参阅 [CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)的 _Locale_ 参数。
    
 _dwFlags_
  
> [in]忽略大小写和音调符号的标志。 有关详细定义，请参阅 [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)的 _dwCmpFlags_ 参数。
    
 _pstr1_
  
> [in]指向要比较的第一个 Unicode 字符串的指针。
    
 _cch1_
  
> [in]第一个 Unicode 字符串的字符长度，不包括终止 null 字符。 如果字符串以 null 结尾，则应用程序可以提供负值。 在这种情况下，MNLS_CompareStringW **自动确定** 长度。 
    
 _pstr2_
  
> [in]指向要比较的第二个 Unicode 字符串的指针。
    
 _cch2_
  
> [in]第二个 Unicode 字符串的字符长度，不包括终止 null 字符。 如果字符串以 null 结尾，则应用程序可以提供负值。 在这种情况下，函数会自动确定长度。
    
## <a name="return-value"></a>返回值

返回为 [CompareStringEx 描述的值](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)。
  
## <a name="remarks"></a>备注

此函数包装 [CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。 **MNLS_CompareStringW** 采用与 [CompareStringW 相同的参数和相同行为](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)
  
[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)

