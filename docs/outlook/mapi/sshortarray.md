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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 59911531b6d8f9c094ef8563510aaa176e3a63b8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778879"
---
# <a name="sshortarray"></a><span data-ttu-id="ebc0a-103">SShortArray</span><span class="sxs-lookup"><span data-stu-id="ebc0a-103">SShortArray</span></span>

  
  
<span data-ttu-id="ebc0a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ebc0a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ebc0a-105">包含用于描述 PT_MV_SHORT 类型的属性的无符号的整数值的数组。</span><span class="sxs-lookup"><span data-stu-id="ebc0a-105">Contains an array of unsigned integer values that are used to describe a property of type PT_MV_SHORT.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ebc0a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ebc0a-106">Header file:</span></span>  <br/> |<span data-ttu-id="ebc0a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ebc0a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SShortArray
{
  ULONG cValues;
  short int FAR *lpi;
} SShortArray;

```

## <a name="members"></a><span data-ttu-id="ebc0a-108">成员</span><span class="sxs-lookup"><span data-stu-id="ebc0a-108">Members</span></span>

 <span data-ttu-id="ebc0a-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="ebc0a-109">**cValues**</span></span>
  
> <span data-ttu-id="ebc0a-110">由**lpi**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="ebc0a-110">Count of values in the array pointed to by the **lpi** member.</span></span> 
    
 <span data-ttu-id="ebc0a-111">**lpi**</span><span class="sxs-lookup"><span data-stu-id="ebc0a-111">**lpi**</span></span>
  
> <span data-ttu-id="ebc0a-112">为无符号的整数值的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="ebc0a-112">Pointer to an array of unsigned integer values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ebc0a-113">备注</span><span class="sxs-lookup"><span data-stu-id="ebc0a-113">Remarks</span></span>

<span data-ttu-id="ebc0a-114">有关 PT_MV_SHORT 和其他属性类型的详细信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="ebc0a-114">For more information about PT_MV_SHORT and other property types, see [Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ebc0a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebc0a-115">See also</span></span>



[<span data-ttu-id="ebc0a-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="ebc0a-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="ebc0a-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="ebc0a-117">MAPI Structures</span></span>](mapi-structures.md)

