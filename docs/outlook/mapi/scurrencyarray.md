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
ms.openlocfilehash: e9468d0c7fc7e46475afe19f12f225e53196639e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360695"
---
# <a name="scurrencyarray"></a><span data-ttu-id="d38a9-103">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="d38a9-103">SCurrencyArray</span></span>

  
  
<span data-ttu-id="d38a9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d38a9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d38a9-105">包含用于描述类型为 PT_MV_CURRENCY 的属性的货币值数组。</span><span class="sxs-lookup"><span data-stu-id="d38a9-105">Contains an array of currency values that are used to describe a property of type PT_MV_CURRENCY.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d38a9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d38a9-106">Header file:</span></span>  <br/> |<span data-ttu-id="d38a9-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d38a9-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a><span data-ttu-id="d38a9-108">Members</span><span class="sxs-lookup"><span data-stu-id="d38a9-108">Members</span></span>

 <span data-ttu-id="d38a9-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="d38a9-109">**cValues**</span></span>
  
> <span data-ttu-id="d38a9-110">由**lpcur**成员指向的数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="d38a9-110">Count of values in the array pointed to by the **lpcur** member.</span></span> 
    
 <span data-ttu-id="d38a9-111">**lpcur**</span><span class="sxs-lookup"><span data-stu-id="d38a9-111">**lpcur**</span></span>
  
> <span data-ttu-id="d38a9-112">指向包含货币值的[货币](currency.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="d38a9-112">Pointer to an array of [CURRENCY](currency.md) structures that contain the currency values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d38a9-113">注解</span><span class="sxs-lookup"><span data-stu-id="d38a9-113">Remarks</span></span>

<span data-ttu-id="d38a9-114">有关 PT_MV_CURRENCY 的信息, 请参阅[属性类型列表](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d38a9-114">For information about PT_MV_CURRENCY, see [List of Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d38a9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d38a9-115">See also</span></span>



[<span data-ttu-id="d38a9-116">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="d38a9-116">CURRENCY</span></span>](currency.md)
  
[<span data-ttu-id="d38a9-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d38a9-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="d38a9-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d38a9-118">MAPI Structures</span></span>](mapi-structures.md)

