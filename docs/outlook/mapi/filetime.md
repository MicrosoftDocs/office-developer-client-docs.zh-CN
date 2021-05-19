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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409501"
---
# <a name="filetime"></a><span data-ttu-id="472f1-103">FILETIME</span><span class="sxs-lookup"><span data-stu-id="472f1-103">FILETIME</span></span>

  
  
<span data-ttu-id="472f1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="472f1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="472f1-105">保留文件的未签名 64 位日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="472f1-105">Holds an unsigned 64-bit date and time value for a file.</span></span> <span data-ttu-id="472f1-106">此值表示自 1601 年 1 月 1 日开始以来 100 纳秒单位的数量。</span><span class="sxs-lookup"><span data-stu-id="472f1-106">This value represents the number of 100-nanosecond units since the start of January 1, 1601.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="472f1-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="472f1-107">Header file:</span></span>  <br/> |<span data-ttu-id="472f1-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="472f1-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a><span data-ttu-id="472f1-109">Members</span><span class="sxs-lookup"><span data-stu-id="472f1-109">Members</span></span>

 <span data-ttu-id="472f1-110">**dwLowDateTime**</span><span class="sxs-lookup"><span data-stu-id="472f1-110">**dwLowDateTime**</span></span>
  
> <span data-ttu-id="472f1-111">文件时间值的低顺序 32 位。</span><span class="sxs-lookup"><span data-stu-id="472f1-111">Low-order 32 bits of the file time value.</span></span> 
    
 <span data-ttu-id="472f1-112">**dwHighDateTime**</span><span class="sxs-lookup"><span data-stu-id="472f1-112">**dwHighDateTime**</span></span>
  
> <span data-ttu-id="472f1-113">文件时间值的 32 位高顺序值。</span><span class="sxs-lookup"><span data-stu-id="472f1-113">High-order 32 bits of the file time value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="472f1-114">备注</span><span class="sxs-lookup"><span data-stu-id="472f1-114">Remarks</span></span>

<span data-ttu-id="472f1-115">类型为 PT_SYSTIME其值具有 **FILETIME** 结构。</span><span class="sxs-lookup"><span data-stu-id="472f1-115">A property of type PT_SYSTIME has a **FILETIME** structure for its value.</span></span> <span data-ttu-id="472f1-116">此类属性具有 **FILETIME** 数据类型在 [SPropValue](spropvalue.md)结构中的定义中为 **Value** 成员定义。</span><span class="sxs-lookup"><span data-stu-id="472f1-116">Such a property has a **FILETIME** data type for the **Value** member in its definition in an [SPropValue](spropvalue.md) structure.</span></span> 
  
<span data-ttu-id="472f1-117">**FILETIME** 结构的定义位于 _Win32 程序员_ 参考和 MAPI 头文件 Mapidefs.h 中。</span><span class="sxs-lookup"><span data-stu-id="472f1-117">The definition of the **FILETIME** structure is in the  _Win32 Programmer's Reference_ and in the MAPI header file Mapidefs.h.</span></span> <span data-ttu-id="472f1-118">MAPI 有条件地定义结构，以确保它在 Win32 定义不可用时定义。</span><span class="sxs-lookup"><span data-stu-id="472f1-118">MAPI defines the structure conditionally to make sure that it is defined when the Win32 definition is unavailable.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="472f1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="472f1-119">See also</span></span>



[<span data-ttu-id="472f1-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="472f1-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="472f1-121">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="472f1-121">MAPI Structures</span></span>](mapi-structures.md)

