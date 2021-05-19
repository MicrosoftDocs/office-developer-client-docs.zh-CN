---
title: MNLS_MultiByteToWideChar
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 065d78bf-4c9c-48dd-b1f1-b4e59f3f1243
description: 上次修改时间：2012 年 2 月 21 日
ms.openlocfilehash: 1f137aba40703fe84e5753ee6e370262f780f0a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338239"
---
# <a name="mnls_multibytetowidechar"></a>MNLS_MultiByteToWideChar

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
类似于 **MultiByteToWideChar**，它映射一个字符字符串到 UTF-16 (宽字符) 字符串。 该字符串不一定来自多字节字符集。
  
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
  
> [in]执行转换时要使用的代码页。
    
 _dwFlags_
  
> [in]指示转换类型的标志。
    
 _lpMultiByteStr_
  
> [in]指向要转换的字符串的指针。
    
 _cchMultiByte_
  
> [in]  _lpMultiByteStr_ 参数指示的字符串的大小（以字节为单位）。 
    
 _lpWideCharStr_
  
> [] out可选。 指向接收转换后的字符串的缓冲区的指针。
    
 _cchWideChar_
  
> [in]由  _lpWideCharStr_ 指示的缓冲区的大小（以字符表示）。
    
## <a name="return-value"></a>返回值

如果成功，则返回写入  _lpWideCharStr_ 指示的缓冲区的字符数。 
  
## <a name="remarks"></a>备注

此函数包装 **MultiByteToWideChar** 函数。 有关详细信息，请参阅 [MultiByteToWideChar](https://msdn.microsoft.com/library/dd319072%28VS.85%29.aspx)。
  

