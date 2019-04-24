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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f78e0ed939e190a9855ea4b040d18c01cfecc91d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357839"
---
# <a name="spropproblemarray"></a><span data-ttu-id="7a064-103">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="7a064-103">SPropProblemArray</span></span>

  
  
<span data-ttu-id="7a064-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7a064-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7a064-105">包含一个或多个[SPropProblem](spropproblem.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="7a064-105">Contains an array of one or more [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7a064-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7a064-106">Header file:</span></span>  <br/> |<span data-ttu-id="7a064-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7a064-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7a064-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="7a064-108">Related macros:</span></span>  <br/> |[<span data-ttu-id="7a064-109">CbNewSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="7a064-109">CbNewSPropProblemArray</span></span>](cbnewspropproblemarray.md) <br/> [<span data-ttu-id="7a064-110">CbSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="7a064-110">CbSPropProblemArray</span></span>](cbspropproblemarray.md) <br/> [<span data-ttu-id="7a064-111">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="7a064-111">SizedSPropProblemArray</span></span>](sizedspropproblemarray.md) <br/> |
   
```cpp
typedef struct _SPropProblemArray
{
  ULONG cProblem;
  SPropProblem aProblem[MAPI_DIM];
} SPropProblemArray, FAR *LPSPropProblemArray;

```

## <a name="members"></a><span data-ttu-id="7a064-112">Members</span><span class="sxs-lookup"><span data-stu-id="7a064-112">Members</span></span>

 <span data-ttu-id="7a064-113">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="7a064-113">**cProblem**</span></span>
  
> <span data-ttu-id="7a064-114">由**aProblem**成员指示的数组中的[SPropProblem](spropproblem.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="7a064-114">Count of [SPropProblem](spropproblem.md) structures in the array indicated by the **aProblem** member.</span></span> 
    
 <span data-ttu-id="7a064-115">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="7a064-115">**aProblem**</span></span>
  
> <span data-ttu-id="7a064-116">**SPropProblem**结构的数组, 每个结构描述属性错误。</span><span class="sxs-lookup"><span data-stu-id="7a064-116">Array of **SPropProblem** structures, each describing a property error.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7a064-117">注解</span><span class="sxs-lookup"><span data-stu-id="7a064-117">Remarks</span></span>

<span data-ttu-id="7a064-118">有关**SPropProblem**和**SPropProblemArray**结构如何处理与属性相关的错误的详细信息, 请参阅[MAPI 命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7a064-118">For more information about how the **SPropProblem** and **SPropProblemArray** structures work with errors related to properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7a064-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a064-119">See also</span></span>



[<span data-ttu-id="7a064-120">SCODE</span><span class="sxs-lookup"><span data-stu-id="7a064-120">SCODE</span></span>](scode.md)
  
[<span data-ttu-id="7a064-121">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="7a064-121">SPropProblem</span></span>](spropproblem.md)


[<span data-ttu-id="7a064-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="7a064-122">MAPI Structures</span></span>](mapi-structures.md)

