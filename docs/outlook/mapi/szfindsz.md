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
ms.openlocfilehash: 0075db0a515166c5185657daf3fc6b1e121d6672
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585120"
---
# <a name="szfindsz"></a>SzFindSz

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在以 null 结尾的字符串中查找第一个出现的以 null 结尾的子字符串。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSTR SzFindCh(
  LPCSTR lpsz,
  LPCSTR lpszKey
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向以 null 结尾的字符串，要搜索的指针。 _Lpsz_参数不能超过 65536 个字符。 
    
 _lpszKey_
  
> [in]指向 null 结尾的子字符串搜索的指针。 _LpszKey_参数不能超过 65536 个字符。 
    
## <a name="return-value"></a>返回值

 **SzFindSz**返回字符串中的子字符串的第一个匹配项的第一个字符的指针。 如果子字符串不会发生无处不在字符串中，如果_lpszKey_大于_lpsz_，或者如果任一参数为 NULL，则返回 NULL 值。 
  
## <a name="remarks"></a>注解

**SzFindSz**功能将搜索完全匹配只;它是敏感案例和发音差异。 支持 Unicode 和 DBCS 格式的搜索。 以字符为单位，不必字节有两个参数的长度限制。 
  

