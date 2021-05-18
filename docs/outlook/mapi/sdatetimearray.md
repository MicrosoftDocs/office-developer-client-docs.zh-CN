---
title: SDateTimeArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SDateTimeArray
api_type:
- COM
ms.assetid: 6a0dff65-1055-487c-9d15-4cfe336f2ad7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9d9fd04776742383f40c6989bcf588b24b33d84b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406778"
---
# <a name="sdatetimearray"></a><span data-ttu-id="9afd3-103">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="9afd3-103">SDateTimeArray</span></span>

  
  
<span data-ttu-id="9afd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9afd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9afd3-105">包含一个时间值数组，用于描述类型为 PT_MV_SYSTIME。</span><span class="sxs-lookup"><span data-stu-id="9afd3-105">Contains an array of time values that are used to describe a property of type PT_MV_SYSTIME.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9afd3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="9afd3-106">Header file:</span></span>  <br/> |<span data-ttu-id="9afd3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9afd3-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SDateTimeArray
{
  ULONG cValues;
  FILETIME FAR *lpft;
} SDateTimeArray;

```

## <a name="members"></a><span data-ttu-id="9afd3-108">Members</span><span class="sxs-lookup"><span data-stu-id="9afd3-108">Members</span></span>

 <span data-ttu-id="9afd3-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="9afd3-109">**cValues**</span></span>
  
> <span data-ttu-id="9afd3-110">**lpft** 成员指向的数组中的值计数。</span><span class="sxs-lookup"><span data-stu-id="9afd3-110">Count of values in the array pointed to by the **lpft** member.</span></span> 
    
 <span data-ttu-id="9afd3-111">**lpft**</span><span class="sxs-lookup"><span data-stu-id="9afd3-111">**lpft**</span></span>
  
> <span data-ttu-id="9afd3-112">指向包含时间值的 [FILETIME](filetime.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="9afd3-112">Pointer to an array of [FILETIME](filetime.md) structures that contain the time values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9afd3-113">备注</span><span class="sxs-lookup"><span data-stu-id="9afd3-113">Remarks</span></span>

<span data-ttu-id="9afd3-114">有关属性类型PT_MV_SYSTIME，请参阅 [属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9afd3-114">For more information about PT_MV_SYSTIME, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9afd3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9afd3-115">See also</span></span>



[<span data-ttu-id="9afd3-116">FILETIME</span><span class="sxs-lookup"><span data-stu-id="9afd3-116">FILETIME</span></span>](filetime.md)
  
[<span data-ttu-id="9afd3-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="9afd3-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="9afd3-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="9afd3-118">MAPI Structures</span></span>](mapi-structures.md)

