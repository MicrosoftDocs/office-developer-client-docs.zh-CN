---
title: SizedENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedENTRYID
api_type:
- COM
ms.assetid: 491170af-db35-4d7e-a912-44ffe8c7506b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d797acdbf2abfb88151d69d0c93e743f07afc5c9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563868"
---
# <a name="sizedentryid"></a><span data-ttu-id="e06f8-103">SizedENTRYID</span><span class="sxs-lookup"><span data-stu-id="e06f8-103">SizedENTRYID</span></span>

<span data-ttu-id="e06f8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e06f8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e06f8-105">创建包含的指定大小**ab**成员的命名的[ENTRYID](entryid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e06f8-105">Creates a named [ENTRYID](entryid.md) structure that contains an **ab** member of a specified size.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e06f8-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e06f8-106">Header file:</span></span>  <br/> |<span data-ttu-id="e06f8-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e06f8-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e06f8-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="e06f8-108">Related structure:</span></span>  <br/> |<span data-ttu-id="e06f8-109">**ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="e06f8-109">**ENTRYID**</span></span> <br/> |
   
```cpp
SizedENTRYID (_cb, _name)
```

## <a name="parameters"></a><span data-ttu-id="e06f8-110">参数</span><span class="sxs-lookup"><span data-stu-id="e06f8-110">Parameters</span></span>

<span data-ttu-id="e06f8-111">__cb_</span><span class="sxs-lookup"><span data-stu-id="e06f8-111">__cb_</span></span>
  
> <span data-ttu-id="e06f8-112">在新结构的**ab**成员的字节数。</span><span class="sxs-lookup"><span data-stu-id="e06f8-112">Count of bytes in the **ab** member of the new structure.</span></span> 
    
<span data-ttu-id="e06f8-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="e06f8-113">__name_</span></span>
  
> <span data-ttu-id="e06f8-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="e06f8-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e06f8-115">注解</span><span class="sxs-lookup"><span data-stu-id="e06f8-115">Remarks</span></span>

<span data-ttu-id="e06f8-116">**SizedENTRYID**宏允许您定义的项标识符后已知数组长度要求。</span><span class="sxs-lookup"><span data-stu-id="e06f8-116">The **SizedENTRYID** macro lets you define an entry identifier after array length requirements are known.</span></span> <span data-ttu-id="e06f8-117">使用此宏来使用显式边界创建的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e06f8-117">Use this macro to create an entry identifier with explicit bounds.</span></span> 
  
<span data-ttu-id="e06f8-118">若要使用新结构的结果从**SizedENTRYID**宏作为指针指向**ENTRYID**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="e06f8-118">To use the new structure that results from the **SizedENTRYID** macro as a pointer to an **ENTRYID** structure, perform the following cast:</span></span> 
  
```cpp
lpENTRYID = (LPENTRYID) &SizedENTRYID;

```

## <a name="see-also"></a><span data-ttu-id="e06f8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e06f8-119">See also</span></span>

- [<span data-ttu-id="e06f8-120">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="e06f8-120">ENTRYID</span></span>](entryid.md)
- [<span data-ttu-id="e06f8-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="e06f8-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

