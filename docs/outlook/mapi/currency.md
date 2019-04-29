---
title: CURRENCY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CURRENCY
api_type:
- COM
ms.assetid: cffc05a0-95e4-4b9f-bf8f-c4272a75afa8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dccb6b19af72d0f748a3a513b7f3d78904ebc789
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431118"
---
# <a name="currency"></a><span data-ttu-id="ff159-103">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="ff159-103">CURRENCY</span></span>

  
  
<span data-ttu-id="ff159-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff159-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff159-105">包含一个表示货币值的已签名的64位整数。</span><span class="sxs-lookup"><span data-stu-id="ff159-105">Contains a signed 64-bit integer representing a currency value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ff159-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ff159-106">Header file:</span></span>  <br/> |<span data-ttu-id="ff159-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ff159-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct tagCY
{
  unsigned long Lo;
  long Hi;
} CURRENCY;

```

## <a name="members"></a><span data-ttu-id="ff159-108">Members</span><span class="sxs-lookup"><span data-stu-id="ff159-108">Members</span></span>

 <span data-ttu-id="ff159-109">**高低**</span><span class="sxs-lookup"><span data-stu-id="ff159-109">**Lo**</span></span>
  
> <span data-ttu-id="ff159-110">货币值的低序位32位。</span><span class="sxs-lookup"><span data-stu-id="ff159-110">Low-order 32 bits of the currency value.</span></span> 
    
 <span data-ttu-id="ff159-111">**你好**</span><span class="sxs-lookup"><span data-stu-id="ff159-111">**Hi**</span></span>
  
> <span data-ttu-id="ff159-112">货币值的高序位32位。</span><span class="sxs-lookup"><span data-stu-id="ff159-112">High-order 32 bits of the currency value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff159-113">说明</span><span class="sxs-lookup"><span data-stu-id="ff159-113">Remarks</span></span>

<span data-ttu-id="ff159-114">**货币**结构是十进制数的缩放整数表示形式, 小数点右边有四位数字。</span><span class="sxs-lookup"><span data-stu-id="ff159-114">The **CURRENCY** structure is a scaled integer representation of a decimal number with four digits to the right of the decimal point.</span></span> <span data-ttu-id="ff159-115">例如, 存储的327500值将被解释为表示货币值32.7500。</span><span class="sxs-lookup"><span data-stu-id="ff159-115">For example, a stored value of 327500 is to be construed as representing a currency value of 32.7500.</span></span> 
  
<span data-ttu-id="ff159-116">**货币**结构用于描述类型为 PT_CURRENCY 的属性。</span><span class="sxs-lookup"><span data-stu-id="ff159-116">The **CURRENCY** structure is used to describe a property of type PT_CURRENCY.</span></span> <span data-ttu-id="ff159-117">有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="ff159-117">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff159-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff159-118">See also</span></span>



[<span data-ttu-id="ff159-119">SPropValue</span><span class="sxs-lookup"><span data-stu-id="ff159-119">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="ff159-120">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="ff159-120">MAPI Structures</span></span>](mapi-structures.md)

