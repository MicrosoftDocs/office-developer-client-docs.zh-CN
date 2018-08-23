---
title: SGuidArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SGuidArray
api_type:
- COM
ms.assetid: 2091e5fc-75c8-4ea4-87e9-a9bf508e9c58
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc0ae6d69db6077c17d2efa66d04a5366f2395a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585568"
---
# <a name="sguidarray"></a><span data-ttu-id="e3d34-103">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="e3d34-103">SGuidArray</span></span>

  
  
<span data-ttu-id="e3d34-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e3d34-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e3d34-105">包含用于描述 PT_MV_CLSID 类型的属性的[GUID](guid.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="e3d34-105">Contains an array of [GUID](guid.md) structures that are used to describe a property of type PT_MV_CLSID.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e3d34-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e3d34-106">Header file:</span></span>  <br/> |<span data-ttu-id="e3d34-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e3d34-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a><span data-ttu-id="e3d34-108">Members</span><span class="sxs-lookup"><span data-stu-id="e3d34-108">Members</span></span>

 <span data-ttu-id="e3d34-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="e3d34-109">**cValues**</span></span>
  
> <span data-ttu-id="e3d34-110">由**lpguid**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="e3d34-110">Count of values in the array pointed to by the **lpguid** member.</span></span> 
    
 <span data-ttu-id="e3d34-111">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="e3d34-111">**lpguid**</span></span>
  
> <span data-ttu-id="e3d34-112">指针指向包含的类标识符值的**GUID**结构数组。</span><span class="sxs-lookup"><span data-stu-id="e3d34-112">Pointer to an array of **GUID** structures that contains the class identifier values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e3d34-113">注解</span><span class="sxs-lookup"><span data-stu-id="e3d34-113">Remarks</span></span>

<span data-ttu-id="e3d34-114">有关 PT_MV_CLSID 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e3d34-114">For more information about PT_MV_CLSID, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e3d34-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3d34-115">See also</span></span>



[<span data-ttu-id="e3d34-116">GUID</span><span class="sxs-lookup"><span data-stu-id="e3d34-116">GUID</span></span>](guid.md)
  
[<span data-ttu-id="e3d34-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e3d34-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="e3d34-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e3d34-118">MAPI Structures</span></span>](mapi-structures.md)

