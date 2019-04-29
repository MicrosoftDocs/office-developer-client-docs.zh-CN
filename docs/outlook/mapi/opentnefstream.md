---
title: OpenTnefStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenTnefStream
api_type:
- COM
ms.assetid: 912d7799-53ce-42a7-9fbd-f9a6a3a56047
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 524b52026010b9a06d5822b48b7c04bbf90a113e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423956"
---
# <a name="opentnefstream"></a><span data-ttu-id="df12c-103">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="df12c-103">OpenTnefStream</span></span>

<span data-ttu-id="df12c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df12c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df12c-105">由传输提供程序调用, 以启动 MAPI 传输中性封装格式 (TNEF) 会话。</span><span class="sxs-lookup"><span data-stu-id="df12c-105">Called by a transport provider to initiate a MAPI Transport Neutral Encapsulation Format (TNEF) session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="df12c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="df12c-106">Header file:</span></span>  <br/> |<span data-ttu-id="df12c-107">Tnef</span><span class="sxs-lookup"><span data-stu-id="df12c-107">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="df12c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="df12c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="df12c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="df12c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="df12c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="df12c-110">Called by:</span></span>  <br/> |<span data-ttu-id="df12c-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="df12c-111">Transport providers</span></span>  <br/> |
   
```cpp
HRESULT OpenTnefStream(
  LPVOID lpvSupport,
  LPSTREAM lpStream,
  LPSTR lpszStreamName, 
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  WORD wKey,
  LPITNEF FAR * lppTNEF
);
```

## <a name="parameters"></a><span data-ttu-id="df12c-112">参数</span><span class="sxs-lookup"><span data-stu-id="df12c-112">Parameters</span></span>

<span data-ttu-id="df12c-113">_lpvSupport_</span><span class="sxs-lookup"><span data-stu-id="df12c-113">_lpvSupport_</span></span>
  
> <span data-ttu-id="df12c-114">实时传递一个支持对象或传递为 NULL。</span><span class="sxs-lookup"><span data-stu-id="df12c-114">[in] Passes a support object, or passes in NULL.</span></span> 
    
<span data-ttu-id="df12c-115">_lpStream_</span><span class="sxs-lookup"><span data-stu-id="df12c-115">_lpStream_</span></span>
  
> <span data-ttu-id="df12c-116">实时指向存储流对象 OLE **IStream**接口的指针, 该接口为 TNEF 流消息提供源或目标。</span><span class="sxs-lookup"><span data-stu-id="df12c-116">[in] Pointer to a storage stream object OLE **IStream** interface providing a source or destination for a TNEF stream message.</span></span> 
    
<span data-ttu-id="df12c-117">_lpszStreamName_</span><span class="sxs-lookup"><span data-stu-id="df12c-117">_lpszStreamName_</span></span>
  
> <span data-ttu-id="df12c-118">实时一个指向 TNEF 对象使用的数据流的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="df12c-118">[in] Pointer to the name of the data stream that the TNEF object uses.</span></span> <span data-ttu-id="df12c-119">如果调用方在其对**OpenTnefStream**的调用中设置了 TNEF_ENCODE 标志 ( _ulFlags_参数), 则_lpszName_参数必须指定一个非 null 的指针, 该指针指向包含为文件命名有效的任何字符的非 null 字符串。</span><span class="sxs-lookup"><span data-stu-id="df12c-119">If the caller has set the TNEF_ENCODE flag ( _ulFlags_ parameter) in its call to **OpenTnefStream**, the  _lpszName_ parameter must specify a non-null pointer to a non-null string consisting of any characters considered valid for naming a file.</span></span> <span data-ttu-id="df12c-120">MAPI 不允许包含字符 "["、"]" 或 ":" 的字符串名称, 即使文件系统允许使用它们。</span><span class="sxs-lookup"><span data-stu-id="df12c-120">MAPI does not allow string names including the characters "[", "]", or ":", even if the file system permits their use.</span></span> <span data-ttu-id="df12c-121">为_lpszName_传递的字符串的大小不得超过 MAX_PATH 的值, 即包含路径名的字符串的最大长度。</span><span class="sxs-lookup"><span data-stu-id="df12c-121">The size of the string passed for  _lpszName_ must not exceed the value of MAX_PATH, the maximum length of a string that contains a path name.</span></span> 
    
<span data-ttu-id="df12c-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="df12c-122">_ulFlags_</span></span>
  
> <span data-ttu-id="df12c-123">实时用于指示函数模式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="df12c-123">[in] Bitmask of flags used to indicate the mode of the function.</span></span> <span data-ttu-id="df12c-124">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="df12c-124">The following flags can be set:</span></span>
    
<span data-ttu-id="df12c-125">TNEF_BEST_DATA</span><span class="sxs-lookup"><span data-stu-id="df12c-125">TNEF_BEST_DATA</span></span> 
  
> <span data-ttu-id="df12c-126">所有可能的属性都将映射到其下层属性, 但当由于转换为下层属性而导致数据丢失时, 该属性也会在 encapsulations 中进行编码。</span><span class="sxs-lookup"><span data-stu-id="df12c-126">All possible properties are mapped into their down-level attributes, but when there is a possible data loss due to the conversion to a down-level attribute, the property is also encoded in the encapsulations.</span></span> <span data-ttu-id="df12c-127">请注意, 这将导致 TNEF 流中的信息重复。</span><span class="sxs-lookup"><span data-stu-id="df12c-127">Note that this will cause the duplication of information in the TNEF stream.</span></span> <span data-ttu-id="df12c-128">如果未指定其他模式, 则 TNEF_BEST_DATA 为默认值。</span><span class="sxs-lookup"><span data-stu-id="df12c-128">TNEF_BEST_DATA is the default if no other modes are specified.</span></span> 
    
<span data-ttu-id="df12c-129">TNEF_COMPATIBILITY</span><span class="sxs-lookup"><span data-stu-id="df12c-129">TNEF_COMPATIBILITY</span></span> 
  
> <span data-ttu-id="df12c-130">提供与旧客户端应用程序的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="df12c-130">Provides backward compatibility with the older client applications.</span></span> <span data-ttu-id="df12c-131">使用此标志编码的 TNEF 流会将所有可能的属性映射到其相应的低级别属性。</span><span class="sxs-lookup"><span data-stu-id="df12c-131">TNEF streams encoded with this flag will map all possible properties into their corresponding down-level attribute.</span></span> <span data-ttu-id="df12c-132">此模式还会导致低级别客户端所需的某些属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="df12c-132">This mode also causes the defaulting of some properties that are required by down-level clients.</span></span> 
    
  > [!CAUTION]
  > <span data-ttu-id="df12c-133">此标志已过时, 不应使用。</span><span class="sxs-lookup"><span data-stu-id="df12c-133">This flag is obsolete and should not be used.</span></span> 
  
<span data-ttu-id="df12c-134">TNEF_DECODE</span><span class="sxs-lookup"><span data-stu-id="df12c-134">TNEF_DECODE</span></span> 
  
> <span data-ttu-id="df12c-135">以只读访问权限打开指定流中的 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="df12c-135">The TNEF object on the indicated stream is opened with read-only access.</span></span> <span data-ttu-id="df12c-136">如果传输提供程序想要函数初始化对象以进行后续解码, 则必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="df12c-136">The transport provider must set this flag if it wants the function to initialize the object for subsequent decoding.</span></span>
    
<span data-ttu-id="df12c-137">TNEF_ENCODE</span><span class="sxs-lookup"><span data-stu-id="df12c-137">TNEF_ENCODE</span></span> 
  
> <span data-ttu-id="df12c-138">将打开指定流上的 TNEF 对象以进行读/写权限。</span><span class="sxs-lookup"><span data-stu-id="df12c-138">The TNEF object on the indicated stream is opened for read/write permission.</span></span> <span data-ttu-id="df12c-139">如果传输提供程序希望函数为后续编码初始化对象, 则必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="df12c-139">The transport provider must set this flag if it wants the function to initialize the object for subsequent encoding.</span></span>
    
<span data-ttu-id="df12c-140">TNEF_PURE</span><span class="sxs-lookup"><span data-stu-id="df12c-140">TNEF_PURE</span></span> 
  
> <span data-ttu-id="df12c-141">将所有属性编码为 MAPI 封装块。</span><span class="sxs-lookup"><span data-stu-id="df12c-141">Encodes all properties into the MAPI encapsulation blocks.</span></span> <span data-ttu-id="df12c-142">因此, "纯" TNEF 文件将由 attMAPIProps、attAttachment、attRenddata 和 attRecipTable 组成。</span><span class="sxs-lookup"><span data-stu-id="df12c-142">Therefore, a "pure" TNEF file will consist of, at most, attMAPIProps, attAttachment, attRenddata, and attRecipTable.</span></span> <span data-ttu-id="df12c-143">此模式非常适合在不需要向后兼容性时使用。</span><span class="sxs-lookup"><span data-stu-id="df12c-143">This mode is ideal for use when no backward compatibility is required.</span></span>
    
<span data-ttu-id="df12c-144">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="df12c-144">_lpMessage_</span></span>
  
> <span data-ttu-id="df12c-145">实时指向邮件对象的指针, 作为带有附件的已解码邮件的目标或带有附件的已编码邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="df12c-145">[in] Pointer to a message object as a destination for a decoded message with attachments or a source for an encoded message with attachments.</span></span> <span data-ttu-id="df12c-146">目标邮件的任何属性可能会被编码邮件的属性覆盖。</span><span class="sxs-lookup"><span data-stu-id="df12c-146">Any properties of a destination message might be overwritten by the properties of an encoded message.</span></span>
    
<span data-ttu-id="df12c-147">_wKey_</span><span class="sxs-lookup"><span data-stu-id="df12c-147">_wKey_</span></span>
  
> <span data-ttu-id="df12c-148">实时TNEF 对象用来将附件与邮件文本中插入的文本标记相匹配的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="df12c-148">[in] A search key that the TNEF object uses to match attachments to the text tags inserted in the message text.</span></span> <span data-ttu-id="df12c-149">此值在邮件中应是相对唯一的。</span><span class="sxs-lookup"><span data-stu-id="df12c-149">This value should be relatively unique across messages.</span></span>
    
<span data-ttu-id="df12c-150">_lppTNEF_</span><span class="sxs-lookup"><span data-stu-id="df12c-150">_lppTNEF_</span></span>
  
> <span data-ttu-id="df12c-151">排除指向新 TNEF 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="df12c-151">[out] Pointer to the new TNEF object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="df12c-152">返回值</span><span class="sxs-lookup"><span data-stu-id="df12c-152">Return value</span></span>

<span data-ttu-id="df12c-153">S_OK</span><span class="sxs-lookup"><span data-stu-id="df12c-153">S_OK</span></span> 
  
> <span data-ttu-id="df12c-154">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="df12c-154">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="df12c-155">说明</span><span class="sxs-lookup"><span data-stu-id="df12c-155">Remarks</span></span>

<span data-ttu-id="df12c-156">**OpenTnefStream**函数创建的 TNEF 对象随后调用 OLE 方法**IUnknown:: AddRef**为 support 对象、stream 对象和 message 对象添加引用。</span><span class="sxs-lookup"><span data-stu-id="df12c-156">A TNEF object created by the **OpenTnefStream** function later calls the OLE method **IUnknown::AddRef** to add references for the support object, the stream object, and the message object.</span></span> <span data-ttu-id="df12c-157">传输提供程序可以释放对所有三个对象的引用, 并对 OLE 方法**IUnknown::** 在 TNEF 对象上进行一次调用。</span><span class="sxs-lookup"><span data-stu-id="df12c-157">The transport provider can release the references for all three objects with a single call to the OLE method **IUnknown::Release** on the TNEF object.</span></span> 
  
<span data-ttu-id="df12c-158">**OpenTnefStream**分配并初始化 tnef 对象**ITnef**接口, 以便提供程序在将 MAPI 邮件**IMessage**接口编码为 TNEF 流邮件时使用。</span><span class="sxs-lookup"><span data-stu-id="df12c-158">**OpenTnefStream** allocates and initializes a TNEF object **ITnef** interface for the provider to use in encoding a MAPI message **IMessage** interface into a TNEF stream message.</span></span> <span data-ttu-id="df12c-159">此外, 函数还可以设置对象, 以便提供程序在后续调用[ITnef:: ExtractProps](itnef-extractprops.md)将 TNEF 流邮件解码为 MAPI 邮件时使用该对象。</span><span class="sxs-lookup"><span data-stu-id="df12c-159">Alternatively, the function can set up the object for the provider to use in subsequent calls to [ITnef::ExtractProps](itnef-extractprops.md) to decode a TNEF stream message into a MAPI message.</span></span> <span data-ttu-id="df12c-160">若要释放 TNEF 对象并关闭会话, 传输提供程序必须在对象上调用继承的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="df12c-160">To free the TNEF object and close the session, the transport provider must call the inherited **IUnknown::Release** method on the object.</span></span> 
  
<span data-ttu-id="df12c-161">此函数是 TNEF 访问的原始入口点, 已由[OpenTnefStreamEx](opentnefstreamex.md)替换, 但仍用于兼容已使用 TNEF 的。</span><span class="sxs-lookup"><span data-stu-id="df12c-161">This function is the original entry point for TNEF access and has been replaced by [OpenTnefStreamEx](opentnefstreamex.md) but is still used for compatibility for those already using TNEF.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="df12c-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df12c-162">See also</span></span>

- [<span data-ttu-id="df12c-163">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="df12c-163">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
- [<span data-ttu-id="df12c-164">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="df12c-164">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)

