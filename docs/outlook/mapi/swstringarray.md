---
title: SWStringArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SWStringArray
api_type:
- COM
ms.assetid: c1ae24ad-1bbb-4dee-b414-b5226593b6fa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1578e26ec96f69975c2304cb185f352193a52c2d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778930"
---
# <a name="swstringarray"></a><span data-ttu-id="dc53f-103">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="dc53f-103">SWStringArray</span></span>

  
  
<span data-ttu-id="dc53f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dc53f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dc53f-105">包含用于描述 PT_MV_UNICODE 类型的属性的字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="dc53f-105">Contains an array of character strings that are used to describe a property of type PT_MV_UNICODE.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dc53f-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="dc53f-106">Header file:</span></span>  <br/> |<span data-ttu-id="dc53f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc53f-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SWStringArray
{
  ULONG cValues;
  LPWSTR FAR *lppszW;
} SWStringArray;

```

## <a name="members"></a><span data-ttu-id="dc53f-108">Members</span><span class="sxs-lookup"><span data-stu-id="dc53f-108">Members</span></span>

 <span data-ttu-id="dc53f-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="dc53f-109">**cValues**</span></span>
  
> <span data-ttu-id="dc53f-110">由**lppszW**成员指向的字符串数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="dc53f-110">Count of strings in the array pointed to by the **lppszW** member.</span></span> 
    
 <span data-ttu-id="dc53f-111">**lppszW**</span><span class="sxs-lookup"><span data-stu-id="dc53f-111">**lppszW**</span></span>
  
> <span data-ttu-id="dc53f-112">指向一个 null 结束 Unicode 字符的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="dc53f-112">Pointer to an array of null-ended Unicode character strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dc53f-113">说明</span><span class="sxs-lookup"><span data-stu-id="dc53f-113">Remarks</span></span>

<span data-ttu-id="dc53f-114">有关 PT_MV_UNICODE 的详细信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="dc53f-114">For more information about PT_MV_UNICODE, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc53f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc53f-115">See also</span></span>



[<span data-ttu-id="dc53f-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="dc53f-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="dc53f-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dc53f-117">MAPI Structures</span></span>](mapi-structures.md)

