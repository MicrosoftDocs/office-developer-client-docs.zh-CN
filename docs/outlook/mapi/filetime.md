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
ms.openlocfilehash: a5f950907e2b14cb4101a094715c24b25beb2016
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774932"
---
# <a name="filetime"></a><span data-ttu-id="2fd55-103">FILETIME</span><span class="sxs-lookup"><span data-stu-id="2fd55-103">FILETIME</span></span>

  
  
<span data-ttu-id="2fd55-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2fd55-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2fd55-105">包含无符号的 64 位日期和文件的时间值。</span><span class="sxs-lookup"><span data-stu-id="2fd55-105">Holds an unsigned 64-bit date and time value for a file.</span></span> <span data-ttu-id="2fd55-106">此值表示自 1601 年 1 月 1 日启动以来的 100 纳秒的单位数。</span><span class="sxs-lookup"><span data-stu-id="2fd55-106">This value represents the number of 100-nanosecond units since the start of January 1, 1601.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2fd55-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="2fd55-107">Header file:</span></span>  <br/> |<span data-ttu-id="2fd55-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2fd55-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a><span data-ttu-id="2fd55-109">Members</span><span class="sxs-lookup"><span data-stu-id="2fd55-109">Members</span></span>

 <span data-ttu-id="2fd55-110">**dwLowDateTime**</span><span class="sxs-lookup"><span data-stu-id="2fd55-110">**dwLowDateTime**</span></span>
  
> <span data-ttu-id="2fd55-111">低序位 32 位的文件时间值。</span><span class="sxs-lookup"><span data-stu-id="2fd55-111">Low-order 32 bits of the file time value.</span></span> 
    
 <span data-ttu-id="2fd55-112">**dwHighDateTime**</span><span class="sxs-lookup"><span data-stu-id="2fd55-112">**dwHighDateTime**</span></span>
  
> <span data-ttu-id="2fd55-113">高阶 32 位的文件时间值。</span><span class="sxs-lookup"><span data-stu-id="2fd55-113">High-order 32 bits of the file time value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2fd55-114">说明</span><span class="sxs-lookup"><span data-stu-id="2fd55-114">Remarks</span></span>

<span data-ttu-id="2fd55-115">PT_SYSTIME 类型的属性具有其值**FILETIME**结构。</span><span class="sxs-lookup"><span data-stu-id="2fd55-115">A property of type PT_SYSTIME has a **FILETIME** structure for its value.</span></span> <span data-ttu-id="2fd55-116">这种属性**值**在其定义[SPropValue](spropvalue.md)结构中成员的具有**FILETIME**数据类型。</span><span class="sxs-lookup"><span data-stu-id="2fd55-116">Such a property has a **FILETIME** data type for the **Value** member in its definition in an [SPropValue](spropvalue.md) structure.</span></span> 
  
<span data-ttu-id="2fd55-117">在_Win32 程序员参考_和 MAPI 头文件 Mapidefs.h **FILETIME**结构的定义。</span><span class="sxs-lookup"><span data-stu-id="2fd55-117">The definition of the **FILETIME** structure is in the  _Win32 Programmer's Reference_ and in the MAPI header file Mapidefs.h.</span></span> <span data-ttu-id="2fd55-118">MAPI 定义有条件地以确保它被定义 Win32 定义不可用时的结构。</span><span class="sxs-lookup"><span data-stu-id="2fd55-118">MAPI defines the structure conditionally to make sure that it is defined when the Win32 definition is unavailable.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2fd55-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fd55-119">See also</span></span>



[<span data-ttu-id="2fd55-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2fd55-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="2fd55-121">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2fd55-121">MAPI Structures</span></span>](mapi-structures.md)

