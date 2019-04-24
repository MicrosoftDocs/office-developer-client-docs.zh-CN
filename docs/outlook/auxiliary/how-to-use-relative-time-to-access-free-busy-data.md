---
title: 使用相对于访问忙/闲数据的时间
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 13aa6ae2-47b9-2cf4-a6ef-651f1338dd49
description: 忙/闲 API 中的 IFreeBusyData 接口使用相对时间概念, 即自1601年1月1日起的分钟数 (以通用时间 (UTC) 表示) 以及 LONG 类型的值。
ms.openlocfilehash: 1b977fc3aebd1f2b20e51f24caa36d6bbf2862ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317631"
---
# <a name="use-relative-time-to-access-freebusy-data"></a>使用相对于访问忙/闲数据的时间

忙/闲 API 中的[IFreeBusyData](ifreebusydata.md)接口使用相对时间概念, 即自1601年1月1日起的分钟数 (以通用时间 (UTC) 表示) 以及**LONG**类型的值。 
  
以下是一些常用的相对时间值:
  
- `ULONG ulrtmMax = 1525252319L`
    
- `ULONG ulrtmMin = 0L`
    
使用前面的最大和最小相关时间值, 以帮助验证相对时间值是否有效。
  
由于 NTFS 以[FILETIME](https://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)格式本身记录文件时间, 因此使用下面的代码示例可以将相对于和从**FILETIME**转换到和。 
  
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

