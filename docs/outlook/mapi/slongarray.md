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
ms.openlocfilehash: 9b1c5a09a60240efa9d4fa117f0d8fe8113169d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361164"
---
# <a name="slongarray"></a><span data-ttu-id="76c26-103">SLongArray</span><span class="sxs-lookup"><span data-stu-id="76c26-103">SLongArray</span></span>

  
  
<span data-ttu-id="76c26-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="76c26-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="76c26-105">包含用于描述类型为 PT_MV_LONG 的属性的 LONG 值类型的数组。</span><span class="sxs-lookup"><span data-stu-id="76c26-105">Contains an array of LONG value types that are used to describe a property of type PT_MV_LONG.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="76c26-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="76c26-106">Header file:</span></span>  <br/> |<span data-ttu-id="76c26-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="76c26-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLongArray
{
  ULONG cValues;
  LONG FAR *lpl;
} SLongArray;

```

## <a name="members"></a><span data-ttu-id="76c26-108">Members</span><span class="sxs-lookup"><span data-stu-id="76c26-108">Members</span></span>

 <span data-ttu-id="76c26-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="76c26-109">**cValues**</span></span>
  
> <span data-ttu-id="76c26-110">由**lpl**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="76c26-110">Count of values in the array pointed to by the **lpl** member.</span></span> 
    
 <span data-ttu-id="76c26-111">**lpl**</span><span class="sxs-lookup"><span data-stu-id="76c26-111">**lpl**</span></span>
  
> <span data-ttu-id="76c26-112">指向 LONG 值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="76c26-112">Pointer to an array of LONG values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="76c26-113">注解</span><span class="sxs-lookup"><span data-stu-id="76c26-113">Remarks</span></span>

<span data-ttu-id="76c26-114">有关 PT_MV_LONG 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="76c26-114">For more information about PT_MV_LONG, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="76c26-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76c26-115">See also</span></span>



[<span data-ttu-id="76c26-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="76c26-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="76c26-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="76c26-117">MAPI Structures</span></span>](mapi-structures.md)

