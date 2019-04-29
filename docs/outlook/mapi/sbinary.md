---
title: SBinary
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBinary
api_type:
- COM
ms.assetid: f21b5e6c-7a63-46bf-acbf-0e042e3519f7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 38263f46ccb50e1836f31d457f54f52abca7ce9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407842"
---
# <a name="sbinary"></a><span data-ttu-id="c4df6-103">SBinary</span><span class="sxs-lookup"><span data-stu-id="c4df6-103">SBinary</span></span>

  
  
<span data-ttu-id="c4df6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4df6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4df6-105">描述类型 PT_BINARY 的属性。</span><span class="sxs-lookup"><span data-stu-id="c4df6-105">Describes a property of type PT_BINARY.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c4df6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c4df6-106">Header file:</span></span>  <br/> |<span data-ttu-id="c4df6-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="c4df6-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBinary
{
  ULONG      cb;
  LPBYTE     lpb;
} SBinary, FAR *LPSBinary;

```

## <a name="members"></a><span data-ttu-id="c4df6-108">Members</span><span class="sxs-lookup"><span data-stu-id="c4df6-108">Members</span></span>

 <span data-ttu-id="c4df6-109">**cb**</span><span class="sxs-lookup"><span data-stu-id="c4df6-109">**cb**</span></span>
  
> <span data-ttu-id="c4df6-110">**lpb**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="c4df6-110">Count of bytes in the **lpb** member.</span></span> 
    
 <span data-ttu-id="c4df6-111">**lpb**</span><span class="sxs-lookup"><span data-stu-id="c4df6-111">**lpb**</span></span>
  
> <span data-ttu-id="c4df6-112">指向 PT_BINARY 属性值的指针。</span><span class="sxs-lookup"><span data-stu-id="c4df6-112">Pointer to the PT_BINARY property value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c4df6-113">说明</span><span class="sxs-lookup"><span data-stu-id="c4df6-113">Remarks</span></span>

<span data-ttu-id="c4df6-114">有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c4df6-114">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c4df6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4df6-115">See also</span></span>



[<span data-ttu-id="c4df6-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c4df6-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="c4df6-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c4df6-117">MAPI Structures</span></span>](mapi-structures.md)

