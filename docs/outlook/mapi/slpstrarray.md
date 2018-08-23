---
title: SLPSTRArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLPSTRArray
api_type:
- COM
ms.assetid: 5f570d9b-eb3d-4fc7-bcbe-348a0b8fe9e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ccad74a9f2553bf29af124821c6d6a87dcde3303
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572870"
---
# <a name="slpstrarray"></a><span data-ttu-id="86137-103">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="86137-103">SLPSTRArray</span></span>

  
  
<span data-ttu-id="86137-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="86137-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="86137-105">包含用于描述 PT_MV_STRING8 类型的属性的字符串值的数组。</span><span class="sxs-lookup"><span data-stu-id="86137-105">Contains an array of string values that are used to describe a property of type PT_MV_STRING8.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="86137-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="86137-106">Header file:</span></span>  <br/> |<span data-ttu-id="86137-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="86137-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLPSTRArray
{
  ULONG cValues;
  LPSTR FAR *lppszA;
} SLPSTRArray;

```

## <a name="members"></a><span data-ttu-id="86137-108">Members</span><span class="sxs-lookup"><span data-stu-id="86137-108">Members</span></span>

 <span data-ttu-id="86137-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="86137-109">**cValues**</span></span>
  
> <span data-ttu-id="86137-110">由**lppszA**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="86137-110">Count of values in the array pointed to by the **lppszA** member.</span></span> 
    
 <span data-ttu-id="86137-111">**lppszA**</span><span class="sxs-lookup"><span data-stu-id="86137-111">**lppszA**</span></span>
  
> <span data-ttu-id="86137-112">指向一个 null 结束 8 位字符的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="86137-112">Pointer to an array of null-ended 8-bit character strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="86137-113">注解</span><span class="sxs-lookup"><span data-stu-id="86137-113">Remarks</span></span>

<span data-ttu-id="86137-114">有关 PT_MV_STRING8 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="86137-114">For more information about PT_MV_STRING8, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86137-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86137-115">See also</span></span>



[<span data-ttu-id="86137-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="86137-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="86137-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="86137-117">MAPI Structures</span></span>](mapi-structures.md)

