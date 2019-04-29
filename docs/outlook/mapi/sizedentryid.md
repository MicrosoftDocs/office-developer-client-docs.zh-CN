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
ms.openlocfilehash: 88cf91330dea82dda490b81cc8de6fea0504baf7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405707"
---
# <a name="sizedentryid"></a><span data-ttu-id="a70f9-103">SizedENTRYID</span><span class="sxs-lookup"><span data-stu-id="a70f9-103">SizedENTRYID</span></span>

<span data-ttu-id="a70f9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a70f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a70f9-105">创建一个命名的[ENTRYID](entryid.md)结构, 其中包含指定大小的**ab**成员。</span><span class="sxs-lookup"><span data-stu-id="a70f9-105">Creates a named [ENTRYID](entryid.md) structure that contains an **ab** member of a specified size.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a70f9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a70f9-106">Header file:</span></span>  <br/> |<span data-ttu-id="a70f9-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="a70f9-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="a70f9-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="a70f9-108">Related structure:</span></span>  <br/> |<span data-ttu-id="a70f9-109">**ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="a70f9-109">**ENTRYID**</span></span> <br/> |
   
```cpp
SizedENTRYID (_cb, _name)
```

## <a name="parameters"></a><span data-ttu-id="a70f9-110">参数</span><span class="sxs-lookup"><span data-stu-id="a70f9-110">Parameters</span></span>

<span data-ttu-id="a70f9-111">__cb_</span><span class="sxs-lookup"><span data-stu-id="a70f9-111">__cb_</span></span>
  
> <span data-ttu-id="a70f9-112">新结构的**ab**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="a70f9-112">Count of bytes in the **ab** member of the new structure.</span></span> 
    
<span data-ttu-id="a70f9-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="a70f9-113">__name_</span></span>
  
> <span data-ttu-id="a70f9-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="a70f9-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a70f9-115">说明</span><span class="sxs-lookup"><span data-stu-id="a70f9-115">Remarks</span></span>

<span data-ttu-id="a70f9-116">**SizedENTRYID**宏允许您在已知数组长度要求后定义条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a70f9-116">The **SizedENTRYID** macro lets you define an entry identifier after array length requirements are known.</span></span> <span data-ttu-id="a70f9-117">使用此宏创建具有显式界限的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a70f9-117">Use this macro to create an entry identifier with explicit bounds.</span></span> 
  
<span data-ttu-id="a70f9-118">若要使用作为指向**ENTRYID**结构的指针的**SizedENTRYID**宏生成的新结构, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="a70f9-118">To use the new structure that results from the **SizedENTRYID** macro as a pointer to an **ENTRYID** structure, perform the following cast:</span></span> 
  
```cpp
lpENTRYID = (LPENTRYID) &SizedENTRYID;

```

## <a name="see-also"></a><span data-ttu-id="a70f9-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a70f9-119">See also</span></span>

- [<span data-ttu-id="a70f9-120">ENTRYID</span><span class="sxs-lookup"><span data-stu-id="a70f9-120">ENTRYID</span></span>](entryid.md)
- [<span data-ttu-id="a70f9-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="a70f9-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

