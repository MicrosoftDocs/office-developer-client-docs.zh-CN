---
title: SDoubleArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SDoubleArray
api_type:
- COM
ms.assetid: b63b26de-faf9-453c-ab8b-fb703ed09ae8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6986ed7c9ab9932c5d95fcfb7f74f80088f21971
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580367"
---
# <a name="sdoublearray"></a><span data-ttu-id="af4ca-103">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="af4ca-103">SDoubleArray</span></span>

  
  
<span data-ttu-id="af4ca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af4ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af4ca-105">包含数组的双精度数用来描述 PT_MV_DOUBLE 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="af4ca-105">Contains an array of doubles used to describe a property of type PT_MV_DOUBLE.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="af4ca-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="af4ca-106">Header file:</span></span>  <br/> |<span data-ttu-id="af4ca-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="af4ca-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a><span data-ttu-id="af4ca-108">Members</span><span class="sxs-lookup"><span data-stu-id="af4ca-108">Members</span></span>

 <span data-ttu-id="af4ca-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="af4ca-109">**cValues**</span></span>
  
> <span data-ttu-id="af4ca-110">由**lpdbl**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="af4ca-110">Count of values in the array pointed to by the **lpdbl** member.</span></span> 
    
 <span data-ttu-id="af4ca-111">**lpdbl**</span><span class="sxs-lookup"><span data-stu-id="af4ca-111">**lpdbl**</span></span>
  
> <span data-ttu-id="af4ca-112">指向双精度值的数组。</span><span class="sxs-lookup"><span data-stu-id="af4ca-112">Pointer to an array of double values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="af4ca-113">注解</span><span class="sxs-lookup"><span data-stu-id="af4ca-113">Remarks</span></span>

<span data-ttu-id="af4ca-114">有关 PT_MV_DOUBLE 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="af4ca-114">For more information about PT_MV_DOUBLE, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af4ca-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af4ca-115">See also</span></span>



[<span data-ttu-id="af4ca-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="af4ca-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="af4ca-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="af4ca-117">MAPI Structures</span></span>](mapi-structures.md)

