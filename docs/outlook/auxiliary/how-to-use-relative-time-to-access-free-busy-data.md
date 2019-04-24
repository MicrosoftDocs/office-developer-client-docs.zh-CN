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
# <a name="use-relative-time-to-access-freebusy-data"></a><span data-ttu-id="7cc5f-103">使用相对于访问忙/闲数据的时间</span><span class="sxs-lookup"><span data-stu-id="7cc5f-103">Use relative time to access free/busy data</span></span>

<span data-ttu-id="7cc5f-104">忙/闲 API 中的[IFreeBusyData](ifreebusydata.md)接口使用相对时间概念, 即自1601年1月1日起的分钟数 (以通用时间 (UTC) 表示) 以及**LONG**类型的值。</span><span class="sxs-lookup"><span data-stu-id="7cc5f-104">The [IFreeBusyData](ifreebusydata.md) interface in the Free/Busy API uses a concept of relative time, which is the number of minutes since January 1, 1601, expressed in Universal Time (UTC), and is a value of type **LONG**.</span></span> 
  
<span data-ttu-id="7cc5f-105">以下是一些常用的相对时间值:</span><span class="sxs-lookup"><span data-stu-id="7cc5f-105">The following are some commonly used relative time values:</span></span>
  
- `ULONG ulrtmMax = 1525252319L`
    
- `ULONG ulrtmMin = 0L`
    
<span data-ttu-id="7cc5f-106">使用前面的最大和最小相关时间值, 以帮助验证相对时间值是否有效。</span><span class="sxs-lookup"><span data-stu-id="7cc5f-106">Use the preceding maximum and minimum relative time values to help verify that your relative time values are valid.</span></span>
  
<span data-ttu-id="7cc5f-107">由于 NTFS 以[FILETIME](https://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)格式本身记录文件时间, 因此使用下面的代码示例可以将相对于和从**FILETIME**转换到和。</span><span class="sxs-lookup"><span data-stu-id="7cc5f-107">Because NTFS records file times natively in [FILETIME](https://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx) format, it might be handy to use the following code example to convert relative time to and from **FILETIME**.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="7cc5f-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cc5f-108">See also</span></span>

- [<span data-ttu-id="7cc5f-109">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="7cc5f-109">About the Free/Busy API</span></span>](about-the-free-busy-api.md)
- [<span data-ttu-id="7cc5f-110">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="7cc5f-110">IFreeBusyData</span></span>](ifreebusydata.md)

