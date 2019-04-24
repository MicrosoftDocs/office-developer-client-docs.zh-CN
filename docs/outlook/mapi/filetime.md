---
title: FILETIME
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FILETIME
api_type:
- COM
ms.assetid: 4af8e79a-697e-44a1-8576-fdc57726e9ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 00355546717ca61492750cb1dd113d20114b0695
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334809"
---
# <a name="filetime"></a><span data-ttu-id="2b07c-103">FILETIME</span><span class="sxs-lookup"><span data-stu-id="2b07c-103">FILETIME</span></span>

  
  
<span data-ttu-id="2b07c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b07c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b07c-105">保留文件的无符号64位日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="2b07c-105">Holds an unsigned 64-bit date and time value for a file.</span></span> <span data-ttu-id="2b07c-106">此值表示自1601年1月1日开始起的100毫微秒单位的数量。</span><span class="sxs-lookup"><span data-stu-id="2b07c-106">This value represents the number of 100-nanosecond units since the start of January 1, 1601.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2b07c-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="2b07c-107">Header file:</span></span>  <br/> |<span data-ttu-id="2b07c-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="2b07c-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a><span data-ttu-id="2b07c-109">Members</span><span class="sxs-lookup"><span data-stu-id="2b07c-109">Members</span></span>

 <span data-ttu-id="2b07c-110">**dwLowDateTime**</span><span class="sxs-lookup"><span data-stu-id="2b07c-110">**dwLowDateTime**</span></span>
  
> <span data-ttu-id="2b07c-111">文件时间值的低序位32位。</span><span class="sxs-lookup"><span data-stu-id="2b07c-111">Low-order 32 bits of the file time value.</span></span> 
    
 <span data-ttu-id="2b07c-112">**dwHighDateTime**</span><span class="sxs-lookup"><span data-stu-id="2b07c-112">**dwHighDateTime**</span></span>
  
> <span data-ttu-id="2b07c-113">文件时间值的高序位32位。</span><span class="sxs-lookup"><span data-stu-id="2b07c-113">High-order 32 bits of the file time value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2b07c-114">注解</span><span class="sxs-lookup"><span data-stu-id="2b07c-114">Remarks</span></span>

<span data-ttu-id="2b07c-115">PT_SYSTIME 类型的属性具有其值的**FILETIME**结构。</span><span class="sxs-lookup"><span data-stu-id="2b07c-115">A property of type PT_SYSTIME has a **FILETIME** structure for its value.</span></span> <span data-ttu-id="2b07c-116">此类属性的**值**成员在[SPropValue](spropvalue.md)结构中的定义中有一个**FILETIME**数据类型。</span><span class="sxs-lookup"><span data-stu-id="2b07c-116">Such a property has a **FILETIME** data type for the **Value** member in its definition in an [SPropValue](spropvalue.md) structure.</span></span> 
  
<span data-ttu-id="2b07c-117">**FILETIME**结构的定义位于_Win32 程序员参考_和 MAPI 头文件 mapidefs.h 中。</span><span class="sxs-lookup"><span data-stu-id="2b07c-117">The definition of the **FILETIME** structure is in the  _Win32 Programmer's Reference_ and in the MAPI header file Mapidefs.h.</span></span> <span data-ttu-id="2b07c-118">MAPI 定义有条件的结构, 以确保在 Win32 定义不可用时定义它。</span><span class="sxs-lookup"><span data-stu-id="2b07c-118">MAPI defines the structure conditionally to make sure that it is defined when the Win32 definition is unavailable.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2b07c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b07c-119">See also</span></span>



[<span data-ttu-id="2b07c-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2b07c-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="2b07c-121">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2b07c-121">MAPI Structures</span></span>](mapi-structures.md)

