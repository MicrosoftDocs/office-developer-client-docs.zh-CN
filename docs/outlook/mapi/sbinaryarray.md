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
ms.openlocfilehash: e601a59a68a3a7d248165d4e573c5abc34d27e2a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586464"
---
# <a name="sbinaryarray"></a><span data-ttu-id="7ea39-103">SBinaryArray</span><span class="sxs-lookup"><span data-stu-id="7ea39-103">SBinaryArray</span></span>

  
  
<span data-ttu-id="7ea39-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ea39-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ea39-105">包含的二进制值的数组。</span><span class="sxs-lookup"><span data-stu-id="7ea39-105">Contains an array of binary values.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ea39-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="7ea39-106">Header file:</span></span>  <br/> |<span data-ttu-id="7ea39-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7ea39-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBinaryArray
{
  ULONG cValues;
  SBinary FAR *lpbin;
} SBinaryArray;

```

## <a name="members"></a><span data-ttu-id="7ea39-108">Members</span><span class="sxs-lookup"><span data-stu-id="7ea39-108">Members</span></span>

 <span data-ttu-id="7ea39-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="7ea39-109">**cValues**</span></span>
  
> <span data-ttu-id="7ea39-110">由**lpbin**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="7ea39-110">Count of values in the array pointed to by the **lpbin** member.</span></span> 
    
 <span data-ttu-id="7ea39-111">**lpbin**</span><span class="sxs-lookup"><span data-stu-id="7ea39-111">**lpbin**</span></span>
  
> <span data-ttu-id="7ea39-112">指向保存二进制值的数组[SBinary](sbinary.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7ea39-112">Pointer to an array of [SBinary](sbinary.md) structures that holds the binary values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7ea39-113">注解</span><span class="sxs-lookup"><span data-stu-id="7ea39-113">Remarks</span></span>

<span data-ttu-id="7ea39-114">**SBinaryArray**结构用于描述 PT_MV_BINARY 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="7ea39-114">The **SBinaryArray** structure is used to describe properties of type PT_MV_BINARY.</span></span> 
  
<span data-ttu-id="7ea39-115">有关 PT_MV_BINARY 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea39-115">For more information about PT_MV_BINARY, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ea39-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ea39-116">See also</span></span>



[<span data-ttu-id="7ea39-117">SBinary</span><span class="sxs-lookup"><span data-stu-id="7ea39-117">SBinary</span></span>](sbinary.md)
  
[<span data-ttu-id="7ea39-118">SPropValue</span><span class="sxs-lookup"><span data-stu-id="7ea39-118">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="7ea39-119">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="7ea39-119">MAPI Structures</span></span>](mapi-structures.md)

