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
ms.openlocfilehash: 3d20a0932de0fb29ea73e56c37e262c0ccd062c3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339212"
---
# <a name="sguidarray"></a><span data-ttu-id="60c8a-103">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="60c8a-103">SGuidArray</span></span>

  
  
<span data-ttu-id="60c8a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="60c8a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="60c8a-105">包含用于描述类型为 PT_MV_CLSID 的属性的[GUID](guid.md)结构数组。</span><span class="sxs-lookup"><span data-stu-id="60c8a-105">Contains an array of [GUID](guid.md) structures that are used to describe a property of type PT_MV_CLSID.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="60c8a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="60c8a-106">Header file:</span></span>  <br/> |<span data-ttu-id="60c8a-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="60c8a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a><span data-ttu-id="60c8a-108">Members</span><span class="sxs-lookup"><span data-stu-id="60c8a-108">Members</span></span>

 <span data-ttu-id="60c8a-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="60c8a-109">**cValues**</span></span>
  
> <span data-ttu-id="60c8a-110">由**lpguid**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="60c8a-110">Count of values in the array pointed to by the **lpguid** member.</span></span> 
    
 <span data-ttu-id="60c8a-111">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="60c8a-111">**lpguid**</span></span>
  
> <span data-ttu-id="60c8a-112">指向包含类标识符值的**GUID**结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="60c8a-112">Pointer to an array of **GUID** structures that contains the class identifier values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="60c8a-113">注解</span><span class="sxs-lookup"><span data-stu-id="60c8a-113">Remarks</span></span>

<span data-ttu-id="60c8a-114">有关 PT_MV_CLSID 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="60c8a-114">For more information about PT_MV_CLSID, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="60c8a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60c8a-115">See also</span></span>



[<span data-ttu-id="60c8a-116">GUID</span><span class="sxs-lookup"><span data-stu-id="60c8a-116">GUID</span></span>](guid.md)
  
[<span data-ttu-id="60c8a-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="60c8a-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="60c8a-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="60c8a-118">MAPI Structures</span></span>](mapi-structures.md)

