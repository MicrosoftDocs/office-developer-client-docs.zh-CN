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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424922"
---
# <a name="sguidarray"></a><span data-ttu-id="057fe-103">SGuidArray</span><span class="sxs-lookup"><span data-stu-id="057fe-103">SGuidArray</span></span>

  
  
<span data-ttu-id="057fe-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="057fe-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="057fe-105">包含一个 [GUID](guid.md) 结构数组，用于描述类型为 PT_MV_CLSID。</span><span class="sxs-lookup"><span data-stu-id="057fe-105">Contains an array of [GUID](guid.md) structures that are used to describe a property of type PT_MV_CLSID.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="057fe-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="057fe-106">Header file:</span></span>  <br/> |<span data-ttu-id="057fe-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="057fe-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SGuidArray
{
  ULONG cValues;
  GUID FAR *lpguid;
} SGuidArray;

```

## <a name="members"></a><span data-ttu-id="057fe-108">Members</span><span class="sxs-lookup"><span data-stu-id="057fe-108">Members</span></span>

 <span data-ttu-id="057fe-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="057fe-109">**cValues**</span></span>
  
> <span data-ttu-id="057fe-110">**lpguid** 成员指向的数组中的值计数。</span><span class="sxs-lookup"><span data-stu-id="057fe-110">Count of values in the array pointed to by the **lpguid** member.</span></span> 
    
 <span data-ttu-id="057fe-111">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="057fe-111">**lpguid**</span></span>
  
> <span data-ttu-id="057fe-112">指向包含类标识符值的 **GUID** 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="057fe-112">Pointer to an array of **GUID** structures that contains the class identifier values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="057fe-113">备注</span><span class="sxs-lookup"><span data-stu-id="057fe-113">Remarks</span></span>

<span data-ttu-id="057fe-114">有关属性类型PT_MV_CLSID，请参阅 [属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="057fe-114">For more information about PT_MV_CLSID, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="057fe-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="057fe-115">See also</span></span>



[<span data-ttu-id="057fe-116">GUID</span><span class="sxs-lookup"><span data-stu-id="057fe-116">GUID</span></span>](guid.md)
  
[<span data-ttu-id="057fe-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="057fe-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="057fe-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="057fe-118">MAPI Structures</span></span>](mapi-structures.md)

