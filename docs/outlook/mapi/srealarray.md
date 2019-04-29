---
title: SRealArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRealArray
api_type:
- COM
ms.assetid: 95be07bf-5732-4775-9e0f-fec47e99d9b7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8439d6609ebece75699a1150a9d0c1a41277fd52
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429871"
---
# <a name="srealarray"></a><span data-ttu-id="40940-103">SRealArray</span><span class="sxs-lookup"><span data-stu-id="40940-103">SRealArray</span></span>

  
  
<span data-ttu-id="40940-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="40940-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="40940-105">包含用于描述类型为 PT_MV_R4 的属性的 float 值数组。</span><span class="sxs-lookup"><span data-stu-id="40940-105">Contains an array of float values that are used to describe a property of type PT_MV_R4.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="40940-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="40940-106">Header file:</span></span>  <br/> |<span data-ttu-id="40940-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="40940-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SRealArray
{
  ULONG cValues;
  float FAR *lpflt;
} SRealArray;

```

## <a name="members"></a><span data-ttu-id="40940-108">Members</span><span class="sxs-lookup"><span data-stu-id="40940-108">Members</span></span>

 <span data-ttu-id="40940-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="40940-109">**cValues**</span></span>
  
> <span data-ttu-id="40940-110">由**lpflt**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="40940-110">Count of values in the array pointed to by the **lpflt** member.</span></span> 
    
 <span data-ttu-id="40940-111">**lpflt**</span><span class="sxs-lookup"><span data-stu-id="40940-111">**lpflt**</span></span>
  
> <span data-ttu-id="40940-112">指向 float 值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="40940-112">Pointer to an array of float values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="40940-113">说明</span><span class="sxs-lookup"><span data-stu-id="40940-113">Remarks</span></span>

<span data-ttu-id="40940-114">有关 PT_MV_R4 属性类型的详细信息, 请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="40940-114">For more information about the PT_MV_R4 property type, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="40940-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40940-115">See also</span></span>



[<span data-ttu-id="40940-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="40940-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="40940-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="40940-117">MAPI Structures</span></span>](mapi-structures.md)

