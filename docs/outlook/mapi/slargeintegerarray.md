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
ms.openlocfilehash: ab82fff2645a5e1861523eb3f1866e0ddc7d13a5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331386"
---
# <a name="slargeintegerarray"></a><span data-ttu-id="bbb4b-103">SLargeIntegerArray</span><span class="sxs-lookup"><span data-stu-id="bbb4b-103">SLargeIntegerArray</span></span>

  
  
<span data-ttu-id="bbb4b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bbb4b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bbb4b-105">包含用于描述 PT_MV_I8 类型的属性的[LARGE_INTEGER](https://go.microsoft.com/fwlink/?LinkId=132130)结构数组。</span><span class="sxs-lookup"><span data-stu-id="bbb4b-105">Contains an array of [LARGE_INTEGER](https://go.microsoft.com/fwlink/?LinkId=132130) structures that are used to describe a property of type PT_MV_I8.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bbb4b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="bbb4b-106">Header file:</span></span>  <br/> |<span data-ttu-id="bbb4b-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="bbb4b-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLargeIntegerArray
{
  ULONG cValues;
  LARGE_INTEGER FAR *lpli;
} SLargeIntegerArray;

```

## <a name="members"></a><span data-ttu-id="bbb4b-108">Members</span><span class="sxs-lookup"><span data-stu-id="bbb4b-108">Members</span></span>

 <span data-ttu-id="bbb4b-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="bbb4b-109">**cValues**</span></span>
  
> <span data-ttu-id="bbb4b-110">由**lpli**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="bbb4b-110">Count of values in the array pointed to by the **lpli** member.</span></span> 
    
 <span data-ttu-id="bbb4b-111">**lpli**</span><span class="sxs-lookup"><span data-stu-id="bbb4b-111">**lpli**</span></span>
  
> <span data-ttu-id="bbb4b-112">指向保存整数值的**LARGE_INTEGER**结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="bbb4b-112">Pointer to an array of **LARGE_INTEGER** structures holding the integer values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="bbb4b-113">注解</span><span class="sxs-lookup"><span data-stu-id="bbb4b-113">Remarks</span></span>

<span data-ttu-id="bbb4b-114">有关 PT_MV_18 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="bbb4b-114">For more information about PT_MV_18, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbb4b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbb4b-115">See also</span></span>



[<span data-ttu-id="bbb4b-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="bbb4b-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="bbb4b-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="bbb4b-117">MAPI Structures</span></span>](mapi-structures.md)

