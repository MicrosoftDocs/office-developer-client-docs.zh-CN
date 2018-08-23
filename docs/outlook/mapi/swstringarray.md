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
ms.openlocfilehash: e3f53a894b7f7cdaa68e66530c7bd99bf49b9ed0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581354"
---
# <a name="swstringarray"></a><span data-ttu-id="2f2d9-103">SWStringArray</span><span class="sxs-lookup"><span data-stu-id="2f2d9-103">SWStringArray</span></span>

  
  
<span data-ttu-id="2f2d9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2f2d9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2f2d9-105">包含用于描述 PT_MV_UNICODE 类型的属性的字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="2f2d9-105">Contains an array of character strings that are used to describe a property of type PT_MV_UNICODE.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2f2d9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2f2d9-106">Header file:</span></span>  <br/> |<span data-ttu-id="2f2d9-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2f2d9-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SWStringArray
{
  ULONG cValues;
  LPWSTR FAR *lppszW;
} SWStringArray;

```

## <a name="members"></a><span data-ttu-id="2f2d9-108">Members</span><span class="sxs-lookup"><span data-stu-id="2f2d9-108">Members</span></span>

 <span data-ttu-id="2f2d9-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="2f2d9-109">**cValues**</span></span>
  
> <span data-ttu-id="2f2d9-110">由**lppszW**成员指向的字符串数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="2f2d9-110">Count of strings in the array pointed to by the **lppszW** member.</span></span> 
    
 <span data-ttu-id="2f2d9-111">**lppszW**</span><span class="sxs-lookup"><span data-stu-id="2f2d9-111">**lppszW**</span></span>
  
> <span data-ttu-id="2f2d9-112">指向一个 null 结束 Unicode 字符的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="2f2d9-112">Pointer to an array of null-ended Unicode character strings.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2f2d9-113">注解</span><span class="sxs-lookup"><span data-stu-id="2f2d9-113">Remarks</span></span>

<span data-ttu-id="2f2d9-114">有关 PT_MV_UNICODE 的详细信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="2f2d9-114">For more information about PT_MV_UNICODE, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f2d9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f2d9-115">See also</span></span>



[<span data-ttu-id="2f2d9-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="2f2d9-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="2f2d9-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2f2d9-117">MAPI Structures</span></span>](mapi-structures.md)

