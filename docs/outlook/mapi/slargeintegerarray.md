---
title: SLargeIntegerArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLargeIntegerArray
api_type:
- COM
ms.assetid: 9ec9a674-c1a2-4137-856f-6cabe6f0eb9f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4d6785783f69857bd93f3c5818983e832e16af05
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778820"
---
# <a name="slargeintegerarray"></a><span data-ttu-id="c4d83-103">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="c4d83-103">SLargeIntegerArray</span></span>

  
  
<span data-ttu-id="c4d83-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c4d83-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c4d83-105">包含用于描述 PT_MV_I8 类型的属性的[LARGE_INTEGER](http://go.microsoft.com/fwlink/?LinkId=132130)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="c4d83-105">Contains an array of [LARGE_INTEGER](http://go.microsoft.com/fwlink/?LinkId=132130) structures that are used to describe a property of type PT_MV_I8.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c4d83-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c4d83-106">Header file:</span></span>  <br/> |<span data-ttu-id="c4d83-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c4d83-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLargeIntegerArray
{
  ULONG cValues;
  LARGE_INTEGER FAR *lpli;
} SLargeIntegerArray;

```

## <a name="members"></a><span data-ttu-id="c4d83-108">Members</span><span class="sxs-lookup"><span data-stu-id="c4d83-108">Members</span></span>

 <span data-ttu-id="c4d83-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="c4d83-109">**cValues**</span></span>
  
> <span data-ttu-id="c4d83-110">由**lpli**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="c4d83-110">Count of values in the array pointed to by the **lpli** member.</span></span> 
    
 <span data-ttu-id="c4d83-111">**lpli**</span><span class="sxs-lookup"><span data-stu-id="c4d83-111">**lpli**</span></span>
  
> <span data-ttu-id="c4d83-112">指向**LARGE_INTEGER**结构包含的整数值的数组。</span><span class="sxs-lookup"><span data-stu-id="c4d83-112">Pointer to an array of **LARGE_INTEGER** structures holding the integer values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c4d83-113">说明</span><span class="sxs-lookup"><span data-stu-id="c4d83-113">Remarks</span></span>

<span data-ttu-id="c4d83-114">有关 PT_MV_18 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c4d83-114">For more information about PT_MV_18, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4d83-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4d83-115">See also</span></span>



[<span data-ttu-id="c4d83-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c4d83-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="c4d83-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c4d83-117">MAPI Structures</span></span>](mapi-structures.md)

