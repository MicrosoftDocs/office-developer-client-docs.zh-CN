---
title: MNLS_WideCharToMultiByte
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f64cde12-7ed1-444f-8ca4-51cb3ea514cf
description: '上次修改时间: 2012 年2月21日'
ms.openlocfilehash: ad41f9b6060e5cfbabecfd9bb29a47815929d6b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338729"
---
# <a name="mnlswidechartomultibyte"></a>MNLS_WideCharToMultiByte

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
此函数类似于**WideCharToMultiByte**, 它将 UTF-16 (宽字符) 字符串映射到新的字符字符串。 新的字符串不一定来自多字节字符集。
  
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
  
> 实时要在执行转换时使用的代码页。
    
 _dwFlags_
  
> 实时指示转换类型的标志。
    
 _lpWideCharStr_
  
> 实时指向要转换的 Unicode 字符串的指针。
    
 _cchWideChar_
  
> 实时指示转换类型的标志。
    
 _lpMultiByteStr_
  
> [] out可选。 指向接收转换后的字符串的缓冲区的指针。
    
 _cchMultiByte_
  
> 实时由_lpMultiByteStr_指示的缓冲区的大小 (以字节为单位)。
    
 _lpDefaultChar_
  
> [中]可选。 一个指针, 指向在指定的代码页中无法表示字符时要使用的字符。
    
 _lpfUsedDefaultChar_
  
> [] out可选。 指向标志的指针, 该标志指示函数是否已在转换中使用默认字符。
    
## <a name="return-value"></a>返回值

如果成功, 则返回写入到_lpMultiByteStr_所指向的缓冲区中的字节数。 
  
## <a name="remarks"></a>注解

此函数将包装**WideCharToMultiByte**函数。 有关详细信息, 请参阅[WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)。
  
## <a name="see-also"></a>另请参阅



[WideCharToMultiByte](https://msdn.microsoft.com/library/dd374130%28VS.85%29.aspx)

