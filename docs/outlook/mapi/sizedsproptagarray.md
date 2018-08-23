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
ms.openlocfilehash: 363a85e1c6f111936b16e471eda6b9f962f8b65d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573619"
---
# <a name="sizedsproptagarray"></a><span data-ttu-id="fae00-103">SizedSPropTagArray</span><span class="sxs-lookup"><span data-stu-id="fae00-103">SizedSPropTagArray</span></span>

<span data-ttu-id="fae00-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fae00-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fae00-105">创建命名的[SPropTagArray](sproptagarray.md)结构，其中包含指定的数目的属性标记。</span><span class="sxs-lookup"><span data-stu-id="fae00-105">Creates a named [SPropTagArray](sproptagarray.md) structure that includes a specified number of property tags.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fae00-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="fae00-106">Header file:</span></span>  <br/> |<span data-ttu-id="fae00-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fae00-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fae00-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="fae00-108">Related structure:</span></span>  <br/> |<span data-ttu-id="fae00-109">**SPropTagArray**</span><span class="sxs-lookup"><span data-stu-id="fae00-109">**SPropTagArray**</span></span> <br/> |
   
```cpp
SizedSPropTagArray (_ctag, _name)
```

## <a name="parameters"></a><span data-ttu-id="fae00-110">参数</span><span class="sxs-lookup"><span data-stu-id="fae00-110">Parameters</span></span>

<span data-ttu-id="fae00-111">__ctag_</span><span class="sxs-lookup"><span data-stu-id="fae00-111">__ctag_</span></span>
  
> <span data-ttu-id="fae00-112">要包含在新结构属性标记的计数。</span><span class="sxs-lookup"><span data-stu-id="fae00-112">Count of property tags to be included in the new structure.</span></span>
    
<span data-ttu-id="fae00-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="fae00-113">__name_</span></span>
  
> <span data-ttu-id="fae00-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="fae00-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fae00-115">注解</span><span class="sxs-lookup"><span data-stu-id="fae00-115">Remarks</span></span>

<span data-ttu-id="fae00-116">使用**SizedSPropTagArray**宏来使用显式边界创建属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="fae00-116">Use the **SizedSPropTagArray** macro to create a property tag array with explicit bounds.</span></span> 
  
<span data-ttu-id="fae00-117">若要使用新结构的结果从**SizedSPropTagArray**宏作为指针指向**SPropTagArray**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="fae00-117">To use the new structure that results from the **SizedSPropTagArray** macro as a pointer to an **SPropTagArray** structure, perform the following cast:</span></span> 
  
```cpp
lpPropTagArray = (LPPropTagArray) &SizedSPropTagArray;

```

## <a name="see-also"></a><span data-ttu-id="fae00-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fae00-118">See also</span></span>

- [<span data-ttu-id="fae00-119">SPropTagArray</span><span class="sxs-lookup"><span data-stu-id="fae00-119">SPropTagArray</span></span>](sproptagarray.md)
- [<span data-ttu-id="fae00-120">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="fae00-120">Macros Related to Structures</span></span>](macros-related-to-structures.md)

