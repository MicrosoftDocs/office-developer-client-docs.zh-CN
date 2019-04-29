---
title: SzFindSz
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindSz
api_type:
- COM
ms.assetid: f4584569-1246-4ac9-a404-48284e4920d7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9fc21a27cb6c9041bdd8976ce5f030f0ab9eb57f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435220"
---
# <a name="szfindsz"></a>SzFindSz

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在以 null 结尾的字符串中查找以 null 结尾的子字符串的第一个匹配项。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时指向要搜索的以 null 结尾的字符串的指针。 _lpsz_参数不能超过65536个字符。 
    
 _lpszKey_
  
> 实时指向要搜索的以 null 结尾的子字符串的指针。 _lpszKey_参数不能超过65536个字符。 
    
## <a name="return-value"></a>返回值

 **SzFindSz**返回一个指针, 指向字符串中的子字符串的第一个匹配项的第一个字符。 如果子字符串不出现在字符串中的任何位置, 如果_lpszKey_大于_lpsz_, 或者任一参数为 null, 则返回 null 值。 
  
## <a name="remarks"></a>说明

**SzFindSz**函数仅搜索完全匹配项;区分大小写和变音差异。 支持以 Unicode 和 DBCS 格式搜索。 这两个参数的长度限制为字符, 而不一定是字节。 
  

