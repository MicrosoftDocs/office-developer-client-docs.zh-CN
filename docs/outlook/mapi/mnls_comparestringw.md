---
title: MNLS_CompareStringW
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f8d0b7b9-2798-4d29-99e4-17da99039361
description: 上次修改时间： 2012 年 2 月 20 日
ms.openlocfilehash: dbb18ce712d7900106f2c8dd18404e47d8bdbdb7
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396209"
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
  
> [in]区域设置标识符。 有关详细的定义，请参阅_Locale_参数的[CompareString](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。
    
 _dwFlags_
  
> [in]要忽略大小写和音调符号的标志。 有关详细的定义，请参阅[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)的_dwCmpFlags_参数。
    
 _pstr1_
  
> [in]指向要比较的第一个 Unicode 字符串。
    
 _cch1_
  
> [in]以字符数计不包括 null 终止符的第一个 Unicode 字符串的长度。 如果 string 是 null 结尾，应用程序可以提供一个负值。 在这种情况下， **MNLS_CompareStringW**函数将自动确定长度。 
    
 _pstr2_
  
> [in]指向要比较的第二个 Unicode 字符串。
    
 _cch2_
  
> [in]在不包括 null 终止符的第二个 Unicode 字符串的字符的长度。 如果 string 是 null 结尾，应用程序可以提供一个负值。 在这种情况下，该函数将自动确定长度。
    
## <a name="return-value"></a>返回值

返回 for [CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)所述的值。
  
## <a name="remarks"></a>说明

此函数的换行[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)。 **MNLS_CompareStringW**采用相同参数具有[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)相同的行为。
  
## <a name="see-also"></a>另请参阅



[CompareStringW](https://msdn.microsoft.com/library/dd317759%28VS.85%29.aspx)
  
[CompareStringEx](https://msdn.microsoft.com/library/dd317761%28VS.85%29.aspx)

