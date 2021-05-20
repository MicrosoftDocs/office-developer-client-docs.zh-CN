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
# <a name="sdoublearray"></a><span data-ttu-id="f8367-103">SDoubleArray</span><span class="sxs-lookup"><span data-stu-id="f8367-103">SDoubleArray</span></span>

  
  
<span data-ttu-id="f8367-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8367-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8367-105">包含一个双精度数组，用于描述类型为 PT_MV_DOUBLE。</span><span class="sxs-lookup"><span data-stu-id="f8367-105">Contains an array of doubles used to describe a property of type PT_MV_DOUBLE.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f8367-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f8367-106">Header file:</span></span>  <br/> |<span data-ttu-id="f8367-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f8367-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a><span data-ttu-id="f8367-108">Members</span><span class="sxs-lookup"><span data-stu-id="f8367-108">Members</span></span>

 <span data-ttu-id="f8367-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="f8367-109">**cValues**</span></span>
  
> <span data-ttu-id="f8367-110">**lpdbl** 成员指向的数组中的值计数。</span><span class="sxs-lookup"><span data-stu-id="f8367-110">Count of values in the array pointed to by the **lpdbl** member.</span></span> 
    
 <span data-ttu-id="f8367-111">**lpdbl**</span><span class="sxs-lookup"><span data-stu-id="f8367-111">**lpdbl**</span></span>
  
> <span data-ttu-id="f8367-112">指向双值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="f8367-112">Pointer to an array of double values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f8367-113">备注</span><span class="sxs-lookup"><span data-stu-id="f8367-113">Remarks</span></span>

<span data-ttu-id="f8367-114">有关属性类型PT_MV_DOUBLE，请参阅 [属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="f8367-114">For more information about PT_MV_DOUBLE, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f8367-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8367-115">See also</span></span>



[<span data-ttu-id="f8367-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="f8367-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="f8367-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f8367-117">MAPI Structures</span></span>](mapi-structures.md)

