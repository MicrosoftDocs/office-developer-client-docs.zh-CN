---
title: SizedSPropTagArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSPropTagArray
api_type:
- COM
ms.assetid: 1d2dc6e9-735d-4b5b-af6f-adf6a32a666d
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 7505c5dbcfc98a8b868424ae51cbe9c47b1d4338
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778799"
---
# <a name="sizedsproptagarray"></a><span data-ttu-id="6e187-103">SizedSPropTagArray</span><span class="sxs-lookup"><span data-stu-id="6e187-103">SizedSPropTagArray</span></span>

<span data-ttu-id="6e187-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6e187-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6e187-105">创建命名的[SPropTagArray](sproptagarray.md)结构，其中包含指定的数目的属性标记。</span><span class="sxs-lookup"><span data-stu-id="6e187-105">Creates a named [SPropTagArray](sproptagarray.md) structure that includes a specified number of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6e187-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="6e187-106">Header file:</span></span>  <br/> |<span data-ttu-id="6e187-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6e187-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="6e187-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="6e187-108">Related structure:</span></span>  <br/> |<span data-ttu-id="6e187-109">**SPropTagArray**</span><span class="sxs-lookup"><span data-stu-id="6e187-109">**SPropTagArray**</span></span> <br/> |
   
```cpp
SizedSPropTagArray (_ctag, _name)
```

## <a name="parameters"></a><span data-ttu-id="6e187-110">参数</span><span class="sxs-lookup"><span data-stu-id="6e187-110">Parameters</span></span>

<span data-ttu-id="6e187-111">__ctag_</span><span class="sxs-lookup"><span data-stu-id="6e187-111">__ctag_</span></span>
  
> <span data-ttu-id="6e187-112">要包含在新结构属性标记的计数。</span><span class="sxs-lookup"><span data-stu-id="6e187-112">Count of property tags to be included in the new structure.</span></span>
    
<span data-ttu-id="6e187-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="6e187-113">__name_</span></span>
  
> <span data-ttu-id="6e187-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="6e187-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e187-115">备注</span><span class="sxs-lookup"><span data-stu-id="6e187-115">Remarks</span></span>

<span data-ttu-id="6e187-116">使用**SizedSPropTagArray**宏来使用显式边界创建属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="6e187-116">Use the **SizedSPropTagArray** macro to create a property tag array with explicit bounds.</span></span> 
  
<span data-ttu-id="6e187-117">若要使用新结构的结果从**SizedSPropTagArray**宏作为指针指向**SPropTagArray**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="6e187-117">To use the new structure that results from the **SizedSPropTagArray** macro as a pointer to an **SPropTagArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropTagArray = (LPPropTagArray) &SizedSPropTagArray;

```

## <a name="see-also"></a><span data-ttu-id="6e187-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e187-118">See also</span></span>

- [<span data-ttu-id="6e187-119">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="6e187-119">SPropTagArray</span></span>](sproptagarray.md)
- [<span data-ttu-id="6e187-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="6e187-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

