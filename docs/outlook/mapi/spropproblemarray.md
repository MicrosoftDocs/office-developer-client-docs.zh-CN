---
title: SPropProblemArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropProblemArray
api_type:
- COM
ms.assetid: 3fbaa77a-be43-4fce-af67-1826ee101799
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 3fd61828cd631c4abc0131da867ca213a3c44d20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778866"
---
# <a name="spropproblemarray"></a><span data-ttu-id="2d850-103">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="2d850-103">SPropProblemArray</span></span>

  
  
<span data-ttu-id="2d850-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="2d850-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="2d850-105">包含一个或多个[SPropProblem](spropproblem.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="2d850-105">Contains an array of one or more [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2d850-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="2d850-106">Header file:</span></span>  <br/> |<span data-ttu-id="2d850-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2d850-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2d850-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="2d850-108">Related macros:</span></span>  <br/> |[<span data-ttu-id="2d850-109">CbNewSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="2d850-109">CbNewSPropProblemArray</span></span>](cbnewspropproblemarray.md) <br/> [<span data-ttu-id="2d850-110">CbSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="2d850-110">CbSPropProblemArray</span></span>](cbspropproblemarray.md) <br/> [<span data-ttu-id="2d850-111">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="2d850-111">SizedSPropProblemArray</span></span>](sizedspropproblemarray.md) <br/> |
   
```cpp
typedef struct _SPropProblemArray
{
  ULONG cProblem;
  SPropProblem aProblem[MAPI_DIM];
} SPropProblemArray, FAR *LPSPropProblemArray;

```

## <a name="members"></a><span data-ttu-id="2d850-112">成员</span><span class="sxs-lookup"><span data-stu-id="2d850-112">Members</span></span>

 <span data-ttu-id="2d850-113">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="2d850-113">**cProblem**</span></span>
  
> <span data-ttu-id="2d850-114">[SPropProblem](spropproblem.md)结构由**aProblem**成员数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="2d850-114">Count of [SPropProblem](spropproblem.md) structures in the array indicated by the **aProblem** member.</span></span> 
    
 <span data-ttu-id="2d850-115">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="2d850-115">**aProblem**</span></span>
  
> <span data-ttu-id="2d850-116">每个描述属性错误的**SPropProblem**结构数组。</span><span class="sxs-lookup"><span data-stu-id="2d850-116">Array of **SPropProblem** structures, each describing a property error.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="2d850-117">备注</span><span class="sxs-lookup"><span data-stu-id="2d850-117">Remarks</span></span>

<span data-ttu-id="2d850-118">有关的**SPropProblem**和**SPropProblemArray**结构有属性相关的错误的工作原理的详细信息，请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="2d850-118">For more information about how the **SPropProblem** and **SPropProblemArray** structures work with errors related to properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2d850-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d850-119">See also</span></span>



[<span data-ttu-id="2d850-120">SCODE</span><span class="sxs-lookup"><span data-stu-id="2d850-120">SCODE</span></span>](scode.md)
  
[<span data-ttu-id="2d850-121">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="2d850-121">SPropProblem</span></span>](spropproblem.md)


[<span data-ttu-id="2d850-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="2d850-122">MAPI Structures</span></span>](mapi-structures.md)

