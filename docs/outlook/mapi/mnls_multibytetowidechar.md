---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: 上次修改时间： 2012 年 2 月 21 日
ms.openlocfilehash: ab082c8ac70bf851097080fb41033f76bccc3044
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776522"
---
# <a name="mnlsmultibytetowidechar"></a>MNLS_MultiByteToWideChar

  
  
**适用于**： Outlook 
  
类似于**MultiByteToWideChar**，映射到 utf-16 （宽字符） 字符串的字符串。 字符串不一定是从多字节字符设置。
  
```cpp
int MNLS_MultiByteToWideChar(
  UINT uCodePage,
  DWORD dwFlags,
  LPCSTR lpMultiByteStr,
  int cchMultiByte,
  LPWSTR lpWideCharStr,
  int cchWideChar);
```

## <a name="parameters"></a>参数

 _uCodePage_
  
> [in]用于执行转换的代码页。
    
 _dwFlags_
  
> [in]标志指示的转换类型。
    
 _lpMultiByteStr_
  
> [in]指向要转换的字符串。
    
 _cchMultiByte_
  
> [in]大小，以字节为单位指示_lpMultiByteStr_参数的字符串。 
    
 _lpWideCharStr_
  
> [] out可选。 指向接收转换后的字符串的缓冲区的指针。
    
 _cchWideChar_
  
> [in]以字符为单位，由_lpWideCharStr_缓冲区的大小。
    
## <a name="return-value"></a>返回值

返回写入由_lpWideCharStr_ ，如果成功缓冲区的字符的数。 
  
## <a name="remarks"></a>说明

此函数的换行**MultiByteToWideChar**函数。 有关详细信息，请参阅[MultiByteToWideChar](http://msdn.microsoft.com/en-us/library/dd319072%28VS.85%29.aspx)。
  

