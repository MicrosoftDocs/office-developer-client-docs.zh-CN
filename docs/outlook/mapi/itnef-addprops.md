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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348620"
---
# <a name="itnefaddprops"></a><span data-ttu-id="fd13c-103">ITnef::AddProps</span><span class="sxs-lookup"><span data-stu-id="fd13c-103">ITnef::AddProps</span></span>

  
  
<span data-ttu-id="fd13c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fd13c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fd13c-105">启用呼叫服务提供程序或网关以将属性添加到邮件或附件的封装。</span><span class="sxs-lookup"><span data-stu-id="fd13c-105">Enables the calling service provider or gateway to add properties to the encapsulation of a message or an attachment.</span></span> 
  
```cpp
HRESULT AddProps(
  ULONG ulFlags,
  ULONG ulElemID,
  LPVOID lpvData,
  LPSPropTagArray lpPropList
);
```

## <a name="parameters"></a><span data-ttu-id="fd13c-106">参数</span><span class="sxs-lookup"><span data-stu-id="fd13c-106">Parameters</span></span>

 <span data-ttu-id="fd13c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="fd13c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="fd13c-108">实时用于控制如何在封装中包含或排除属性的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-108">[in] A bitmask of flags that controls how properties are included in or excluded from encapsulation.</span></span> <span data-ttu-id="fd13c-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="fd13c-109">The following flags can be set:</span></span>
    
<span data-ttu-id="fd13c-110">TNEF_PROP_ATTACHMENTS_ONLY</span><span class="sxs-lookup"><span data-stu-id="fd13c-110">TNEF_PROP_ATTACHMENTS_ONLY</span></span> 
  
> <span data-ttu-id="fd13c-111">仅对_lpPropList_参数中作为邮件附件的一部分的属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-111">Encodes only the properties in the  _lpPropList_ parameter that are part of attachments in the message.</span></span> 
    
<span data-ttu-id="fd13c-112">TNEF_PROP_CONTAINED</span><span class="sxs-lookup"><span data-stu-id="fd13c-112">TNEF_PROP_CONTAINED</span></span> 
  
> <span data-ttu-id="fd13c-113">仅对_ulElemID_参数所指定的附件中的属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-113">Encodes only properties from the attachment specified by the  _ulElemID_ parameter.</span></span> <span data-ttu-id="fd13c-114">如果_lpvData_参数不为 NULL, 则指向的数据将写入到附件在**PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) 属性指示的文件中的封装中。</span><span class="sxs-lookup"><span data-stu-id="fd13c-114">If the  _lpvData_ parameter is not NULL, the data pointed to is written into the attachment's encapsulation in the file indicated by the **PR_ATTACH_TRANSPORT_NAME** ([PidTagAttachTransportName](pidtagattachtransportname-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="fd13c-115">TNEF_PROP_CONTAINED_TNEF</span><span class="sxs-lookup"><span data-stu-id="fd13c-115">TNEF_PROP_CONTAINED_TNEF</span></span> 
  
> <span data-ttu-id="fd13c-116">仅对_ulElemID_参数所指定的邮件或附件中的属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-116">Encodes only properties from the message or attachment specified by the  _ulElemID_ parameter.</span></span> <span data-ttu-id="fd13c-117">如果设置了此标志, 则_lpvData_中的值必须是[IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream)指针。</span><span class="sxs-lookup"><span data-stu-id="fd13c-117">If this flag is set, the value in  _lpvData_ must be an [IStream](https://docs.microsoft.com/windows/desktop/api/objidl/nn-objidl-istream) pointer.</span></span> 
    
<span data-ttu-id="fd13c-118">TNEF_PROP_EXCLUDE</span><span class="sxs-lookup"><span data-stu-id="fd13c-118">TNEF_PROP_EXCLUDE</span></span> 
  
> <span data-ttu-id="fd13c-119">对未在_lpPropList_参数中指定的所有属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-119">Encodes all properties not specified in the  _lpPropList_ parameter.</span></span> 
    
<span data-ttu-id="fd13c-120">TNEF_PROP_INCLUDE</span><span class="sxs-lookup"><span data-stu-id="fd13c-120">TNEF_PROP_INCLUDE</span></span> 
  
> <span data-ttu-id="fd13c-121">对在_lpPropList_中指定的所有属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-121">Encodes all properties specified in  _lpPropList_.</span></span> 
    
<span data-ttu-id="fd13c-122">TNEF_PROP_MESSAGE_ONLY</span><span class="sxs-lookup"><span data-stu-id="fd13c-122">TNEF_PROP_MESSAGE_ONLY</span></span> 
  
> <span data-ttu-id="fd13c-123">仅对在_lpPropList_中指定的那些属于邮件本身的属性进行编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-123">Encodes only those properties specified in  _lpPropList_ that are part of the message itself.</span></span> 
    
 <span data-ttu-id="fd13c-124">_ulElemID_</span><span class="sxs-lookup"><span data-stu-id="fd13c-124">_ulElemID_</span></span>
  
> <span data-ttu-id="fd13c-125">实时附件的**PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) 属性, 其中包含一个在其父邮件中唯一标识附件的编号。</span><span class="sxs-lookup"><span data-stu-id="fd13c-125">[in] An attachment's **PR_ATTACH_NUM** ([PidTagAttachNumber](pidtagattachnumber-canonical-property.md)) property, which contains a number that uniquely identifies the attachment in its parent message.</span></span> <span data-ttu-id="fd13c-126">当请求附件的特殊处理时, 使用_ulElemID_参数。</span><span class="sxs-lookup"><span data-stu-id="fd13c-126">The  _ulElemID_ parameter is used when special handling is requested for an attachment.</span></span> <span data-ttu-id="fd13c-127">除非在_ulFlags_参数中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF 标志, 否则_ulElemID_参数应为0。</span><span class="sxs-lookup"><span data-stu-id="fd13c-127">The  _ulElemID_ parameter should be 0 unless the TNEF_PROP_CONTAINED or TNEF_PROP_CONTAINED_TNEF flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="fd13c-128">_lpvData_</span><span class="sxs-lookup"><span data-stu-id="fd13c-128">_lpvData_</span></span>
  
> <span data-ttu-id="fd13c-129">实时指向用于替换在_ulElemID_中指定的附件数据的附件数据的指针。</span><span class="sxs-lookup"><span data-stu-id="fd13c-129">[in] A pointer to attachment data used to replace the data of the attachment specified in  _ulElemID_.</span></span> <span data-ttu-id="fd13c-130">除非在_ulFlags_中设置了 TNEF_PROP_CONTAINED 或 TNEF_PROP_CONTAINED_TNEF, 否则_lpvData_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fd13c-130">The  _lpvData_ parameter should be NULL unless TNEF_PROP_CONTAINED or TNEF_PROP_CONTAINED_TNEF is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="fd13c-131">_lpPropList_</span><span class="sxs-lookup"><span data-stu-id="fd13c-131">_lpPropList_</span></span>
  
> <span data-ttu-id="fd13c-132">实时指向要包含在封装中或从封装中排除的属性列表的指针。</span><span class="sxs-lookup"><span data-stu-id="fd13c-132">[in] A pointer to the list of properties to include in or exclude from encapsulation.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fd13c-133">返回值</span><span class="sxs-lookup"><span data-stu-id="fd13c-133">Return value</span></span>

<span data-ttu-id="fd13c-134">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd13c-134">S_OK</span></span> 
  
> <span data-ttu-id="fd13c-135">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="fd13c-135">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fd13c-136">注解</span><span class="sxs-lookup"><span data-stu-id="fd13c-136">Remarks</span></span>

<span data-ttu-id="fd13c-137">传输提供程序、邮件存储提供程序和网关调用**ITnef:: AddProps**方法, 以列出要包含或排除在邮件或附件的传输中性封装格式 (TNEF) 处理中的属性。</span><span class="sxs-lookup"><span data-stu-id="fd13c-137">Transport providers, message store providers, and gateways call the **ITnef::AddProps** method to list properties to be included in or excluded from the Transport-Neutral Encapsulation Format (TNEF) processing of a message or an attachment.</span></span> <span data-ttu-id="fd13c-138">通过使用连续调用, 提供程序或网关可以指定要添加和编码或从编码中排除的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="fd13c-138">By using successive calls, the provider or gateway can specify a list of properties to add and encode or to exclude from being encoded.</span></span> <span data-ttu-id="fd13c-139">提供程序和网关也可以使用**AddProps**提供有关应提供的任何特殊处理附件的信息。</span><span class="sxs-lookup"><span data-stu-id="fd13c-139">Providers and gateways can also use **AddProps** to provide information about any special handling attachments should be given.</span></span> 
  
 <span data-ttu-id="fd13c-140">仅在使用[OpenTnefStream](opentnefstream.md)或[OpenTnefStreamEx](opentnefstreamex.md)函数的 TNEF_ENCODE 标志打开的 TNEF 对象中支持**AddProps** 。</span><span class="sxs-lookup"><span data-stu-id="fd13c-140">**AddProps** is supported only for TNEF objects that are opened with the TNEF_ENCODE flag for the [OpenTnefStream](opentnefstream.md) or [OpenTnefStreamEx](opentnefstreamex.md) function.</span></span> 
  
<span data-ttu-id="fd13c-141">请注意, 在调用[ITnef:: Finish](itnef-finish.md)方法之前, 不会对**AddProps**进行实际的 TNEF 编码。</span><span class="sxs-lookup"><span data-stu-id="fd13c-141">Note that no actual TNEF encoding happens for **AddProps** until the [ITnef::Finish](itnef-finish.md) method is called.</span></span> <span data-ttu-id="fd13c-142">此功能意味着传递到**AddProps**的指针必须一直保持有效, 直到对完成的调用**完成**。</span><span class="sxs-lookup"><span data-stu-id="fd13c-142">This functionality means that pointers passed into **AddProps** must remain valid until after the call to **Finish** is made.</span></span> <span data-ttu-id="fd13c-143">在这种情况下, 可以释放或释放使用**AddProps**调用传入的所有对象和数据。</span><span class="sxs-lookup"><span data-stu-id="fd13c-143">At that point, all objects and data passed in with **AddProps** calls can be released or freed.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="fd13c-144">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="fd13c-144">MFCMAPI reference</span></span>

<span data-ttu-id="fd13c-145">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="fd13c-145">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="fd13c-146">**文件**</span><span class="sxs-lookup"><span data-stu-id="fd13c-146">**File**</span></span>|<span data-ttu-id="fd13c-147">**函数**</span><span class="sxs-lookup"><span data-stu-id="fd13c-147">**Function**</span></span>|<span data-ttu-id="fd13c-148">**备注**</span><span class="sxs-lookup"><span data-stu-id="fd13c-148">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fd13c-149">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="fd13c-149">File.cpp</span></span>  <br/> |<span data-ttu-id="fd13c-150">SaveToTNEF</span><span class="sxs-lookup"><span data-stu-id="fd13c-150">SaveToTNEF</span></span>  <br/> |<span data-ttu-id="fd13c-151">MFCMAPI 使用**ITnef:: AddProps**方法将邮件中的属性复制到 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="fd13c-151">MFCMAPI uses the **ITnef::AddProps** method to copy properties from a message to a TNEF stream.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fd13c-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd13c-152">See also</span></span>



[<span data-ttu-id="fd13c-153">ITnef::Finish</span><span class="sxs-lookup"><span data-stu-id="fd13c-153">ITnef::Finish</span></span>](itnef-finish.md)
  
[<span data-ttu-id="fd13c-154">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="fd13c-154">OpenTnefStream</span></span>](opentnefstream.md)
  
[<span data-ttu-id="fd13c-155">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="fd13c-155">OpenTnefStreamEx</span></span>](opentnefstreamex.md)
  
[<span data-ttu-id="fd13c-156">PidTagAttachTransportName 规范属性</span><span class="sxs-lookup"><span data-stu-id="fd13c-156">PidTagAttachTransportName Canonical Property</span></span>](pidtagattachtransportname-canonical-property.md)
  
[<span data-ttu-id="fd13c-157">ITnef : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fd13c-157">ITnef : IUnknown</span></span>](itnefiunknown.md)


[<span data-ttu-id="fd13c-158">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="fd13c-158">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

