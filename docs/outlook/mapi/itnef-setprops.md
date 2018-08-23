---
title: ITnefSetProps
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.SetProps
api_type:
- COM
ms.assetid: 09e4b427-316b-4630-9f3d-81e74f040d7b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 81f9388b67d3194fe1442091b9f4f75a7671cb6d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579646"
---
# <a name="itnefsetprops"></a><span data-ttu-id="8452b-103">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="8452b-103">ITnef::SetProps</span></span>

  
  
<span data-ttu-id="8452b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8452b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8452b-105">设置用于封装的邮件或附件的一个或多个属性的值，而无需修改原始邮件或附件。</span><span class="sxs-lookup"><span data-stu-id="8452b-105">Sets the value of one or more properties for an encapsulated message or attachment without modifying the original message or attachment.</span></span> 
  
```cpp
HRESULT SetProps(
  ULONG ulFlags,
  ULONG ulElemID,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a><span data-ttu-id="8452b-106">参数</span><span class="sxs-lookup"><span data-stu-id="8452b-106">Parameters</span></span>

 <span data-ttu-id="8452b-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="8452b-107">_ulFlags_</span></span>
  
> <span data-ttu-id="8452b-108">[in]位掩码的标志的控制设置属性值的方式。</span><span class="sxs-lookup"><span data-stu-id="8452b-108">[in] A bitmask of flags that controls how property values are set.</span></span> <span data-ttu-id="8452b-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="8452b-109">The following flag can be set:</span></span>
    
<span data-ttu-id="8452b-110">TNEF_PROP_CONTAINED</span><span class="sxs-lookup"><span data-stu-id="8452b-110">TNEF_PROP_CONTAINED</span></span> 
  
> <span data-ttu-id="8452b-111">将编码仅从邮件或附件_ulElemID_参数指定的属性。</span><span class="sxs-lookup"><span data-stu-id="8452b-111">Encodes only properties from the message or attachment specified by the  _ulElemID_ parameter.</span></span> 
    
 <span data-ttu-id="8452b-112">_ulElemID_</span><span class="sxs-lookup"><span data-stu-id="8452b-112">_ulElemID_</span></span>
  
> <span data-ttu-id="8452b-113">[in]附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个数字唯一地标识其父邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="8452b-113">[in] An attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property, which contains a number that uniquely identifies the attachment in its parent message.</span></span>
    
 <span data-ttu-id="8452b-114">_cValues_</span><span class="sxs-lookup"><span data-stu-id="8452b-114">_cValues_</span></span>
  
> <span data-ttu-id="8452b-115">[in]_LpProps_参数指向[SPropValue](spropvalue.md)结构中的属性值的数目。</span><span class="sxs-lookup"><span data-stu-id="8452b-115">[in] The number of property values in the [SPropValue](spropvalue.md) structure pointed to by the  _lpProps_ parameter.</span></span> 
    
 <span data-ttu-id="8452b-116">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="8452b-116">_lpProps_</span></span>
  
> <span data-ttu-id="8452b-117">[in]一个指向**SPropValue**结构，其中包含要设置的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="8452b-117">[in] A pointer to an **SPropValue** structure that contains the property values of the properties to set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="8452b-118">返回值</span><span class="sxs-lookup"><span data-stu-id="8452b-118">Return value</span></span>

<span data-ttu-id="8452b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="8452b-119">S_OK</span></span> 
  
> <span data-ttu-id="8452b-120">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="8452b-120">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8452b-121">注解</span><span class="sxs-lookup"><span data-stu-id="8452b-121">Remarks</span></span>

<span data-ttu-id="8452b-122">传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::SetProps**方法可设置属性包括在邮件或附件封装而无需修改的原始邮件或附件。</span><span class="sxs-lookup"><span data-stu-id="8452b-122">Transport providers, message store providers, and gateways call the **ITnef::SetProps** method to set properties to include in the encapsulation of a message or an attachment without modifying the original message or attachment.</span></span> <span data-ttu-id="8452b-123">与此呼叫设置的所有属性重都写封装的消息中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="8452b-123">Any properties set with this call override existing properties in the encapsulated message.</span></span> 
  
 <span data-ttu-id="8452b-124">**SetProps**仅支持使用 TNEF_ENCODE 标志[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="8452b-124">**SetProps** is supported only for TNEF objects that are opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> <span data-ttu-id="8452b-125">与此呼叫，可以设置任意数量的属性。</span><span class="sxs-lookup"><span data-stu-id="8452b-125">Any number of properties can be set with this call.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8452b-126">无实际 TNEF 编码的**SetProps**直到调用[ITnef::Finish](itnef-finish.md)方法后会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="8452b-126">No actual TNEF encoding for **SetProps** happens until after the [ITnef::Finish](itnef-finish.md) method is called.</span></span> <span data-ttu-id="8452b-127">此功能的含义，**完成**呼叫后，指针传递给**SetProps**必须保持才有效。</span><span class="sxs-lookup"><span data-stu-id="8452b-127">This functionality means that pointers passed into **SetProps** must remain valid until after the call to **Finish** is made.</span></span> <span data-ttu-id="8452b-128">此时，所有对象和数据传递到**SetProps**呼叫可以发布或释放。</span><span class="sxs-lookup"><span data-stu-id="8452b-128">At that point, all objects and data passed into **SetProps** calls can be released or freed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8452b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8452b-129">See also</span></span>



[<span data-ttu-id="8452b-130">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="8452b-130">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="8452b-131">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="8452b-131">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="8452b-132">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="8452b-132">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="8452b-133">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="8452b-133">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)
  
[<span data-ttu-id="8452b-134">SPropValue</span><span class="sxs-lookup"><span data-stu-id="8452b-134">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="8452b-135">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8452b-135">ITnef : IUnknown</span></span>](itnefiunknown.md)

