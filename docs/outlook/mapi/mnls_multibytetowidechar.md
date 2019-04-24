---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: '上次修改时间: 2012 年2月21日'
ms.openlocfilehash: 1f137aba40703fe84e5753ee6e370262f780f0a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338239"
---
# <a name="mnlsmultibytetowidechar"></a>MNLS_MultiByteToWideChar

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
类似于**MultiByteToWideChar**, 它将字符串映射到 utf-16 (宽字符) 字符串。 字符串不一定来自多字节字符集。
  
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
  
> 实时要在执行转换时使用的代码页。
    
 _dwFlags_
  
> 实时指示转换类型的标志。
    
 _lpMultiByteStr_
  
> 实时指向要转换的字符串的指针。
    
 _cchMultiByte_
  
> 实时由_lpMultiByteStr_参数指示的字符串的大小 (以字节为单位)。 
    
 _lpWideCharStr_
  
> [] out可选。 指向接收转换后的字符串的缓冲区的指针。
    
 _cchWideChar_
  
> 实时由_lpWideCharStr_指示的缓冲区的大小 (以字符为单位)。
    
## <a name="return-value"></a>返回值

返回在_lpWideCharStr_成功时写入缓冲区中的字符数。 
  
## <a name="remarks"></a>注解

此函数将包装**MultiByteToWideChar**函数。 有关详细信息, 请参阅[MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx)。
  

