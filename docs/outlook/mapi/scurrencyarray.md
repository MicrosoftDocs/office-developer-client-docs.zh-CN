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
ms.openlocfilehash: 1b262ba9c83e9890719f716a373c566be172ae73
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572450"
---
# <a name="scurrencyarray"></a><span data-ttu-id="cd05d-103">SCurrencyArray</span><span class="sxs-lookup"><span data-stu-id="cd05d-103">SCurrencyArray</span></span>

  
  
<span data-ttu-id="cd05d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd05d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd05d-105">包含用于描述 PT_MV_CURRENCY 类型的属性的货币值的数组。</span><span class="sxs-lookup"><span data-stu-id="cd05d-105">Contains an array of currency values that are used to describe a property of type PT_MV_CURRENCY.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="cd05d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="cd05d-106">Header file:</span></span>  <br/> |<span data-ttu-id="cd05d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cd05d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a><span data-ttu-id="cd05d-108">Members</span><span class="sxs-lookup"><span data-stu-id="cd05d-108">Members</span></span>

 <span data-ttu-id="cd05d-109">**cValues**</span><span class="sxs-lookup"><span data-stu-id="cd05d-109">**cValues**</span></span>
  
> <span data-ttu-id="cd05d-110">由**lpcur**成员指向数组中的值的数目。</span><span class="sxs-lookup"><span data-stu-id="cd05d-110">Count of values in the array pointed to by the **lpcur** member.</span></span> 
    
 <span data-ttu-id="cd05d-111">**lpcur**</span><span class="sxs-lookup"><span data-stu-id="cd05d-111">**lpcur**</span></span>
  
> <span data-ttu-id="cd05d-112">指向的[货币](currency.md)结构包含货币值的数组。</span><span class="sxs-lookup"><span data-stu-id="cd05d-112">Pointer to an array of [CURRENCY](currency.md) structures that contain the currency values.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="cd05d-113">注解</span><span class="sxs-lookup"><span data-stu-id="cd05d-113">Remarks</span></span>

<span data-ttu-id="cd05d-114">有关 PT_MV_CURRENCY 的信息，请参阅[列表的属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cd05d-114">For information about PT_MV_CURRENCY, see [List of Property Types](property-types.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cd05d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd05d-115">See also</span></span>



[<span data-ttu-id="cd05d-116">CURRENCY</span><span class="sxs-lookup"><span data-stu-id="cd05d-116">CURRENCY</span></span>](currency.md)
  
[<span data-ttu-id="cd05d-117">SPropValue</span><span class="sxs-lookup"><span data-stu-id="cd05d-117">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="cd05d-118">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="cd05d-118">MAPI Structures</span></span>](mapi-structures.md)

