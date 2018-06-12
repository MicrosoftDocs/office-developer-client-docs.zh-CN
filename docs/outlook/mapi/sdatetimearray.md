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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9734adff9c9c7526fc8ff46d17ca913752e104b3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778710"
---
# <a name="sdatetimearray"></a><span data-ttu-id="94d49-103">SDateTimeArray</span><span class="sxs-lookup"><span data-stu-id="94d49-103">SDateTimeArray</span></span>

  
  
<span data-ttu-id="94d49-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="94d49-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="94d49-105">包含用于描述 PT_MV_SYSTIME 类型的属性的时间值的数组。</span><span class="sxs-lookup"><span data-stu-id="94d49-105">Contains an array of time values that are used to describe a property of type PT_MV_SYSTIME.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="94d49-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="94d49-106">Header file:</span></span>  <br/> |<span data-ttu-id="94d49-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="94d49-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SDateTimeArray
{
  ULONG cValues;
  FILETIME FAR *lpft;
} SDateTimeArray;

```

## <a name="members"></a><span data-ttu-id="94d49-108">成员</span><span class="sxs-lookup"><span data-stu-id="94d49-108">Members</span></span>

 <span data-ttu-id="94d49-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="94d49-109">**cValues**</span></span>
  
> <span data-ttu-id="94d49-110">由**lpft**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="94d49-110">Count of values in the array pointed to by the **lpft** member.</span></span> 
    
 <span data-ttu-id="94d49-111">**lpft**</span><span class="sxs-lookup"><span data-stu-id="94d49-111">**lpft**</span></span>
  
> <span data-ttu-id="94d49-112">指向一个[FILETIME](filetime.md)结构包含时间值的数组。</span><span class="sxs-lookup"><span data-stu-id="94d49-112">Pointer to an array of [FILETIME](filetime.md) structures that contain the time values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="94d49-113">备注</span><span class="sxs-lookup"><span data-stu-id="94d49-113">Remarks</span></span>

<span data-ttu-id="94d49-114">有关 PT_MV_SYSTIME 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="94d49-114">For more information about PT_MV_SYSTIME, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94d49-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94d49-115">See also</span></span>



[<span data-ttu-id="94d49-116">FILETIME</span><span class="sxs-lookup"><span data-stu-id="94d49-116">FILETIME</span></span>](filetime.md)
  
[<span data-ttu-id="94d49-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="94d49-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="94d49-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="94d49-118">MAPI Structures</span></span>](mapi-structures.md)

