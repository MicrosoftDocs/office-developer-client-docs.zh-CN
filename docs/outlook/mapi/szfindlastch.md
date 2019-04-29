---
title: SzFindLastCh
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindLastCh
api_type:
- COM
ms.assetid: 7c3e5a71-7b78-4328-b8ee-265cc4da4be5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f22d30c1bc7c797834f58bcd1306b14ac2542c6d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421254"
---
# <a name="szfindlastch"></a>SzFindLastCh

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在以 null 结尾的字符串中搜索字符的最后一个匹配项。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
LPSTR SzFindLastCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> 实时指向要搜索的以 null 结尾的字符串的指针。 
    
 _章_
  
> 实时要搜索的字符。
    
## <a name="return-value"></a>返回值

 **SzFindLastCh**返回指向字符串中字符的最后一个匹配项的指针。 如果该字符未出现在字符串中的任何位置, 或者如果_lpsz_参数为 null, 则返回值 null。 
  
## <a name="remarks"></a>说明

**SzFindLastCh**函数仅搜索完全匹配项;区分大小写和变音差异。 支持在 Unicode 和 DBCS 格式的搜索中进行搜索。 
  

