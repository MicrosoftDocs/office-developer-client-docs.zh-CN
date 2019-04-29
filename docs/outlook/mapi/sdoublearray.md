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
ms.openlocfilehash: 91440d619c8ad8a64b2bac7463a26d9c196a3c0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439266"
---
# <a name="sdoublearray"></a><span data-ttu-id="3cbd2-103">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="3cbd2-103">SDoubleArray</span></span>

  
  
<span data-ttu-id="3cbd2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3cbd2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3cbd2-105">包含用于描述类型 PT_MV_DOUBLE 的属性的双精度数组。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-105">Contains an array of doubles used to describe a property of type PT_MV_DOUBLE.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cbd2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3cbd2-106">Header file:</span></span>  <br/> |<span data-ttu-id="3cbd2-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3cbd2-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a><span data-ttu-id="3cbd2-108">Members</span><span class="sxs-lookup"><span data-stu-id="3cbd2-108">Members</span></span>

 <span data-ttu-id="3cbd2-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="3cbd2-109">**cValues**</span></span>
  
> <span data-ttu-id="3cbd2-110">由**lpdbl**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-110">Count of values in the array pointed to by the **lpdbl** member.</span></span> 
    
 <span data-ttu-id="3cbd2-111">**lpdbl**</span><span class="sxs-lookup"><span data-stu-id="3cbd2-111">**lpdbl**</span></span>
  
> <span data-ttu-id="3cbd2-112">指向双精度值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-112">Pointer to an array of double values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3cbd2-113">说明</span><span class="sxs-lookup"><span data-stu-id="3cbd2-113">Remarks</span></span>

<span data-ttu-id="3cbd2-114">有关 PT_MV_DOUBLE 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3cbd2-114">For more information about PT_MV_DOUBLE, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cbd2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cbd2-115">See also</span></span>



[<span data-ttu-id="3cbd2-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="3cbd2-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="3cbd2-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3cbd2-117">MAPI Structures</span></span>](mapi-structures.md)

