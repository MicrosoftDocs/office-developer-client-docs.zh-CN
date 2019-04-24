---
title: SLPSTRArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SLPSTRArray
api_type:
- COM
ms.assetid: 5f570d9b-eb3d-4fc7-bcbe-348a0b8fe9e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 987020bd6fd49fcba9453075cd502bd5cea4c3a3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361150"
---
# <a name="slpstrarray"></a><span data-ttu-id="6dce7-103">SLPSTRArray</span><span class="sxs-lookup"><span data-stu-id="6dce7-103">SLPSTRArray</span></span>

  
  
<span data-ttu-id="6dce7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6dce7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6dce7-105">包含字符串值的数组, 这些值用于描述 PT_MV_STRING8 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="6dce7-105">Contains an array of string values that are used to describe a property of type PT_MV_STRING8.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6dce7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6dce7-106">Header file:</span></span>  <br/> |<span data-ttu-id="6dce7-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6dce7-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SLPSTRArray
{
  ULONG cValues;
  LPSTR FAR *lppszA;
} SLPSTRArray;

```

## <a name="members"></a><span data-ttu-id="6dce7-108">Members</span><span class="sxs-lookup"><span data-stu-id="6dce7-108">Members</span></span>

 <span data-ttu-id="6dce7-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="6dce7-109">**cValues**</span></span>
  
> <span data-ttu-id="6dce7-110">由**lppszA**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="6dce7-110">Count of values in the array pointed to by the **lppszA** member.</span></span> 
    
 <span data-ttu-id="6dce7-111">**lppszA**</span><span class="sxs-lookup"><span data-stu-id="6dce7-111">**lppszA**</span></span>
  
> <span data-ttu-id="6dce7-112">指向空结束的8位字符字符串数组的指针。</span><span class="sxs-lookup"><span data-stu-id="6dce7-112">Pointer to an array of null-ended 8-bit character strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6dce7-113">注解</span><span class="sxs-lookup"><span data-stu-id="6dce7-113">Remarks</span></span>

<span data-ttu-id="6dce7-114">有关 PT_MV_STRING8 的详细信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="6dce7-114">For more information about PT_MV_STRING8, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6dce7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dce7-115">See also</span></span>



[<span data-ttu-id="6dce7-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="6dce7-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="6dce7-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="6dce7-117">MAPI Structures</span></span>](mapi-structures.md)

