---
title: SCurrencyArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCurrencyArray
api_type:
- COM
ms.assetid: d28852ab-b542-40e1-b2ec-85d20a2eddfd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c440bb7d8f3d2d3002a4d1a80ca3a671b49f4d2b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778720"
---
# <a name="scurrencyarray"></a><span data-ttu-id="7cda1-103">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="7cda1-103">SCurrencyArray</span></span>

  
  
<span data-ttu-id="7cda1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7cda1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7cda1-105">包含用于描述 PT_MV_CURRENCY 类型的属性的货币值的数组。</span><span class="sxs-lookup"><span data-stu-id="7cda1-105">Contains an array of currency values that are used to describe a property of type PT_MV_CURRENCY.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7cda1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="7cda1-106">Header file:</span></span>  <br/> |<span data-ttu-id="7cda1-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7cda1-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a><span data-ttu-id="7cda1-108">Members</span><span class="sxs-lookup"><span data-stu-id="7cda1-108">Members</span></span>

 <span data-ttu-id="7cda1-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="7cda1-109">**cValues**</span></span>
  
> <span data-ttu-id="7cda1-110">由**lpcur**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="7cda1-110">Count of values in the array pointed to by the **lpcur** member.</span></span> 
    
 <span data-ttu-id="7cda1-111">**lpcur**</span><span class="sxs-lookup"><span data-stu-id="7cda1-111">**lpcur**</span></span>
  
> <span data-ttu-id="7cda1-112">指向的[货币](currency.md)结构包含货币值的数组。</span><span class="sxs-lookup"><span data-stu-id="7cda1-112">Pointer to an array of [CURRENCY](currency.md) structures that contain the currency values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7cda1-113">说明</span><span class="sxs-lookup"><span data-stu-id="7cda1-113">Remarks</span></span>

<span data-ttu-id="7cda1-114">有关 PT_MV_CURRENCY 的信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="7cda1-114">For information about PT_MV_CURRENCY, see [List of Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7cda1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7cda1-115">See also</span></span>



[<span data-ttu-id="7cda1-116">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="7cda1-116">CURRENCY</span></span>](currency.md)
  
[<span data-ttu-id="7cda1-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="7cda1-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="7cda1-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="7cda1-118">MAPI Structures</span></span>](mapi-structures.md)

