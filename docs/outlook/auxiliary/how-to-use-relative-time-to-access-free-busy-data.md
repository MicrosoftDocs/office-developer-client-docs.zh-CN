---
title: 使用访问忙/闲数据的相对时间
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 13aa6ae2-47b9-2cf4-a6ef-651f1338dd49
description: 忙/闲 API 中的 IFreeBusyData 接口使用相对时间，即在世界时 (UTC)，表示自 1601，年 1 月 1 日以来的分钟数的概念，并且长是类型的值。
ms.openlocfilehash: b83cd46cfcc4d84d4fc3bf000dd8b0acdda545dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774192"
---
# <a name="use-relative-time-to-access-freebusy-data"></a>使用访问忙/闲数据的相对时间

忙/闲 API 中的[IFreeBusyData](ifreebusydata.md)接口使用相对时间，即在世界时 (UTC)，表示自 1601，年 1 月 1 日以来的分钟数的概念，并为**LONG**类型的值。 
  
以下是一些常用相对时间值：
  
- `ULONG ulrtmMax = 1525252319L`
    
- `ULONG ulrtmMin = 0L`
    
使用前面的最大和最小相对时间值有助于验证您相对时间的值有效。
  
NTFS 格式[FILETIME](http://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)本机记录文件的时间，因为它可能可以方便地使用下面的代码示例将与**FILETIME**转换相对时间。 
  
```cpp
static const LONGLONG UnitsPerMinute = 600000000; 
static const LONGLONG UnitsPerHalfMinute = 300000000; 
void RTimeToFileTime(LONG rtime, FILETIME *pft) 
{ 
    Assert(pft != NULL); 
    ULARGE_INTEGER *puli = (ULARGE_INTEGER *)pft; 
    puli->QuadPart = rtime * UnitsPerMinute; 
} 
  
void FileTimeToRTime(FILETIME *pft, LONG* prtime) 
{ 
    Assert(pft != NULL); 
    Assert(prtime != NULL); 
 
    ULARGE_INTEGER uli = *(ULARGE_INTEGER *)pft; 
  
    uli.QuadPart += UnitsPerHalfMinute; 
    uli.QuadPart /= UnitsPerMinute; 
    *prtime = uli.LowPart; 
} 

```

## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)
- [IFreeBusyData](ifreebusydata.md)

