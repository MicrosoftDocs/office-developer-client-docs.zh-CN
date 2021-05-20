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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429612"
---
# <a name="sshortarray"></a><span data-ttu-id="766c2-103">SShortArray</span><span class="sxs-lookup"><span data-stu-id="766c2-103">SShortArray</span></span>

  
  
<span data-ttu-id="766c2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="766c2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="766c2-105">包含一个无符号整数值的数组，这些值用于描述类型为 PT_MV_SHORT。</span><span class="sxs-lookup"><span data-stu-id="766c2-105">Contains an array of unsigned integer values that are used to describe a property of type PT_MV_SHORT.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="766c2-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="766c2-106">Header file:</span></span>  <br/> |<span data-ttu-id="766c2-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="766c2-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SShortArray
{
  ULONG cValues;
  short int FAR *lpi;
} SShortArray;

```

## <a name="members"></a><span data-ttu-id="766c2-108">Members</span><span class="sxs-lookup"><span data-stu-id="766c2-108">Members</span></span>

 <span data-ttu-id="766c2-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="766c2-109">**cValues**</span></span>
  
> <span data-ttu-id="766c2-110">lpi 成员指向的数组 **中的值** 计数。</span><span class="sxs-lookup"><span data-stu-id="766c2-110">Count of values in the array pointed to by the **lpi** member.</span></span> 
    
 <span data-ttu-id="766c2-111">**lpi**</span><span class="sxs-lookup"><span data-stu-id="766c2-111">**lpi**</span></span>
  
> <span data-ttu-id="766c2-112">指向无符号整数值的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="766c2-112">Pointer to an array of unsigned integer values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="766c2-113">备注</span><span class="sxs-lookup"><span data-stu-id="766c2-113">Remarks</span></span>

<span data-ttu-id="766c2-114">有关属性类型PT_MV_SHORT，请参阅属性 [类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="766c2-114">For more information about PT_MV_SHORT and other property types, see [Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="766c2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="766c2-115">See also</span></span>



[<span data-ttu-id="766c2-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="766c2-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="766c2-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="766c2-117">MAPI Structures</span></span>](mapi-structures.md)

