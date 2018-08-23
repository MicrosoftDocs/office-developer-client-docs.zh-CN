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
ms.openlocfilehash: a8f4e62a8eb1b5e61cb0223c66b921e15ab9423b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577679"
---
# <a name="spropattrarray"></a><span data-ttu-id="bf6bb-103">SPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="bf6bb-103">SPropAttrArray</span></span>

  
  
<span data-ttu-id="bf6bb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bf6bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bf6bb-105">包含对象的属性的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="bf6bb-105">Contains a list of attributes for properties of an object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bf6bb-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bf6bb-106">Header file:</span></span>  <br/> |<span data-ttu-id="bf6bb-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="bf6bb-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="bf6bb-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="bf6bb-108">Related macros:</span></span>  <br/> |<span data-ttu-id="bf6bb-109">[CbNewSPropAttrArray](cbnewspropattrarray.md) [CbSPropAttrArray](cbspropattrarray.md)</span><span class="sxs-lookup"><span data-stu-id="bf6bb-109">[CbNewSPropAttrArray](cbnewspropattrarray.md), [CbSPropAttrArray](cbspropattrarray.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cValues;
  ULONG aPropAttr[MAPI_DIM];
} SPropAttrArray, FAR *LPSPropAttrArray;

```

## <a name="members"></a><span data-ttu-id="bf6bb-110">Members</span><span class="sxs-lookup"><span data-stu-id="bf6bb-110">Members</span></span>

 <span data-ttu-id="bf6bb-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="bf6bb-111">**cValues**</span></span>
  
> <span data-ttu-id="bf6bb-112">在**aPropAttr**成员中声明 property 属性的计数。</span><span class="sxs-lookup"><span data-stu-id="bf6bb-112">Count of property attributes in the **aPropAttr** member.</span></span> 
    
 <span data-ttu-id="bf6bb-113">**aPropAttr**</span><span class="sxs-lookup"><span data-stu-id="bf6bb-113">**aPropAttr**</span></span>
  
> <span data-ttu-id="bf6bb-114">一个 property 属性的数组。</span><span class="sxs-lookup"><span data-stu-id="bf6bb-114">An array of property attributes.</span></span> <span data-ttu-id="bf6bb-115">属性的有效值如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf6bb-115">Valid values for attributes are as follows:</span></span>
    
    - <span data-ttu-id="bf6bb-116">PROPATTR_MANDATORY</span><span class="sxs-lookup"><span data-stu-id="bf6bb-116">PROPATTR_MANDATORY</span></span>
    
    - <span data-ttu-id="bf6bb-117">PROPATTR_READABLE</span><span class="sxs-lookup"><span data-stu-id="bf6bb-117">PROPATTR_READABLE</span></span>
    
    - <span data-ttu-id="bf6bb-118">PROPATTR_WRITEABLE</span><span class="sxs-lookup"><span data-stu-id="bf6bb-118">PROPATTR_WRITEABLE</span></span>
    
    - <span data-ttu-id="bf6bb-119">PROPATTR_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="bf6bb-119">PROPATTR_NOT_PRESENT</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bf6bb-120">注解</span><span class="sxs-lookup"><span data-stu-id="bf6bb-120">Remarks</span></span>

<span data-ttu-id="bf6bb-121">**SPropAttrArray**结构由实现的属性数据对象[IPropData: IMAPIProp](ipropdataimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bf6bb-121">The **SPropAttrArray** structure is used by property data objects that implement the [IPropData : IMAPIProp](ipropdataimapiprop.md) interface.</span></span> <span data-ttu-id="bf6bb-122">MAPI 的实现还使用[IMAPIMessageSite: IUnknown](imapimessagesiteiunknown.md) ，它是基于结构化的存储。</span><span class="sxs-lookup"><span data-stu-id="bf6bb-122">It is also used by MAPI's implementation of [IMAPIMessageSite : IUnknown](imapimessagesiteiunknown.md) that is based on structured storage.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bf6bb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf6bb-123">See also</span></span>



[<span data-ttu-id="bf6bb-124">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="bf6bb-124">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="bf6bb-125">IMAPIMessageSite : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bf6bb-125">IMAPIMessageSite : IUnknown</span></span>](imapimessagesiteiunknown.md)
  
[<span data-ttu-id="bf6bb-126">CbNewSPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="bf6bb-126">CbNewSPropAttrArray</span></span>](cbnewspropattrarray.md)
  
[<span data-ttu-id="bf6bb-127">CbSPropAttrArray</span><span class="sxs-lookup"><span data-stu-id="bf6bb-127">CbSPropAttrArray</span></span>](cbspropattrarray.md)


[<span data-ttu-id="bf6bb-128">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="bf6bb-128">MAPI Structures</span></span>](mapi-structures.md)

