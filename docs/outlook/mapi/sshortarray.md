---
title: SShortArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SShortArray
api_type:
- COM
ms.assetid: 201ceb76-41bc-4d7b-835d-5196bf3dc234
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8ea7d51b15a6e6acd44a3c0b6158378661f311bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344497"
---
# <a name="sshortarray"></a><span data-ttu-id="fee50-103">SShortArray</span><span class="sxs-lookup"><span data-stu-id="fee50-103">SShortArray</span></span>

  
  
<span data-ttu-id="fee50-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fee50-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fee50-105">包含用于描述类型为 PT_MV_SHORT 的属性的无符号整数值数组。</span><span class="sxs-lookup"><span data-stu-id="fee50-105">Contains an array of unsigned integer values that are used to describe a property of type PT_MV_SHORT.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fee50-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fee50-106">Header file:</span></span>  <br/> |<span data-ttu-id="fee50-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fee50-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SShortArray
{
  ULONG cValues;
  short int FAR *lpi;
} SShortArray;

```

## <a name="members"></a><span data-ttu-id="fee50-108">Members</span><span class="sxs-lookup"><span data-stu-id="fee50-108">Members</span></span>

 <span data-ttu-id="fee50-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="fee50-109">**cValues**</span></span>
  
> <span data-ttu-id="fee50-110">由**lpi**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="fee50-110">Count of values in the array pointed to by the **lpi** member.</span></span> 
    
 <span data-ttu-id="fee50-111">**越高**</span><span class="sxs-lookup"><span data-stu-id="fee50-111">**lpi**</span></span>
  
> <span data-ttu-id="fee50-112">指向无符号整数值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="fee50-112">Pointer to an array of unsigned integer values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fee50-113">注解</span><span class="sxs-lookup"><span data-stu-id="fee50-113">Remarks</span></span>

<span data-ttu-id="fee50-114">有关 PT_MV_SHORT 和其他属性类型的详细信息, 请参阅[property types](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="fee50-114">For more information about PT_MV_SHORT and other property types, see [Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fee50-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fee50-115">See also</span></span>



[<span data-ttu-id="fee50-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="fee50-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="fee50-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="fee50-117">MAPI Structures</span></span>](mapi-structures.md)

