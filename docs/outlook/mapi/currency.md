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
ms.openlocfilehash: 0789b566eb814fe984ae78670d22ad2937b0c3a5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774745"
---
# <a name="currency"></a><span data-ttu-id="50adc-103">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="50adc-103">CURRENCY</span></span>

  
  
<span data-ttu-id="50adc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="50adc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="50adc-105">包含表示货币值有符号的 64 位整数。</span><span class="sxs-lookup"><span data-stu-id="50adc-105">Contains a signed 64-bit integer representing a currency value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="50adc-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="50adc-106">Header file:</span></span>  <br/> |<span data-ttu-id="50adc-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="50adc-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct tagCY
{
  unsigned long Lo;
  long Hi;
} CURRENCY;

```

## <a name="members"></a><span data-ttu-id="50adc-108">Members</span><span class="sxs-lookup"><span data-stu-id="50adc-108">Members</span></span>

 <span data-ttu-id="50adc-109">**Lo**</span><span class="sxs-lookup"><span data-stu-id="50adc-109">**Lo**</span></span>
  
> <span data-ttu-id="50adc-110">低序位 32 位的货币值。</span><span class="sxs-lookup"><span data-stu-id="50adc-110">Low-order 32 bits of the currency value.</span></span> 
    
 <span data-ttu-id="50adc-111">**你好**</span><span class="sxs-lookup"><span data-stu-id="50adc-111">**Hi**</span></span>
  
> <span data-ttu-id="50adc-112">货币值的高顺序 32 位。</span><span class="sxs-lookup"><span data-stu-id="50adc-112">High-order 32 bits of the currency value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="50adc-113">说明</span><span class="sxs-lookup"><span data-stu-id="50adc-113">Remarks</span></span>

<span data-ttu-id="50adc-114">**货币**结构是十进制数与小数点右边的四位数字的依比例调整的整数表示形式。</span><span class="sxs-lookup"><span data-stu-id="50adc-114">The **CURRENCY** structure is a scaled integer representation of a decimal number with four digits to the right of the decimal point.</span></span> <span data-ttu-id="50adc-115">例如，存储的值是 32.7500 的 327500 是 32.7500 的解释为表示货币值。</span><span class="sxs-lookup"><span data-stu-id="50adc-115">For example, a stored value of 327500 is to be construed as representing a currency value of 32.7500.</span></span> 
  
<span data-ttu-id="50adc-116">**货币**结构用于描述 PT_CURRENCY 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="50adc-116">The **CURRENCY** structure is used to describe a property of type PT_CURRENCY.</span></span> <span data-ttu-id="50adc-117">属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="50adc-117">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50adc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50adc-118">See also</span></span>



[<span data-ttu-id="50adc-119">SPropValue</span><span class="sxs-lookup"><span data-stu-id="50adc-119">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="50adc-120">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="50adc-120">MAPI Structures</span></span>](mapi-structures.md)

