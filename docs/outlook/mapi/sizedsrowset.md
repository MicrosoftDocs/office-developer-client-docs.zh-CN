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
ms.openlocfilehash: cb1e19a3f3703dc4943a5f6c322f1c8b429da5fa
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410929"
---
# <a name="sizedsrowset"></a><span data-ttu-id="7488b-103">SizedSRowSet</span><span class="sxs-lookup"><span data-stu-id="7488b-103">SizedSRowSet</span></span>

<span data-ttu-id="7488b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7488b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7488b-105">创建一个包含指定数量的行的命名[SRowSet](srowset.md)结构。</span><span class="sxs-lookup"><span data-stu-id="7488b-105">Creates a named [SRowSet](srowset.md) structure that contains a specified number of rows.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7488b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="7488b-106">Header file:</span></span>  <br/> |<span data-ttu-id="7488b-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7488b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="7488b-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="7488b-108">Related structure:</span></span>  <br/> |<span data-ttu-id="7488b-109">**SRowSet**</span><span class="sxs-lookup"><span data-stu-id="7488b-109">**SRowSet**</span></span> <br/> |
   
```cpp
SizedSRowSet (_crow, _name)
```

## <a name="parameters"></a><span data-ttu-id="7488b-110">参数</span><span class="sxs-lookup"><span data-stu-id="7488b-110">Parameters</span></span>

<span data-ttu-id="7488b-111">__鱼尾纹_</span><span class="sxs-lookup"><span data-stu-id="7488b-111">__crow_</span></span>
  
> <span data-ttu-id="7488b-112">要包含在新结构中的行数的计数。</span><span class="sxs-lookup"><span data-stu-id="7488b-112">Count of the number of rows to be included in the new structure.</span></span>
    
<span data-ttu-id="7488b-113">__名称_</span><span class="sxs-lookup"><span data-stu-id="7488b-113">__name_</span></span>
  
> <span data-ttu-id="7488b-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="7488b-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7488b-115">说明</span><span class="sxs-lookup"><span data-stu-id="7488b-115">Remarks</span></span>

<span data-ttu-id="7488b-116">若要使用作为指向**SRowSet**结构的指针的**SizedSRowSet**宏生成的新结构, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="7488b-116">To use the new structure that results from the **SizedSRowSet** macro as a pointer to an **SRowSet** structure, perform the following cast:</span></span> 
  
```cpp
lpSRowSet = (LPSRowSet) &SizedSRowSet;

```

## <a name="see-also"></a><span data-ttu-id="7488b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7488b-117">See also</span></span>

- [<span data-ttu-id="7488b-118">SRowSet</span><span class="sxs-lookup"><span data-stu-id="7488b-118">SRowSet</span></span>](srowset.md)
- [<span data-ttu-id="7488b-119">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="7488b-119">Macros Related to Structures</span></span>](macros-related-to-structures.md)

