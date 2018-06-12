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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 553ec17e9caf9bf93278ff139eb94e02e6b48554
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778774"
---
# <a name="sguidarray"></a><span data-ttu-id="e8541-103">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="e8541-103">SGuidArray</span></span>

  
  
<span data-ttu-id="e8541-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e8541-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e8541-105">包含用于描述 PT_MV_CLSID 类型的属性的[GUID](guid.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="e8541-105">Contains an array of [GUID](guid.md) structures that are used to describe a property of type PT_MV_CLSID.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e8541-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e8541-106">Header file:</span></span>  <br/> |<span data-ttu-id="e8541-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e8541-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a><span data-ttu-id="e8541-108">成员</span><span class="sxs-lookup"><span data-stu-id="e8541-108">Members</span></span>

 <span data-ttu-id="e8541-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="e8541-109">**cValues**</span></span>
  
> <span data-ttu-id="e8541-110">由**lpguid**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="e8541-110">Count of values in the array pointed to by the **lpguid** member.</span></span> 
    
 <span data-ttu-id="e8541-111">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="e8541-111">**lpguid**</span></span>
  
> <span data-ttu-id="e8541-112">指针指向包含的类标识符值的**GUID**结构数组。</span><span class="sxs-lookup"><span data-stu-id="e8541-112">Pointer to an array of **GUID** structures that contains the class identifier values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e8541-113">备注</span><span class="sxs-lookup"><span data-stu-id="e8541-113">Remarks</span></span>

<span data-ttu-id="e8541-114">有关 PT_MV_CLSID 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="e8541-114">For more information about PT_MV_CLSID, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8541-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8541-115">See also</span></span>



[<span data-ttu-id="e8541-116">GUID</span><span class="sxs-lookup"><span data-stu-id="e8541-116">GUID</span></span>](guid.md)
  
[<span data-ttu-id="e8541-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e8541-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="e8541-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e8541-118">MAPI Structures</span></span>](mapi-structures.md)

