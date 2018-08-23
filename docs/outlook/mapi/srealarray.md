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
ms.openlocfilehash: 8c7ce2805248bf91ce7da071c67ece28a5b8ca07
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564281"
---
# <a name="srealarray"></a><span data-ttu-id="a4a72-103">SRealArray</span><span class="sxs-lookup"><span data-stu-id="a4a72-103">SRealArray</span></span>

  
  
<span data-ttu-id="a4a72-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a4a72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a4a72-105">包含用于描述 PT_MV_R4 类型的属性的浮点值的数组。</span><span class="sxs-lookup"><span data-stu-id="a4a72-105">Contains an array of float values that are used to describe a property of type PT_MV_R4.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a4a72-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="a4a72-106">Header file:</span></span>  <br/> |<span data-ttu-id="a4a72-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a4a72-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SRealArray
{
  ULONG cValues;
  float FAR *lpflt;
} SRealArray;

```

## <a name="members"></a><span data-ttu-id="a4a72-108">Members</span><span class="sxs-lookup"><span data-stu-id="a4a72-108">Members</span></span>

 <span data-ttu-id="a4a72-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="a4a72-109">**cValues**</span></span>
  
> <span data-ttu-id="a4a72-110">由**lpflt**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="a4a72-110">Count of values in the array pointed to by the **lpflt** member.</span></span> 
    
 <span data-ttu-id="a4a72-111">**lpflt**</span><span class="sxs-lookup"><span data-stu-id="a4a72-111">**lpflt**</span></span>
  
> <span data-ttu-id="a4a72-112">指向的浮点值的数组。</span><span class="sxs-lookup"><span data-stu-id="a4a72-112">Pointer to an array of float values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a4a72-113">注解</span><span class="sxs-lookup"><span data-stu-id="a4a72-113">Remarks</span></span>

<span data-ttu-id="a4a72-114">有关 PT_MV_R4 属性类型的详细信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a4a72-114">For more information about the PT_MV_R4 property type, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4a72-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4a72-115">See also</span></span>



[<span data-ttu-id="a4a72-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="a4a72-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="a4a72-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="a4a72-117">MAPI Structures</span></span>](mapi-structures.md)

