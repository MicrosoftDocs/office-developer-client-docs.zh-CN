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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c207b1db6a24cc60967735e2f4b1a4aa97007750
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778812"
---
# <a name="slongarray"></a><span data-ttu-id="c74e9-103">SLongArray</span><span class="sxs-lookup"><span data-stu-id="c74e9-103">SLongArray</span></span>

  
  
<span data-ttu-id="c74e9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c74e9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c74e9-105">包含用于描述 PT_MV_LONG 类型的属性的 long 类型的数组。</span><span class="sxs-lookup"><span data-stu-id="c74e9-105">Contains an array of LONG value types that are used to describe a property of type PT_MV_LONG.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c74e9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c74e9-106">Header file:</span></span>  <br/> |<span data-ttu-id="c74e9-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c74e9-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLongArray
{
  ULONG cValues;
  LONG FAR *lpl;
} SLongArray;

```

## <a name="members"></a><span data-ttu-id="c74e9-108">成员</span><span class="sxs-lookup"><span data-stu-id="c74e9-108">Members</span></span>

 <span data-ttu-id="c74e9-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="c74e9-109">**cValues**</span></span>
  
> <span data-ttu-id="c74e9-110">由**lpl**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="c74e9-110">Count of values in the array pointed to by the **lpl** member.</span></span> 
    
 <span data-ttu-id="c74e9-111">**lpl**</span><span class="sxs-lookup"><span data-stu-id="c74e9-111">**lpl**</span></span>
  
> <span data-ttu-id="c74e9-112">指向的 LONG 值的数组。</span><span class="sxs-lookup"><span data-stu-id="c74e9-112">Pointer to an array of LONG values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c74e9-113">备注</span><span class="sxs-lookup"><span data-stu-id="c74e9-113">Remarks</span></span>

<span data-ttu-id="c74e9-114">有关 PT_MV_LONG 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c74e9-114">For more information about PT_MV_LONG, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c74e9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c74e9-115">See also</span></span>



[<span data-ttu-id="c74e9-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c74e9-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="c74e9-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c74e9-117">MAPI Structures</span></span>](mapi-structures.md)

