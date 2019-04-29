---
title: SPropAttrArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropAttrArray
api_type:
- COM
ms.assetid: 30dd19d9-0840-49e9-aec6-ec8d19b1f91d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 55cba4f7cfb3fa8035117348b10ab1d6d3082710
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405511"
---
# <a name="spropattrarray"></a><span data-ttu-id="c5bc6-103">SPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="c5bc6-103">SPropAttrArray</span></span>

  
  
<span data-ttu-id="c5bc6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c5bc6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c5bc6-105">包含对象属性的属性列表。</span><span class="sxs-lookup"><span data-stu-id="c5bc6-105">Contains a list of attributes for properties of an object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c5bc6-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c5bc6-106">Header file:</span></span>  <br/> |<span data-ttu-id="c5bc6-107">Imessage</span><span class="sxs-lookup"><span data-stu-id="c5bc6-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="c5bc6-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="c5bc6-108">Related macros:</span></span>  <br/> |<span data-ttu-id="c5bc6-109">[CbNewSPropAttrArray](cbnewspropattrarray.md)、 [CbSPropAttrArray](cbspropattrarray.md)</span><span class="sxs-lookup"><span data-stu-id="c5bc6-109">[CbNewSPropAttrArray](cbnewspropattrarray.md), [CbSPropAttrArray](cbspropattrarray.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cValues;
  ULONG aPropAttr[MAPI_DIM];
} SPropAttrArray, FAR *LPSPropAttrArray;

```

## <a name="members"></a><span data-ttu-id="c5bc6-110">Members</span><span class="sxs-lookup"><span data-stu-id="c5bc6-110">Members</span></span>

 <span data-ttu-id="c5bc6-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="c5bc6-111">**cValues**</span></span>
  
> <span data-ttu-id="c5bc6-112">**aPropAttr**成员中属性属性的计数。</span><span class="sxs-lookup"><span data-stu-id="c5bc6-112">Count of property attributes in the **aPropAttr** member.</span></span> 
    
 <span data-ttu-id="c5bc6-113">**aPropAttr**</span><span class="sxs-lookup"><span data-stu-id="c5bc6-113">**aPropAttr**</span></span>
  
> <span data-ttu-id="c5bc6-114">属性属性的数组。</span><span class="sxs-lookup"><span data-stu-id="c5bc6-114">An array of property attributes.</span></span> <span data-ttu-id="c5bc6-115">属性的有效值如下所示:</span><span class="sxs-lookup"><span data-stu-id="c5bc6-115">Valid values for attributes are as follows:</span></span>
    
    - <span data-ttu-id="c5bc6-116">PROPATTR_MANDATORY</span><span class="sxs-lookup"><span data-stu-id="c5bc6-116">PROPATTR_MANDATORY</span></span>
    
    - <span data-ttu-id="c5bc6-117">PROPATTR_READABLE</span><span class="sxs-lookup"><span data-stu-id="c5bc6-117">PROPATTR_READABLE</span></span>
    
    - <span data-ttu-id="c5bc6-118">PROPATTR_WRITEABLE</span><span class="sxs-lookup"><span data-stu-id="c5bc6-118">PROPATTR_WRITEABLE</span></span>
    
    - <span data-ttu-id="c5bc6-119">PROPATTR_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="c5bc6-119">PROPATTR_NOT_PRESENT</span></span>
    
## <a name="remarks"></a><span data-ttu-id="c5bc6-120">说明</span><span class="sxs-lookup"><span data-stu-id="c5bc6-120">Remarks</span></span>

<span data-ttu-id="c5bc6-121">**SPropAttrArray**结构由实现[IPropData: IMAPIProp](ipropdataimapiprop.md)接口的属性数据对象使用。</span><span class="sxs-lookup"><span data-stu-id="c5bc6-121">The **SPropAttrArray** structure is used by property data objects that implement the [IPropData : IMAPIProp](ipropdataimapiprop.md) interface.</span></span> <span data-ttu-id="c5bc6-122">MAPI 的 IMAPIMessageSite (即基于结构化存储的[IUnknown](imapimessagesiteiunknown.md) ) 实现也使用它。</span><span class="sxs-lookup"><span data-stu-id="c5bc6-122">It is also used by MAPI's implementation of [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) that is based on structured storage.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c5bc6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5bc6-123">See also</span></span>



[<span data-ttu-id="c5bc6-124">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c5bc6-124">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="c5bc6-125">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c5bc6-125">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)
  
[<span data-ttu-id="c5bc6-126">CbNewSPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="c5bc6-126">CbNewSPropAttrArray</span></span>](cbnewspropattrarray.md)
  
[<span data-ttu-id="c5bc6-127">CbSPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="c5bc6-127">CbSPropAttrArray</span></span>](cbspropattrarray.md)


[<span data-ttu-id="c5bc6-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c5bc6-128">MAPI Structures</span></span>](mapi-structures.md)

