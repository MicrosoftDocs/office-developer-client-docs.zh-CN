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
  
在以 null 结尾的字符串中搜索最后一次出现的字符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSTR SzFindLastCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向要搜索的以 null 结尾的字符串的指针。 
    
 _ch_
  
> [in]要搜索的字符。
    
## <a name="return-value"></a>返回值

 **SzFindLastCh** 返回指向字符串中最后出现的字符的指针。 如果该字符不在字符串中的任何位置出现，或者  _lpsz_ 参数为 NULL，则返回 NULL 值。 
  
## <a name="remarks"></a>备注

**SzFindLastCh** 函数仅搜索完全匹配;区分大小写和音调差异。 支持 Unicode 和 DBCS 格式的搜索。 
  

