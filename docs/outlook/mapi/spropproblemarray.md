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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406855"
---
# <a name="spropproblemarray"></a><span data-ttu-id="f7561-103">SPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f7561-103">SPropProblemArray</span></span>

  
  
<span data-ttu-id="f7561-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7561-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7561-105">包含一个或多个 [SPropProblem 结构的](spropproblem.md) 数组。</span><span class="sxs-lookup"><span data-stu-id="f7561-105">Contains an array of one or more [SPropProblem](spropproblem.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f7561-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f7561-106">Header file:</span></span>  <br/> |<span data-ttu-id="f7561-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f7561-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f7561-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="f7561-108">Related macros:</span></span>  <br/> |[<span data-ttu-id="f7561-109">CbNewSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f7561-109">CbNewSPropProblemArray</span></span>](cbnewspropproblemarray.md) <br/> [<span data-ttu-id="f7561-110">CbSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f7561-110">CbSPropProblemArray</span></span>](cbspropproblemarray.md) <br/> [<span data-ttu-id="f7561-111">SizedSPropProblemArray</span><span class="sxs-lookup"><span data-stu-id="f7561-111">SizedSPropProblemArray</span></span>](sizedspropproblemarray.md) <br/> |
   
```cpp
typedef struct _SPropProblemArray
{
  ULONG cProblem;
  SPropProblem aProblem[MAPI_DIM];
} SPropProblemArray, FAR *LPSPropProblemArray;

```

## <a name="members"></a><span data-ttu-id="f7561-112">Members</span><span class="sxs-lookup"><span data-stu-id="f7561-112">Members</span></span>

 <span data-ttu-id="f7561-113">**cProblem**</span><span class="sxs-lookup"><span data-stu-id="f7561-113">**cProblem**</span></span>
  
> <span data-ttu-id="f7561-114">由 [aProblem](spropproblem.md) 成员指示的数组中的 **SPropProblem 结构** 计数。</span><span class="sxs-lookup"><span data-stu-id="f7561-114">Count of [SPropProblem](spropproblem.md) structures in the array indicated by the **aProblem** member.</span></span> 
    
 <span data-ttu-id="f7561-115">**aProblem**</span><span class="sxs-lookup"><span data-stu-id="f7561-115">**aProblem**</span></span>
  
> <span data-ttu-id="f7561-116">**SPropProblem** 结构数组，每个结构描述一个属性错误。</span><span class="sxs-lookup"><span data-stu-id="f7561-116">Array of **SPropProblem** structures, each describing a property error.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f7561-117">备注</span><span class="sxs-lookup"><span data-stu-id="f7561-117">Remarks</span></span>

<span data-ttu-id="f7561-118">有关 **SPropProblem** 和 **SPropProblemArray** 结构如何处理与属性相关的错误的详细信息，请参阅 [MAPI Named Properties](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f7561-118">For more information about how the **SPropProblem** and **SPropProblemArray** structures work with errors related to properties, see [MAPI Named Properties](mapi-named-properties.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f7561-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7561-119">See also</span></span>



[<span data-ttu-id="f7561-120">SCODE</span><span class="sxs-lookup"><span data-stu-id="f7561-120">SCODE</span></span>](scode.md)
  
[<span data-ttu-id="f7561-121">SPropProblem</span><span class="sxs-lookup"><span data-stu-id="f7561-121">SPropProblem</span></span>](spropproblem.md)


[<span data-ttu-id="f7561-122">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f7561-122">MAPI Structures</span></span>](mapi-structures.md)

