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
ms.openlocfilehash: 7622baaebf6918cf84c48e53291cf5ec2c0b1a4a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572562"
---
# <a name="sizedssortorderset"></a><span data-ttu-id="dc05e-103">SizedSSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="dc05e-103">SizedSSortOrderSet</span></span>

<span data-ttu-id="dc05e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dc05e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dc05e-105">创建命名的[SSortOrderSet](ssortorderset.md)结构，其中包含指定的数目的排序次序。</span><span class="sxs-lookup"><span data-stu-id="dc05e-105">Creates a named [SSortOrderSet](ssortorderset.md) structure that contains a specified number of sort orders.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dc05e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="dc05e-106">Header file:</span></span>  <br/> |<span data-ttu-id="dc05e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dc05e-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="dc05e-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="dc05e-108">Related structure:</span></span>  <br/> |<span data-ttu-id="dc05e-109">**SSortOrderSet**</span><span class="sxs-lookup"><span data-stu-id="dc05e-109">**SSortOrderSet**</span></span> <br/> |
   
```cpp
SizedSSortOrderSet (_csort,_name)
```

## <a name="parameters"></a><span data-ttu-id="dc05e-110">参数</span><span class="sxs-lookup"><span data-stu-id="dc05e-110">Parameters</span></span>

<span data-ttu-id="dc05e-111">__csort_</span><span class="sxs-lookup"><span data-stu-id="dc05e-111">__csort_</span></span>
  
> <span data-ttu-id="dc05e-112">排序次序要包含的新结构中的计数。</span><span class="sxs-lookup"><span data-stu-id="dc05e-112">Count of sort orders to be included in the new structure.</span></span>
    
<span data-ttu-id="dc05e-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="dc05e-113">__name_</span></span>
  
> <span data-ttu-id="dc05e-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="dc05e-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dc05e-115">注解</span><span class="sxs-lookup"><span data-stu-id="dc05e-115">Remarks</span></span>

<span data-ttu-id="dc05e-116">使用**SizedSSortOrderSet**宏来创建使用显式边界设置排序顺序。</span><span class="sxs-lookup"><span data-stu-id="dc05e-116">Use the **SizedSSortOrderSet** macro to create a sort order set with explicit bounds.</span></span> 
  
<span data-ttu-id="dc05e-117">若要使用新结构的结果从**SizedSSortOrderSet**宏作为指针指向**SSortOrderSet**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="dc05e-117">To use the new structure that results from the **SizedSSortOrderSet** macro as a pointer to an **SSortOrderSet** structure, perform the following cast:</span></span> 
  
```cpp
lpSSortOrderSet = (LPSSortOrderSet) &SizedSSortOrderSet;

```

## <a name="see-also"></a><span data-ttu-id="dc05e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc05e-118">See also</span></span>

- [<span data-ttu-id="dc05e-119">SSortOrderSet</span><span class="sxs-lookup"><span data-stu-id="dc05e-119">SSortOrderSet</span></span>](ssortorderset.md)
- [<span data-ttu-id="dc05e-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="dc05e-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

