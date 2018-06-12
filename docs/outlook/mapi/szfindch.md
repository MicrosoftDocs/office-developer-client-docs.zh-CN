---
title: SzFindCh
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SzFindCh
api_type:
- COM
ms.assetid: 3406d060-bfea-4cea-8253-2a9aeb9e8147
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b517eaffa56001d8c414888ee6cbc8ec4f49cf66
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778943"
---
# <a name="szfindch"></a>SzFindCh
 
**适用于**： Outlook 
  
搜索的以 null 结尾的字符串中的字符的第一个匹配项。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
LPSTR SzFindCh(
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

**SzFindCh**返回到字符串中的字符的第一个匹配项的指针。 如果字符，不会发生无处不在字符串中，或者如果_lpsz_参数为 NULL，则返回 NULL 的值。 
  
## <a name="remarks"></a>备注

**SzFindCh**功能将搜索完全匹配只;它是敏感案例和发音差异。 支持 Unicode 和 DBCS 格式的搜索。 
  

