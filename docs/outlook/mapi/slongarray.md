---
title: SLongArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLongArray
api_type:
- COM
ms.assetid: 57435634-202d-4998-9931-4562f1a66f5f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a44974accea30b5d1406c9cc74570012f61639e5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580647"
---
# <a name="slongarray"></a><span data-ttu-id="aac42-103">SLongArray</span><span class="sxs-lookup"><span data-stu-id="aac42-103">SLongArray</span></span>

  
  
<span data-ttu-id="aac42-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aac42-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aac42-105">包含用于描述 PT_MV_LONG 类型的属性的 long 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="aac42-105">Contains an array of LONG value types that are used to describe a property of type PT_MV_LONG.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aac42-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="aac42-106">Header file:</span></span>  <br/> |<span data-ttu-id="aac42-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="aac42-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLongArray
{
  ULONG cValues;
  LONG FAR *lpl;
} SLongArray;

```

## <a name="members"></a><span data-ttu-id="aac42-108">Members</span><span class="sxs-lookup"><span data-stu-id="aac42-108">Members</span></span>

 <span data-ttu-id="aac42-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="aac42-109">**cValues**</span></span>
  
> <span data-ttu-id="aac42-110">由**lpl**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="aac42-110">Count of values in the array pointed to by the **lpl** member.</span></span> 
    
 <span data-ttu-id="aac42-111">**lpl**</span><span class="sxs-lookup"><span data-stu-id="aac42-111">**lpl**</span></span>
  
> <span data-ttu-id="aac42-112">指向的 LONG 值的数组。</span><span class="sxs-lookup"><span data-stu-id="aac42-112">Pointer to an array of LONG values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="aac42-113">注解</span><span class="sxs-lookup"><span data-stu-id="aac42-113">Remarks</span></span>

<span data-ttu-id="aac42-114">有关 PT_MV_LONG 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="aac42-114">For more information about PT_MV_LONG, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aac42-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aac42-115">See also</span></span>



[<span data-ttu-id="aac42-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="aac42-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="aac42-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="aac42-117">MAPI Structures</span></span>](mapi-structures.md)

