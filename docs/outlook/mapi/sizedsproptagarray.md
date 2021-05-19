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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f873ad5234460f9f1781c7427b60d285f7486196
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429346"
---
# <a name="sizedsproptagarray"></a><span data-ttu-id="eb1a3-103">SizedSPropTagArray</span><span class="sxs-lookup"><span data-stu-id="eb1a3-103">SizedSPropTagArray</span></span>

<span data-ttu-id="eb1a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eb1a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eb1a3-105">创建一个名为 [SPropTagArray](sproptagarray.md) 的结构，其中包含指定数量的属性标记。</span><span class="sxs-lookup"><span data-stu-id="eb1a3-105">Creates a named [SPropTagArray](sproptagarray.md) structure that includes a specified number of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="eb1a3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="eb1a3-106">Header file:</span></span>  <br/> |<span data-ttu-id="eb1a3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="eb1a3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="eb1a3-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="eb1a3-108">Related structure:</span></span>  <br/> |<span data-ttu-id="eb1a3-109">**SPropTagArray**</span><span class="sxs-lookup"><span data-stu-id="eb1a3-109">**SPropTagArray**</span></span> <br/> |
   
```cpp
SizedSPropTagArray (_ctag, _name)
```

## <a name="parameters"></a><span data-ttu-id="eb1a3-110">参数</span><span class="sxs-lookup"><span data-stu-id="eb1a3-110">Parameters</span></span>

<span data-ttu-id="eb1a3-111">_ _ctag_</span><span class="sxs-lookup"><span data-stu-id="eb1a3-111">_ _ctag_</span></span>
  
> <span data-ttu-id="eb1a3-112">要包含在新结构中的属性标记的计数。</span><span class="sxs-lookup"><span data-stu-id="eb1a3-112">Count of property tags to be included in the new structure.</span></span>
    
<span data-ttu-id="eb1a3-113">_ _name_</span><span class="sxs-lookup"><span data-stu-id="eb1a3-113">_ _name_</span></span>
  
> <span data-ttu-id="eb1a3-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="eb1a3-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="eb1a3-115">备注</span><span class="sxs-lookup"><span data-stu-id="eb1a3-115">Remarks</span></span>

<span data-ttu-id="eb1a3-116">使用 **SizedSPropTagArray** 宏创建具有显式边界的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="eb1a3-116">Use the **SizedSPropTagArray** macro to create a property tag array with explicit bounds.</span></span> 
  
<span data-ttu-id="eb1a3-117">若要使用由 **SizedSPropTagArray** 宏产生的新结构作为 **指向 SPropTagArray** 结构的指针，请执行以下转换：</span><span class="sxs-lookup"><span data-stu-id="eb1a3-117">To use the new structure that results from the **SizedSPropTagArray** macro as a pointer to an **SPropTagArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropTagArray = (LPPropTagArray) &SizedSPropTagArray;

```

## <a name="see-also"></a><span data-ttu-id="eb1a3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb1a3-118">See also</span></span>

- [<span data-ttu-id="eb1a3-119">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="eb1a3-119">SPropTagArray</span></span>](sproptagarray.md)
- [<span data-ttu-id="eb1a3-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="eb1a3-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

