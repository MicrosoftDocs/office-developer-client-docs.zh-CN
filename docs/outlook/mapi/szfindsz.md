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
  
在以 null 结尾的字符串中查找第一次出现以 null 结尾的子字符串。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向要搜索的以 null 结尾的字符串的指针。 _lpsz_ 参数不能超过 65536 个字符。 
    
 _lpszKey_
  
> [in]指向要搜索的以 null 结束的子字符串的指针。 _lpszKey_ 参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **SzFindSz** 返回指向字符串中子字符串第一个出现的第一个字符的指针。 如果子字符串未出现在字符串中的任何位置，如果  _lpszKey_ 大于  _lpsz_，或者如果任一参数为 NULL，则返回 NULL 值。 
  
## <a name="remarks"></a>备注

**SzFindSz** 函数仅搜索完全匹配;区分大小写和音调差异。 支持 Unicode 和 DBCS 格式的搜索。 这两个参数的长度限制为字符，不一定是字节。 
  

