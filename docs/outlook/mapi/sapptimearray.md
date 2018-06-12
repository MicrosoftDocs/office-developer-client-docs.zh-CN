---
title: SAppTimeArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SAppTimeArray
api_type:
- COM
ms.assetid: 5a1ff95a-9862-4165-8a70-bd2eeb7fe683
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 834a7141f0e7150140fa27c21d88db422d6f5561
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778663"
---
# <a name="sapptimearray"></a><span data-ttu-id="c152e-103">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="c152e-103">SAppTimeArray</span></span>

  
  
<span data-ttu-id="c152e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c152e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c152e-105">包含数组的时间值。</span><span class="sxs-lookup"><span data-stu-id="c152e-105">Contains an array of time values.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c152e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c152e-106">Header file:</span></span>  <br/> |<span data-ttu-id="c152e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c152e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SAppTimeArray
{
  ULONG cValues;
  double FAR *lpat;
} SAppTimeArray;

```

## <a name="members"></a><span data-ttu-id="c152e-108">成员</span><span class="sxs-lookup"><span data-stu-id="c152e-108">Members</span></span>

 <span data-ttu-id="c152e-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="c152e-109">**cValues**</span></span>
  
> <span data-ttu-id="c152e-110">由**lpat**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="c152e-110">Count of values in the array pointed to by the **lpat** member.</span></span> 
    
 <span data-ttu-id="c152e-111">**lpat**</span><span class="sxs-lookup"><span data-stu-id="c152e-111">**lpat**</span></span>
  
> <span data-ttu-id="c152e-112">指向的应用程序时间值的数组。</span><span class="sxs-lookup"><span data-stu-id="c152e-112">Pointer to an array of application time values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c152e-113">备注</span><span class="sxs-lookup"><span data-stu-id="c152e-113">Remarks</span></span>

<span data-ttu-id="c152e-114">**SAppTimeArray**结构用于定义 PT_MV_APPTIME 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="c152e-114">The **SAppTimeArray** structure is used to define properties of type PT_MV_APPTIME.</span></span> <span data-ttu-id="c152e-115">有关 PT_MV_APPTIME 的详细信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c152e-115">For more information about PT_MV_APPTIME, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c152e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c152e-116">See also</span></span>



[<span data-ttu-id="c152e-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c152e-117">MAPI Structures</span></span>](mapi-structures.md)

