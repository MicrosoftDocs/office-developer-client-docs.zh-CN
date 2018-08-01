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
# <a name="use-relative-time-to-access-freebusy-data"></a><span data-ttu-id="f666c-103">使用访问忙/闲数据的相对时间</span><span class="sxs-lookup"><span data-stu-id="f666c-103">Use relative time to access free/busy data</span></span>

<span data-ttu-id="f666c-104">忙/闲 API 中的[IFreeBusyData](ifreebusydata.md)接口使用相对时间，即在世界时 (UTC)，表示自 1601，年 1 月 1 日以来的分钟数的概念，并为**LONG**类型的值。</span><span class="sxs-lookup"><span data-stu-id="f666c-104">The [IFreeBusyData](ifreebusydata.md) interface in the Free/Busy API uses a concept of relative time, which is the number of minutes since January 1, 1601, expressed in Universal Time (UTC), and is a value of type **LONG**.</span></span> 
  
<span data-ttu-id="f666c-105">以下是一些常用相对时间值：</span><span class="sxs-lookup"><span data-stu-id="f666c-105">The following are some commonly used relative time values:</span></span>
  
- `ULONG ulrtmMax = 1525252319L`
    
- `ULONG ulrtmMin = 0L`
    
<span data-ttu-id="f666c-106">使用前面的最大和最小相对时间值有助于验证您相对时间的值有效。</span><span class="sxs-lookup"><span data-stu-id="f666c-106">Use the preceding maximum and minimum relative time values to help verify that your relative time values are valid.</span></span>
  
<span data-ttu-id="f666c-107">NTFS 格式[FILETIME](http://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx)本机记录文件的时间，因为它可能可以方便地使用下面的代码示例将与**FILETIME**转换相对时间。</span><span class="sxs-lookup"><span data-stu-id="f666c-107">Because NTFS records file times natively in [FILETIME](http://msdn.microsoft.com/library/9baf8a0e-59e3-4fbd-9616-2ec9161520d1%28Office.15%29.aspx) format, it might be handy to use the following code example to convert relative time to and from **FILETIME**.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="f666c-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f666c-108">See also</span></span>

- [<span data-ttu-id="f666c-109">关于忙/闲 API</span><span class="sxs-lookup"><span data-stu-id="f666c-109">About the Free/Busy API</span></span>](about-the-free-busy-api.md)
- [<span data-ttu-id="f666c-110">IFreeBusyData</span><span class="sxs-lookup"><span data-stu-id="f666c-110">IFreeBusyData</span></span>](ifreebusydata.md)

