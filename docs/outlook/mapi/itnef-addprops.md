---
title: ITnefAddProps
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.AddProps
api_type:
- COM
ms.assetid: e85641fb-6d3c-494a-981c-01781c7bf5bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6a7bb7265d29d2acfce17a1a09c95f7f7b539064
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396314"
---
# <a name="itnefaddprops"></a><span data-ttu-id="29753-103">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="29753-103">ITnef::AddProps</span></span>

  
  
<span data-ttu-id="29753-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="29753-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="29753-105">允许将属性添加到邮件或附件封装调用服务提供商或网关。</span><span class="sxs-lookup"><span data-stu-id="29753-105">Enables the calling service provider or gateway to add properties to the encapsulation of a message or an attachment.</span></span> 
  
```cpp
HRESULT AddProps(
  ULONG ulFlags,
  ULONG ulElemID,
  LPVOID lpvData,
  LPSPropTagArray lpPropList
);
```

## <a name="parameters"></a><span data-ttu-id="29753-106">参数</span><span class="sxs-lookup"><span data-stu-id="29753-106">Parameters</span></span>

 <span data-ttu-id="29753-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="29753-107">_ulFlags_</span></span>
  
> <span data-ttu-id="29753-108">[in]位掩码的标志，控制如何中包括还是排除在封装属性。</span><span class="sxs-lookup"><span data-stu-id="29753-108">[in] A bitmask of flags that controls how properties are included in or excluded from encapsulation.</span></span> <span data-ttu-id="29753-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="29753-109">The following flags can be set:</span></span>
    
<span data-ttu-id="29753-110">TNEF_PROP_ATTACHMENTS_ONLY</span><span class="sxs-lookup"><span data-stu-id="29753-110">TNEF_PROP_ATTACHMENTS_ONLY</span></span> 
  
> <span data-ttu-id="29753-111">对仅_lpPropList_参数中的属性属于邮件中的附件进行编码。</span><span class="sxs-lookup"><span data-stu-id="29753-111">Encodes only the properties in the  _lpPropList_ parameter that are part of attachments in the message.</span></span> 
    
<span data-ttu-id="29753-112">TNEF_PROP_CONTAINED</span><span class="sxs-lookup"><span data-stu-id="29753-112">TNEF_PROP_CONTAINED</span></span> 
  
> <span data-ttu-id="29753-113">将编码仅从附件_ulElemID_参数指定的属性。</span><span class="sxs-lookup"><span data-stu-id="29753-113">Encodes only properties from the attachment specified by the  _ulElemID_ parameter.</span></span> <span data-ttu-id="29753-114">如果_lpvData_参数不是 NULL，则指向数据写入由**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性指示文件中的附件的封装。</span><span class="sxs-lookup"><span data-stu-id="29753-114">If the  _lpvData_ parameter is not NULL, the data pointed to is written into the attachment's encapsulation in the file indicated by the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="29753-115">TNEF_PROP_CONTAINED_TNEF</span><span class="sxs-lookup"><span data-stu-id="29753-115">TNEF_PROP_CONTAINED_TNEF</span></span> 
  
> <span data-ttu-id="29753-116">将编码仅从邮件或附件_ulElemID_参数指定的属性。</span><span class="sxs-lookup"><span data-stu-id="29753-116">Encodes only properties from the message or attachment specified by the  _ulElemID_ parameter.</span></span> <span data-ttu-id="29753-117">如果设置此标志， _lpvData_中的值必须是[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)指针。</span><span class="sxs-lookup"><span data-stu-id="29753-117">If this flag is set, the value in  _lpvData_ must be an [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) pointer.</span></span> 
    
<span data-ttu-id="29753-118">TNEF_PROP_EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="29753-118">TNEF_PROP_EXCLUDE</span></span> 
  
> <span data-ttu-id="29753-119">将编码不_lpPropList_参数中指定的所有属性。</span><span class="sxs-lookup"><span data-stu-id="29753-119">Encodes all properties not specified in the  _lpPropList_ parameter.</span></span> 
    
<span data-ttu-id="29753-120">TNEF_PROP_INCLUDE</span><span class="sxs-lookup"><span data-stu-id="29753-120">TNEF_PROP_INCLUDE</span></span> 
  
> <span data-ttu-id="29753-121">将编码_lpPropList_中指定的所有属性。</span><span class="sxs-lookup"><span data-stu-id="29753-121">Encodes all properties specified in  _lpPropList_.</span></span> 
    
<span data-ttu-id="29753-122">TNEF_PROP_MESSAGE_ONLY</span><span class="sxs-lookup"><span data-stu-id="29753-122">TNEF_PROP_MESSAGE_ONLY</span></span> 
  
> <span data-ttu-id="29753-123">对仅这些属性中_lpPropList_指定消息本身的一部分进行编码。</span><span class="sxs-lookup"><span data-stu-id="29753-123">Encodes only those properties specified in  _lpPropList_ that are part of the message itself.</span></span> 
    
 <span data-ttu-id="29753-124">_ulElemID_</span><span class="sxs-lookup"><span data-stu-id="29753-124">_ulElemID_</span></span>
  
> <span data-ttu-id="29753-125">[in]附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性，其中包含一个数字唯一地标识其父邮件中的附件。</span><span class="sxs-lookup"><span data-stu-id="29753-125">[in] An attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property, which contains a number that uniquely identifies the attachment in its parent message.</span></span> <span data-ttu-id="29753-126">特殊处理请求的附件时使用_ulElemID_参数。</span><span class="sxs-lookup"><span data-stu-id="29753-126">The  _ulElemID_ parameter is used when special handling is requested for an attachment.</span></span> <span data-ttu-id="29753-127">除非_ulFlags_参数中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 标志， _ulElemID_参数应为 0。</span><span class="sxs-lookup"><span data-stu-id="29753-127">The  _ulElemID_ parameter should be 0 unless the TNEF_PROP_CONTAINED or TNEF_PROP_CONTAINED_TNEF flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="29753-128">_lpvData_</span><span class="sxs-lookup"><span data-stu-id="29753-128">_lpvData_</span></span>
  
> <span data-ttu-id="29753-129">[in]指向用于替换附件_ulElemID_中指定的数据的附件数据的指针。</span><span class="sxs-lookup"><span data-stu-id="29753-129">[in] A pointer to attachment data used to replace the data of the attachment specified in  _ulElemID_.</span></span> <span data-ttu-id="29753-130">除非 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 设置中_ulFlags_， _lpvData_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="29753-130">The  _lpvData_ parameter should be NULL unless TNEF_PROP_CONTAINED or TNEF_PROP_CONTAINED_TNEF is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="29753-131">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="29753-131">_lpPropList_</span></span>
  
> <span data-ttu-id="29753-132">[in]指向要在包含或排除封装的属性列表的指针。</span><span class="sxs-lookup"><span data-stu-id="29753-132">[in] A pointer to the list of properties to include in or exclude from encapsulation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="29753-133">返回值</span><span class="sxs-lookup"><span data-stu-id="29753-133">Return value</span></span>

<span data-ttu-id="29753-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="29753-134">S_OK</span></span> 
  
> <span data-ttu-id="29753-135">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="29753-135">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="29753-136">说明</span><span class="sxs-lookup"><span data-stu-id="29753-136">Remarks</span></span>

<span data-ttu-id="29753-137">传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::AddProps**方法列表属性中包含或排除在邮件或附件的传输中性封装格式 (TNEF) 处理。</span><span class="sxs-lookup"><span data-stu-id="29753-137">Transport providers, message store providers, and gateways call the **ITnef::AddProps** method to list properties to be included in or excluded from the Transport-Neutral Encapsulation Format (TNEF) processing of a message or an attachment.</span></span> <span data-ttu-id="29753-138">通过使用后续呼叫，提供程序或网关可以指定的属性添加和编码或排除要编码的列表。</span><span class="sxs-lookup"><span data-stu-id="29753-138">By using successive calls, the provider or gateway can specify a list of properties to add and encode or to exclude from being encoded.</span></span> <span data-ttu-id="29753-139">提供程序和网关还可以使用**AddProps**提供，应注意任何特殊处理附件有关的信息。</span><span class="sxs-lookup"><span data-stu-id="29753-139">Providers and gateways can also use **AddProps** to provide information about any special handling attachments should be given.</span></span> 
  
 <span data-ttu-id="29753-140">**AddProps**仅支持使用 TNEF_ENCODE 标志[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数打开的 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="29753-140">**AddProps** is supported only for TNEF objects that are opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
  
<span data-ttu-id="29753-141">请注意[ITnef::Finish](itnef-finish.md)方法调用之前对**AddProps**时发生的任何实际 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="29753-141">Note that no actual TNEF encoding happens for **AddProps** until the [ITnef::Finish](itnef-finish.md) method is called.</span></span> <span data-ttu-id="29753-142">此功能的含义，**完成**呼叫后，指针传递给**AddProps**必须保持才有效。</span><span class="sxs-lookup"><span data-stu-id="29753-142">This functionality means that pointers passed into **AddProps** must remain valid until after the call to **Finish** is made.</span></span> <span data-ttu-id="29753-143">此时，所有对象和传入**AddProps**呼叫数据可以发布或释放。</span><span class="sxs-lookup"><span data-stu-id="29753-143">At that point, all objects and data passed in with **AddProps** calls can be released or freed.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="29753-144">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="29753-144">MFCMAPI reference</span></span>

<span data-ttu-id="29753-145">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="29753-145">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="29753-146">**文件**</span><span class="sxs-lookup"><span data-stu-id="29753-146">**File**</span></span>|<span data-ttu-id="29753-147">**函数**</span><span class="sxs-lookup"><span data-stu-id="29753-147">**Function**</span></span>|<span data-ttu-id="29753-148">**备注**</span><span class="sxs-lookup"><span data-stu-id="29753-148">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29753-149">File.cpp</span><span class="sxs-lookup"><span data-stu-id="29753-149">File.cpp</span></span>  <br/> |<span data-ttu-id="29753-150">SaveToTNEF</span><span class="sxs-lookup"><span data-stu-id="29753-150">SaveToTNEF</span></span>  <br/> |<span data-ttu-id="29753-151">MFCMAPI 使用**ITnef::AddProps**方法将属性从邮件复制到 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="29753-151">MFCMAPI uses the **ITnef::AddProps** method to copy properties from a message to a TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="29753-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29753-152">See also</span></span>



[<span data-ttu-id="29753-153">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="29753-153">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="29753-154">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="29753-154">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="29753-155">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="29753-155">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="29753-156">PidTagAttachTransportName 规范属性</span><span class="sxs-lookup"><span data-stu-id="29753-156">PidTagAttachTransportName Canonical Property</span></span>](pidtagattachtransportname-canonical-property.md)
  
[<span data-ttu-id="29753-157">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="29753-157">ITnef : IUnknown</span></span>](itnefiunknown.md)


[<span data-ttu-id="29753-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="29753-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

