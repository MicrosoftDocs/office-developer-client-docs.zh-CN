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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dee1de19ed61fa4f8edab69152315d77545b01b2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430383"
---
# <a name="sapptimearray"></a><span data-ttu-id="dd9ad-103">SAppTimeArray</span><span class="sxs-lookup"><span data-stu-id="dd9ad-103">SAppTimeArray</span></span>

  
  
<span data-ttu-id="dd9ad-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd9ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd9ad-105">包含时间值的数组。</span><span class="sxs-lookup"><span data-stu-id="dd9ad-105">Contains an array of time values.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd9ad-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="dd9ad-106">Header file:</span></span>  <br/> |<span data-ttu-id="dd9ad-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dd9ad-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SAppTimeArray
{
  ULONG cValues;
  double FAR *lpat;
} SAppTimeArray;

```

## <a name="members"></a><span data-ttu-id="dd9ad-108">Members</span><span class="sxs-lookup"><span data-stu-id="dd9ad-108">Members</span></span>

 <span data-ttu-id="dd9ad-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="dd9ad-109">**cValues**</span></span>
  
> <span data-ttu-id="dd9ad-110">lpat 成员指向的数组 **中的值** 计数。</span><span class="sxs-lookup"><span data-stu-id="dd9ad-110">Count of values in the array pointed to by the **lpat** member.</span></span> 
    
 <span data-ttu-id="dd9ad-111">**lpat**</span><span class="sxs-lookup"><span data-stu-id="dd9ad-111">**lpat**</span></span>
  
> <span data-ttu-id="dd9ad-112">指向应用程序时间值的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="dd9ad-112">Pointer to an array of application time values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="dd9ad-113">备注</span><span class="sxs-lookup"><span data-stu-id="dd9ad-113">Remarks</span></span>

<span data-ttu-id="dd9ad-114">**SAppTimeArray** 结构用于定义类型为 PT_MV_APPTIME。</span><span class="sxs-lookup"><span data-stu-id="dd9ad-114">The **SAppTimeArray** structure is used to define properties of type PT_MV_APPTIME.</span></span> <span data-ttu-id="dd9ad-115">有关属性类型PT_MV_APPTIME，请参阅 [属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="dd9ad-115">For more information about PT_MV_APPTIME, see [List of Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dd9ad-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd9ad-116">See also</span></span>



[<span data-ttu-id="dd9ad-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dd9ad-117">MAPI Structures</span></span>](mapi-structures.md)

