---
title: SizedSSortOrderSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSSortOrderSet
api_type:
- COM
ms.assetid: f0b9c2f4-7011-414d-8e6c-ab22893ef132
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 60a335f85eea8778580e0bd74693a5c28591103c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428604"
---
# <a name="sizedssortorderset"></a><span data-ttu-id="06571-103">SizedSSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="06571-103">SizedSSortOrderSet</span></span>

<span data-ttu-id="06571-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06571-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06571-105">创建一个名为 [SSortOrderSet](ssortorderset.md) 的结构，其中包含指定数量的排序顺序。</span><span class="sxs-lookup"><span data-stu-id="06571-105">Creates a named [SSortOrderSet](ssortorderset.md) structure that contains a specified number of sort orders.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="06571-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="06571-106">Header file:</span></span>  <br/> |<span data-ttu-id="06571-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="06571-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="06571-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="06571-108">Related structure:</span></span>  <br/> |<span data-ttu-id="06571-109">**SSortOrderSet**</span><span class="sxs-lookup"><span data-stu-id="06571-109">**SSortOrderSet**</span></span> <br/> |
   
```cpp
SizedSSortOrderSet (_csort,_name)
```

## <a name="parameters"></a><span data-ttu-id="06571-110">参数</span><span class="sxs-lookup"><span data-stu-id="06571-110">Parameters</span></span>

<span data-ttu-id="06571-111">_ _csort_</span><span class="sxs-lookup"><span data-stu-id="06571-111">_ _csort_</span></span>
  
> <span data-ttu-id="06571-112">要包含在新结构中的排序顺序计数。</span><span class="sxs-lookup"><span data-stu-id="06571-112">Count of sort orders to be included in the new structure.</span></span>
    
<span data-ttu-id="06571-113">_ _name_</span><span class="sxs-lookup"><span data-stu-id="06571-113">_ _name_</span></span>
  
> <span data-ttu-id="06571-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="06571-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="06571-115">备注</span><span class="sxs-lookup"><span data-stu-id="06571-115">Remarks</span></span>

<span data-ttu-id="06571-116">使用 **SizedSSortOrderSet** 宏创建具有显式边界的排序顺序集。</span><span class="sxs-lookup"><span data-stu-id="06571-116">Use the **SizedSSortOrderSet** macro to create a sort order set with explicit bounds.</span></span> 
  
<span data-ttu-id="06571-117">若要使用由 **SizedSSortOrderSet** 宏产生的新结构作为 **指向 SSortOrderSet** 结构的指针，请执行以下转换：</span><span class="sxs-lookup"><span data-stu-id="06571-117">To use the new structure that results from the **SizedSSortOrderSet** macro as a pointer to an **SSortOrderSet** structure, perform the following cast:</span></span> 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a><span data-ttu-id="06571-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06571-118">See also</span></span>

- [<span data-ttu-id="06571-119">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="06571-119">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="06571-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="06571-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

