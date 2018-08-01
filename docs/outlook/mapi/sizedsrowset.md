---
title: SizedSRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedSRowSet
api_type:
- COM
ms.assetid: 419e2c6d-ac3b-46c6-9a12-33f51f6d7f12
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8b7a93a9abb9a1c589ac7fdab3723c9c924eea0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778798"
---
# <a name="sizedsrowset"></a><span data-ttu-id="cdec4-103">SizedSRowSet</span><span class="sxs-lookup"><span data-stu-id="cdec4-103">SizedSRowSet</span></span>

<span data-ttu-id="cdec4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cdec4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cdec4-105">创建命名的[SRowSet](srowset.md)结构，其中包含指定的行数。</span><span class="sxs-lookup"><span data-stu-id="cdec4-105">Creates a named [SRowSet](srowset.md) structure that contains a specified number of rows.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cdec4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="cdec4-106">Header file:</span></span>  <br/> |<span data-ttu-id="cdec4-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cdec4-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="cdec4-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="cdec4-108">Related structure:</span></span>  <br/> |<span data-ttu-id="cdec4-109">**SRowSet**</span><span class="sxs-lookup"><span data-stu-id="cdec4-109">**SRowSet**</span></span> <br/> |
   
```cpp
SizedSRowSet (_crow, _name)
```

## <a name="parameters"></a><span data-ttu-id="cdec4-110">参数</span><span class="sxs-lookup"><span data-stu-id="cdec4-110">Parameters</span></span>

<span data-ttu-id="cdec4-111">__crow_</span><span class="sxs-lookup"><span data-stu-id="cdec4-111">__crow_</span></span>
  
> <span data-ttu-id="cdec4-112">要包含的新结构中的行数的计数。</span><span class="sxs-lookup"><span data-stu-id="cdec4-112">Count of the number of rows to be included in the new structure.</span></span>
    
<span data-ttu-id="cdec4-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="cdec4-113">__name_</span></span>
  
> <span data-ttu-id="cdec4-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="cdec4-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cdec4-115">说明</span><span class="sxs-lookup"><span data-stu-id="cdec4-115">Remarks</span></span>

<span data-ttu-id="cdec4-116">若要使用新结构的结果从**SizedSRowSet**宏作为指针指向**SRowSet**结构，执行下列转换：</span><span class="sxs-lookup"><span data-stu-id="cdec4-116">To use the new structure that results from the **SizedSRowSet** macro as a pointer to an **SRowSet** structure, perform the following cast:</span></span> 
  
```cpp
lpSRowSet = (LPSRowSet) &SizedSRowSet;

```

## <a name="see-also"></a><span data-ttu-id="cdec4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdec4-117">See also</span></span>

- [<span data-ttu-id="cdec4-118">SRowSet</span><span class="sxs-lookup"><span data-stu-id="cdec4-118">SRowSet</span></span>](srowset.md)
- [<span data-ttu-id="cdec4-119">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="cdec4-119">Macros Related to Structures</span></span>](macros-related-to-structures.md)

