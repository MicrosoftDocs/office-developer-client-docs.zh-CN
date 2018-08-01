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
ms.openlocfilehash: fe07ed7c7f9c76f82b54732c019b9b5f8beb5db2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778668"
---
# <a name="sbinary"></a><span data-ttu-id="9031e-103">SBinary</span><span class="sxs-lookup"><span data-stu-id="9031e-103">SBinary</span></span>

  
  
<span data-ttu-id="9031e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9031e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9031e-105">介绍 PT_BINARY 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="9031e-105">Describes a property of type PT_BINARY.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9031e-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9031e-106">Header file:</span></span>  <br/> |<span data-ttu-id="9031e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9031e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBinary
{
  ULONG      cb;
  LPBYTE     lpb;
} SBinary, FAR *LPSBinary;

```

## <a name="members"></a><span data-ttu-id="9031e-108">Members</span><span class="sxs-lookup"><span data-stu-id="9031e-108">Members</span></span>

 <span data-ttu-id="9031e-109">**cb**</span><span class="sxs-lookup"><span data-stu-id="9031e-109">**cb**</span></span>
  
> <span data-ttu-id="9031e-110">**Lpb**成员中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9031e-110">Count of bytes in the **lpb** member.</span></span> 
    
 <span data-ttu-id="9031e-111">**lpb**</span><span class="sxs-lookup"><span data-stu-id="9031e-111">**lpb**</span></span>
  
> <span data-ttu-id="9031e-112">指向 PT_BINARY 属性值的指针。</span><span class="sxs-lookup"><span data-stu-id="9031e-112">Pointer to the PT_BINARY property value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9031e-113">说明</span><span class="sxs-lookup"><span data-stu-id="9031e-113">Remarks</span></span>

<span data-ttu-id="9031e-114">属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9031e-114">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9031e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9031e-115">See also</span></span>



[<span data-ttu-id="9031e-116">SPropValue</span><span class="sxs-lookup"><span data-stu-id="9031e-116">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="9031e-117">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="9031e-117">MAPI Structures</span></span>](mapi-structures.md)

