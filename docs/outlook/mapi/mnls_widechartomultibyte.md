---
title: MNLS_WideCharToMultiByte
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f64cde12-7ed1-444f-8ca4-51cb3ea514cf
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: 6957888f6727175d73d277cf4f5b84dc234d22ea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570035"
---
# <a name="mnlswidechartomultibyte"></a>MNLS_WideCharToMultiByte

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
此函数是类似于**WideCharToMultiByte**，映射到新的字符串的 utf-16 （宽字符） 字符串。 新的字符串不一定是从多字节字符设置。
  
```cpp
int MNLS_WideCharToMultiByte(
  UINT uCodePage,
  DWORD dwFlags,
  LPCWSTR lpWideCharStr,
  int cchWideChar,
  LPSTR lpMultiByteStr,
  int cchMultiByte,
  LPCSTR lpDefaultChar,
  BOOL FAR *lpfUsedDefaultChar);
```

## <a name="parameters"></a>参数

 _uCodePage_
  
> [in]用于执行转换的代码页。
    
 _dwFlags_
  
> [in]标志指示的转换类型。
    
 _lpWideCharStr_
  
> [in]指向要转换的 Unicode 字符串。
    
 _cchWideChar_
  
> [in]标志指示的转换类型。
    
 _lpMultiByteStr_
  
> [] out可选。 指向接收转换后的字符串的缓冲区的指针。
    
 _cchMultiByte_
  
> [in]以字节为单位指示_lpMultiByteStr_缓冲区的大小。
    
 _lpDefaultChar_
  
> [中]可选。 指向要使用如果字符不能表示指定的代码页中的字符。
    
 _lpfUsedDefaultChar_
  
> [] out可选。 指向一个标志，指示该函数已转换中使用默认的字符。
    
## <a name="return-value"></a>返回值

返回写入如果成功_lpMultiByteStr_指向缓冲区的字节数。 
  
## <a name="remarks"></a>注解

此函数的换行**WideCharToMultiByte**函数。 有关详细信息，请参阅[WideCharToMultiByte](http://msdn.microsoft.com/en-us/library/dd374130%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[WideCharToMultiByte](http://msdn.microsoft.com/en-us/library/dd374130%28VS.85%29.aspx)

