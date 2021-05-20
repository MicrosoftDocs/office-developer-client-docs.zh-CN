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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f7372830624d774fb914ae956e86a9e4476cf487
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430789"
---
# <a name="itnefsetprops"></a><span data-ttu-id="a20ae-103">ITnef::SetProps</span><span class="sxs-lookup"><span data-stu-id="a20ae-103">ITnef::SetProps</span></span>

  
  
<span data-ttu-id="a20ae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a20ae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a20ae-105">在不修改原始邮件或附件的情况下设置封装邮件或附件的一个或多个属性的值。</span><span class="sxs-lookup"><span data-stu-id="a20ae-105">Sets the value of one or more properties for an encapsulated message or attachment without modifying the original message or attachment.</span></span> 
  
```cpp
HRESULT SetProps(
  ULONG ulFlags,
  ULONG ulElemID,
  ULONG cValues,
  LPSPropValue lpProps
);
```

## <a name="parameters"></a><span data-ttu-id="a20ae-106">参数</span><span class="sxs-lookup"><span data-stu-id="a20ae-106">Parameters</span></span>

 <span data-ttu-id="a20ae-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a20ae-107">_ulFlags_</span></span>
  
> <span data-ttu-id="a20ae-108">[in]控制属性值设置方式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="a20ae-108">[in] A bitmask of flags that controls how property values are set.</span></span> <span data-ttu-id="a20ae-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a20ae-109">The following flag can be set:</span></span>
    
<span data-ttu-id="a20ae-110">TNEF_PROP_CONTAINED</span><span class="sxs-lookup"><span data-stu-id="a20ae-110">TNEF_PROP_CONTAINED</span></span> 
  
> <span data-ttu-id="a20ae-111">仅对  _ulElemID_ 参数指定的邮件或附件中的属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="a20ae-111">Encodes only properties from the message or attachment specified by the  _ulElemID_ parameter.</span></span> 
    
 <span data-ttu-id="a20ae-112">_ulElemID_</span><span class="sxs-lookup"><span data-stu-id="a20ae-112">_ulElemID_</span></span>
  
> <span data-ttu-id="a20ae-113">[in]附件 **的附件** PR_ATTACH_NUM ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个唯一标识其父邮件中的附件的编号。</span><span class="sxs-lookup"><span data-stu-id="a20ae-113">[in] An attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property, which contains a number that uniquely identifies the attachment in its parent message.</span></span>
    
 <span data-ttu-id="a20ae-114">_cValues_</span><span class="sxs-lookup"><span data-stu-id="a20ae-114">_cValues_</span></span>
  
> <span data-ttu-id="a20ae-115">[in]_lpProps_ 参数指向 [的 SPropValue](spropvalue.md)结构中属性值的数量。</span><span class="sxs-lookup"><span data-stu-id="a20ae-115">[in] The number of property values in the [SPropValue](spropvalue.md) structure pointed to by the  _lpProps_ parameter.</span></span> 
    
 <span data-ttu-id="a20ae-116">_lpProps_</span><span class="sxs-lookup"><span data-stu-id="a20ae-116">_lpProps_</span></span>
  
> <span data-ttu-id="a20ae-117">[in]指向包含要设置的属性的属性值的 **SPropValue** 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="a20ae-117">[in] A pointer to an **SPropValue** structure that contains the property values of the properties to set.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a20ae-118">返回值</span><span class="sxs-lookup"><span data-stu-id="a20ae-118">Return value</span></span>

<span data-ttu-id="a20ae-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a20ae-119">S_OK</span></span> 
  
> <span data-ttu-id="a20ae-120">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="a20ae-120">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a20ae-121">备注</span><span class="sxs-lookup"><span data-stu-id="a20ae-121">Remarks</span></span>

<span data-ttu-id="a20ae-122">传输提供程序、邮件存储提供程序和网关调用 **ITnef：：SetProps** 方法来设置要包括在邮件或附件封装中的属性，而无需修改原始邮件或附件。</span><span class="sxs-lookup"><span data-stu-id="a20ae-122">Transport providers, message store providers, and gateways call the **ITnef::SetProps** method to set properties to include in the encapsulation of a message or an attachment without modifying the original message or attachment.</span></span> <span data-ttu-id="a20ae-123">通过此调用设置的任何属性将覆盖封装邮件中的现有属性。</span><span class="sxs-lookup"><span data-stu-id="a20ae-123">Any properties set with this call override existing properties in the encapsulated message.</span></span> 
  
 <span data-ttu-id="a20ae-124">**SetProps** 仅受使用 [OpenTnefStream 或 OpenTnefStreamEx](opentnefstream.md) TNEF_ENCODE的 TNEF_ENCODE 打开的 [TNEF](opentnefstreamex.md) 对象的支持。</span><span class="sxs-lookup"><span data-stu-id="a20ae-124">**SetProps** is supported only for TNEF objects that are opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> <span data-ttu-id="a20ae-125">此调用可以设置任意数目的属性。</span><span class="sxs-lookup"><span data-stu-id="a20ae-125">Any number of properties can be set with this call.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a20ae-126">在调用 [ITnef：：Finish](itnef-finish.md)方法之前，不会为 **SetProps** 进行实际的 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="a20ae-126">No actual TNEF encoding for **SetProps** happens until after the [ITnef::Finish](itnef-finish.md) method is called.</span></span> <span data-ttu-id="a20ae-127">此功能意味着传递到 **SetProps** 的指针必须一直有效，直到调用 **Finish** 之后。</span><span class="sxs-lookup"><span data-stu-id="a20ae-127">This functionality means that pointers passed into **SetProps** must remain valid until after the call to **Finish** is made.</span></span> <span data-ttu-id="a20ae-128">此时，可以释放或释放传递到 **SetProps** 调用的所有对象和数据。</span><span class="sxs-lookup"><span data-stu-id="a20ae-128">At that point, all objects and data passed into **SetProps** calls can be released or freed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a20ae-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a20ae-129">See also</span></span>



[<span data-ttu-id="a20ae-130">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="a20ae-130">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="a20ae-131">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="a20ae-131">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="a20ae-132">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="a20ae-132">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="a20ae-133">PidTagAttachNumber 规范属性</span><span class="sxs-lookup"><span data-stu-id="a20ae-133">PidTagAttachNumber Canonical Property</span></span>](pidtagattachnumber-canonical-property.md)
  
[<span data-ttu-id="a20ae-134">SPropValue</span><span class="sxs-lookup"><span data-stu-id="a20ae-134">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="a20ae-135">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a20ae-135">ITnef : IUnknown</span></span>](itnefiunknown.md)

