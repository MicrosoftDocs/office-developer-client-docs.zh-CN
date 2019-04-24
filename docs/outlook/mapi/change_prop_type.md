---
title: CHANGE_PROP_TYPE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.CHANGE_PROP_TYPE
api_type:
- COM
ms.assetid: 95513b5a-fd3b-46f2-a6c0-094500ae4ca7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ee1b84e36ef014fab87ca910115675c905f6a09
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332639"
---
# <a name="changeproptype"></a><span data-ttu-id="7b8b9-103">CHANGE_PROP_TYPE</span><span class="sxs-lookup"><span data-stu-id="7b8b9-103">CHANGE_PROP_TYPE</span></span>

  
  
<span data-ttu-id="7b8b9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b8b9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b8b9-105">将属性标记的属性类型更新为指定的值。</span><span class="sxs-lookup"><span data-stu-id="7b8b9-105">Updates the property type of a property tag to a specified value.</span></span> <span data-ttu-id="7b8b9-106">属性标识符保持不变。</span><span class="sxs-lookup"><span data-stu-id="7b8b9-106">The property identifier is unchanged.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7b8b9-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7b8b9-107">Header file:</span></span>  <br/> |<span data-ttu-id="7b8b9-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7b8b9-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7b8b9-109">相关结构:</span><span class="sxs-lookup"><span data-stu-id="7b8b9-109">Related structure:</span></span>  <br/> |[<span data-ttu-id="7b8b9-110">SPropValue</span><span class="sxs-lookup"><span data-stu-id="7b8b9-110">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
CHANGE_PROP_TYPE (ulPropTag, ulPropType)
```

## <a name="parameters"></a><span data-ttu-id="7b8b9-111">参数</span><span class="sxs-lookup"><span data-stu-id="7b8b9-111">Parameters</span></span>

 <span data-ttu-id="7b8b9-112">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="7b8b9-112">_ulPropTag_</span></span>
  
> <span data-ttu-id="7b8b9-113">要修改的属性标记。</span><span class="sxs-lookup"><span data-stu-id="7b8b9-113">The property tag to be modified.</span></span>
    
 <span data-ttu-id="7b8b9-114">_ulPropType_</span><span class="sxs-lookup"><span data-stu-id="7b8b9-114">_ulPropType_</span></span>
  
> <span data-ttu-id="7b8b9-115">属性类型的新值。</span><span class="sxs-lookup"><span data-stu-id="7b8b9-115">The new value for the property type.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7b8b9-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b8b9-116">See also</span></span>



[<span data-ttu-id="7b8b9-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="7b8b9-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="7b8b9-118">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="7b8b9-118">Macros Related to Structures</span></span>](macros-related-to-structures.md)

