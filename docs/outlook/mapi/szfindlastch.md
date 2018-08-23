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
ms.openlocfilehash: eeeff110e5de592d491865079adfa187e5dfa194
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570875"
---
# <a name="szfindlastch"></a>SzFindLastCh

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
搜索的以 null 结尾的字符串中的字符的最后一个实例。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSTR SzFindLastCh(
  LPCSTR lpsz,
  USHORT ch
);
```

## <a name="parameters"></a>参数

 _lpsz_
  
> [in]指向以 null 结尾的字符串，要搜索的指针。 
    
 _频道_
  
> [in]要搜索的字符。
    
## <a name="return-value"></a>返回值

 **SzFindLastCh**返回到字符串中的字符的最后一个匹配项的指针。 如果字符，不会发生无处不在字符串中，或者如果_lpsz_参数为 NULL，则返回 NULL 的值。 
  
## <a name="remarks"></a>注解

**SzFindLastCh**功能将搜索完全匹配只;它是敏感案例和发音差异。 支持 Unicode 和 DBCS 格式的搜索。 
  

