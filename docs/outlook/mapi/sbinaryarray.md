---
title: SBinaryArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBinaryArray
api_type:
- COM
ms.assetid: 2d5b7302-cad2-4522-beb1-7c6c711f42e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12fefbe15491837878608540006e5dd7dc3033ea
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351056"
---
# <a name="sbinaryarray"></a><span data-ttu-id="56513-103">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="56513-103">SBinaryArray</span></span>

  
  
<span data-ttu-id="56513-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="56513-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="56513-105">包含二进制值数组。</span><span class="sxs-lookup"><span data-stu-id="56513-105">Contains an array of binary values.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="56513-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="56513-106">Header file:</span></span>  <br/> |<span data-ttu-id="56513-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="56513-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBinaryArray
{
  ULONG cValues;
  SBinary FAR *lpbin;
} SBinaryArray;

```

## <a name="members"></a><span data-ttu-id="56513-108">Members</span><span class="sxs-lookup"><span data-stu-id="56513-108">Members</span></span>

 <span data-ttu-id="56513-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="56513-109">**cValues**</span></span>
  
> <span data-ttu-id="56513-110">由**lpbin**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="56513-110">Count of values in the array pointed to by the **lpbin** member.</span></span> 
    
 <span data-ttu-id="56513-111">**lpbin**</span><span class="sxs-lookup"><span data-stu-id="56513-111">**lpbin**</span></span>
  
> <span data-ttu-id="56513-112">指向保存二进制值的[SBinary](sbinary.md)结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="56513-112">Pointer to an array of [SBinary](sbinary.md) structures that holds the binary values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="56513-113">注解</span><span class="sxs-lookup"><span data-stu-id="56513-113">Remarks</span></span>

<span data-ttu-id="56513-114">**SBinaryArray**结构用于描述 PT_MV_BINARY 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="56513-114">The **SBinaryArray** structure is used to describe properties of type PT_MV_BINARY.</span></span> 
  
<span data-ttu-id="56513-115">有关 PT_MV_BINARY 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="56513-115">For more information about PT_MV_BINARY, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56513-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56513-116">See also</span></span>



[<span data-ttu-id="56513-117">SBinary</span><span class="sxs-lookup"><span data-stu-id="56513-117">SBinary</span></span>](sbinary.md)
  
[<span data-ttu-id="56513-118">SPropValue</span><span class="sxs-lookup"><span data-stu-id="56513-118">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="56513-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="56513-119">MAPI Structures</span></span>](mapi-structures.md)

