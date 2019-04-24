---
title: OpenTnefStreamEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenTnefStreamEx
api_type:
- COM
ms.assetid: eb84c408-2d8b-453b-92f4-5fd8851b84ca
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 178ab67875d8fb442500dd412dbafe4403deee16
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348571"
---
# <a name="opentnefstreamex"></a><span data-ttu-id="1f2df-103">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="1f2df-103">OpenTnefStreamEx</span></span>

<span data-ttu-id="1f2df-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1f2df-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1f2df-105">创建一个传输中性封装格式 (TNEF) 对象, 该对象可用于将邮件对象编码或解码为 TNEF 数据流, 以供传输或网关和邮件存储使用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-105">Creates a Transport-Neutral Encapsulation Format (TNEF) object that can be used to encode or decode a message object into a TNEF data stream for use by transports or gateways and message stores.</span></span> <span data-ttu-id="1f2df-106">这是 TNEF 访问的入口点。</span><span class="sxs-lookup"><span data-stu-id="1f2df-106">This is the entry point for TNEF access.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1f2df-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1f2df-107">Header file:</span></span>  <br/> |<span data-ttu-id="1f2df-108">Tnef</span><span class="sxs-lookup"><span data-stu-id="1f2df-108">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="1f2df-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="1f2df-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="1f2df-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="1f2df-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="1f2df-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="1f2df-111">Called by:</span></span>  <br/> |<span data-ttu-id="1f2df-112">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="1f2df-112">Transport providers</span></span>  <br/> |
   
```cpp
HRESULT OpenTnefStreamEx(
  LPVOID lpvSupport,
  LPSTREAM lpStream,
  LPSTR lpszStreamName,
  ULONG ulFlags,
  LPMESSAGE lpMessage,
  WORD wKeyVal,
  LPADDRESSBOOK lpAddressBook,
  LPITNEF FAR * lppTNEF
);
```

## <a name="parameters"></a><span data-ttu-id="1f2df-113">参数</span><span class="sxs-lookup"><span data-stu-id="1f2df-113">Parameters</span></span>

<span data-ttu-id="1f2df-114">_lpvSupport_</span><span class="sxs-lookup"><span data-stu-id="1f2df-114">_lpvSupport_</span></span>
  
> <span data-ttu-id="1f2df-115">实时传递一个支持对象或传递为 NULL。</span><span class="sxs-lookup"><span data-stu-id="1f2df-115">[in] Passes a support object, or passes in NULL.</span></span> <span data-ttu-id="1f2df-116">如果为 null, 则_lpAddressBook_参数应为非 NULL。</span><span class="sxs-lookup"><span data-stu-id="1f2df-116">If NULL, the  _lpAddressBook_ parameter should be non-null.</span></span> 
    
<span data-ttu-id="1f2df-117">_lpStream_</span><span class="sxs-lookup"><span data-stu-id="1f2df-117">_lpStream_</span></span>
  
> <span data-ttu-id="1f2df-118">实时指向存储流对象 (如 OLE **IStream**接口) 的指针, 该对象提供 TNEF 流消息的源或目标。</span><span class="sxs-lookup"><span data-stu-id="1f2df-118">[in] Pointer to a storage stream object, such as an OLE **IStream** interface, providing a source or destination for a TNEF stream message.</span></span> 
    
<span data-ttu-id="1f2df-119">_lpszStreamName_</span><span class="sxs-lookup"><span data-stu-id="1f2df-119">_lpszStreamName_</span></span>
  
> <span data-ttu-id="1f2df-120">实时一个指向 TNEF 对象使用的数据流的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="1f2df-120">[in] Pointer to the name of the data stream that the TNEF object uses.</span></span> <span data-ttu-id="1f2df-121">如果调用方在其对**OpenTnefStream**的调用中设置了 TNEF_ENCODE 标志 ( _ulFlags_参数), 则_lpszName_参数必须指定一个非 null 的指针, 该指针指向包含为文件命名有效的任何字符的非 null 字符串。</span><span class="sxs-lookup"><span data-stu-id="1f2df-121">If the caller has set the TNEF_ENCODE flag ( _ulFlags_ parameter) in its call to **OpenTnefStream**, the  _lpszName_ parameter must specify a non-null pointer to a non-null string consisting of any characters considered valid for naming a file.</span></span> <span data-ttu-id="1f2df-122">MAPI 不允许包含字符 "["、"]" 或 ":" 的字符串名称, 即使文件系统允许使用它们。</span><span class="sxs-lookup"><span data-stu-id="1f2df-122">MAPI does not allow string names including the characters "[", "]", or ":", even if the file system permits their use.</span></span> <span data-ttu-id="1f2df-123">为_lpszName_参数传递的字符串的大小不得超过 MAX_PATH 的值, 即包含路径名的字符串的最大长度。</span><span class="sxs-lookup"><span data-stu-id="1f2df-123">The size of the string passed for the  _lpszName_ parameter must not exceed the value of MAX_PATH, the maximum length of a string that contains a path name.</span></span> 
    
<span data-ttu-id="1f2df-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1f2df-124">_ulFlags_</span></span>
  
> <span data-ttu-id="1f2df-125">实时用于指示函数模式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="1f2df-125">[in] Bitmask of flags used to indicate the mode of the function.</span></span> <span data-ttu-id="1f2df-126">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="1f2df-126">The following flags can be set:</span></span>
    
<span data-ttu-id="1f2df-127">TNEF_BEST_DATA</span><span class="sxs-lookup"><span data-stu-id="1f2df-127">TNEF_BEST_DATA</span></span> 
  
> <span data-ttu-id="1f2df-128">所有可能的属性都将映射到其下层属性, 但当由于转换为下层属性而导致数据丢失时, 该属性也会在 encapsulations 中进行编码。</span><span class="sxs-lookup"><span data-stu-id="1f2df-128">All possible properties are mapped into their down-level attributes, but when there is a possible data loss due to the conversion to a down-level attribute, the property is also encoded in the encapsulations.</span></span> <span data-ttu-id="1f2df-129">请注意, 这将导致 TNEF 流中的信息重复。</span><span class="sxs-lookup"><span data-stu-id="1f2df-129">Note that this will cause the duplication of information in the TNEF stream.</span></span> <span data-ttu-id="1f2df-130">如果未指定其他模式, 则 TNEF_BEST_DATA 为默认值。</span><span class="sxs-lookup"><span data-stu-id="1f2df-130">TNEF_BEST_DATA is the default if no other modes are specified.</span></span> 
    
<span data-ttu-id="1f2df-131">TNEF_COMPATIBILITY</span><span class="sxs-lookup"><span data-stu-id="1f2df-131">TNEF_COMPATIBILITY</span></span> 
  
> <span data-ttu-id="1f2df-132">提供与旧客户端应用程序的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="1f2df-132">Provides backward compatibility with older client applications.</span></span> <span data-ttu-id="1f2df-133">使用此标志编码的 TNEF 流会将所有可能的属性映射到其相应的低级别属性。</span><span class="sxs-lookup"><span data-stu-id="1f2df-133">TNEF streams encoded with this flag will map all possible properties into their corresponding down-level attribute.</span></span> <span data-ttu-id="1f2df-134">此模式还会导致低级别客户端所需的某些属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="1f2df-134">This mode also causes the defaulting of some properties that are required by down-level clients.</span></span> 
    
  > [!CAUTION]
  > <span data-ttu-id="1f2df-135">此标志已过时, 不应使用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-135">This flag is obsolete and should not be used.</span></span> 
  
<span data-ttu-id="1f2df-136">TNEF_DECODE</span><span class="sxs-lookup"><span data-stu-id="1f2df-136">TNEF_DECODE</span></span> 
  
> <span data-ttu-id="1f2df-137">以只读访问权限打开指定流中的 TNEF 对象。</span><span class="sxs-lookup"><span data-stu-id="1f2df-137">The TNEF object on the indicated stream is opened with read-only access.</span></span> <span data-ttu-id="1f2df-138">如果函数要初始化对象以进行后续解码, 则传输提供程序必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="1f2df-138">The transport provider must set this flag if the function is to initialize the object for subsequent decoding.</span></span>
    
<span data-ttu-id="1f2df-139">TNEF_ENCODE</span><span class="sxs-lookup"><span data-stu-id="1f2df-139">TNEF_ENCODE</span></span> 
  
> <span data-ttu-id="1f2df-140">将打开指定流上的 TNEF 对象以进行读/写权限。</span><span class="sxs-lookup"><span data-stu-id="1f2df-140">The TNEF object on the indicated stream is opened for read/write permission.</span></span> <span data-ttu-id="1f2df-141">如果函数要为后续编码初始化对象, 则传输提供程序必须设置此标志。</span><span class="sxs-lookup"><span data-stu-id="1f2df-141">The transport provider must set this flag if the function is to initialize the object for subsequent encoding.</span></span>
    
<span data-ttu-id="1f2df-142">TNEF_PURE</span><span class="sxs-lookup"><span data-stu-id="1f2df-142">TNEF_PURE</span></span> 
  
> <span data-ttu-id="1f2df-143">将所有属性编码为 MAPI 封装块。</span><span class="sxs-lookup"><span data-stu-id="1f2df-143">Encodes all properties into the MAPI encapsulation blocks.</span></span> <span data-ttu-id="1f2df-144">因此, "纯" TNEF 文件最多包含属性 attMAPIProps、attAttachment、attRenddata 和 attRecipTable。</span><span class="sxs-lookup"><span data-stu-id="1f2df-144">Therefore, a "pure" TNEF file will consist of, at most, the attributes attMAPIProps, attAttachment, attRenddata, and attRecipTable.</span></span> <span data-ttu-id="1f2df-145">此模式非常适合在不需要向后兼容性时使用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-145">This mode is ideal for use when no backward compatibility is required.</span></span>
    
<span data-ttu-id="1f2df-146">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="1f2df-146">_lpMessage_</span></span>
  
> <span data-ttu-id="1f2df-147">实时指向邮件对象的指针, 作为带有附件的已解码邮件的目标或带有附件的已编码邮件的来源。</span><span class="sxs-lookup"><span data-stu-id="1f2df-147">[in] Pointer to a message object as a destination for a decoded message with attachments or a source for an encoded message with attachments.</span></span> <span data-ttu-id="1f2df-148">目标邮件的任何属性都可以由已编码邮件的属性覆盖。</span><span class="sxs-lookup"><span data-stu-id="1f2df-148">Any properties of a destination message can be overwritten by the properties of an encoded message.</span></span>
    
<span data-ttu-id="1f2df-149">_wKeyVal_</span><span class="sxs-lookup"><span data-stu-id="1f2df-149">_wKeyVal_</span></span>
  
> <span data-ttu-id="1f2df-150">实时TNEF 对象用来将附件与邮件文本中插入的文本标记相匹配的搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="1f2df-150">[in] A search key that the TNEF object uses to match attachments to the text tags inserted in the message text.</span></span> <span data-ttu-id="1f2df-151">此值在邮件中应是相对唯一的。</span><span class="sxs-lookup"><span data-stu-id="1f2df-151">This value should be relatively unique across messages.</span></span> 
    
<span data-ttu-id="1f2df-152">_lpAddressBook_</span><span class="sxs-lookup"><span data-stu-id="1f2df-152">_lpAddressBook_</span></span>
  
> <span data-ttu-id="1f2df-153">实时指向用于获取条目标识符寻址信息的通讯簿对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1f2df-153">[in] Pointer to an address book object used to get addressing information for entry identifiers.</span></span> 
    
<span data-ttu-id="1f2df-154">_lppTNEF_</span><span class="sxs-lookup"><span data-stu-id="1f2df-154">_lppTNEF_</span></span>
  
> <span data-ttu-id="1f2df-155">排除指向新 TNEF 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1f2df-155">[out] Pointer to the new TNEF object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1f2df-156">返回值</span><span class="sxs-lookup"><span data-stu-id="1f2df-156">Return value</span></span>

<span data-ttu-id="1f2df-157">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f2df-157">S_OK</span></span> 
  
> <span data-ttu-id="1f2df-158">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="1f2df-158">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1f2df-159">注解</span><span class="sxs-lookup"><span data-stu-id="1f2df-159">Remarks</span></span>

<span data-ttu-id="1f2df-160">**OpenTnefStreamEx**函数是[OpenTnefStream](opentnefstream.md)的建议替换, 即 TNEF access 的原始入口点。</span><span class="sxs-lookup"><span data-stu-id="1f2df-160">The **OpenTnefStreamEx** function is the recommended replacement for [OpenTnefStream](opentnefstream.md), the original entry point for TNEF access.</span></span> 
  
<span data-ttu-id="1f2df-161">**OpenTnefStreamEx**函数创建的 TNEF 对象随后调用 OLE 方法**IUnknown:: AddRef**为 support 对象、stream 对象和 message 对象添加引用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-161">A TNEF object created by the **OpenTnefStreamEx** function later calls the OLE method **IUnknown::AddRef** to add references for the support object, the stream object, and the message object.</span></span> <span data-ttu-id="1f2df-162">传输提供程序可以释放对所有三个对象的引用, 并对 OLE 方法**IUnknown::** 在 TNEF 对象上进行一次调用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-162">The transport provider can release the references for all three objects with a single call to the OLE method **IUnknown::Release** on the TNEF object.</span></span> 
  
<span data-ttu-id="1f2df-163">**OpenTnefStreamEx**为提供程序分配和初始化 tnef 对象, 以便在将 MAPI 邮件编码为 TNEF 流邮件时使用。</span><span class="sxs-lookup"><span data-stu-id="1f2df-163">**OpenTnefStreamEx** allocates and initializes a TNEF object for the provider to use in encoding a MAPI message into a TNEF stream message.</span></span> <span data-ttu-id="1f2df-164">或者, 此函数可以设置对象, 以便提供程序在后续调用[ITnef:: ExtractProps](itnef-extractprops.md)将 TNEF 流邮件解码为 MAPI 邮件时使用该对象。</span><span class="sxs-lookup"><span data-stu-id="1f2df-164">Alternatively, this function can set up the object for the provider to use in subsequent calls to [ITnef::ExtractProps](itnef-extractprops.md) to decode a TNEF stream message into a MAPI message.</span></span> <span data-ttu-id="1f2df-165">若要释放 TNEF 对象并关闭会话, 传输提供程序必须在对象上调用继承的**IUnknown:: Release**方法。</span><span class="sxs-lookup"><span data-stu-id="1f2df-165">To free the TNEF object and close the session, the transport provider must call the inherited **IUnknown::Release** method on the object.</span></span> 
  
<span data-ttu-id="1f2df-166">_wKeyVal_参数的基值不得为零, 并且对于每个**OpenTnefStreamEx**调用不应相同。</span><span class="sxs-lookup"><span data-stu-id="1f2df-166">The base value for the  _wKeyVal_ parameter must not be zero and should not be the same for every call to **OpenTnefStreamEx**.</span></span> <span data-ttu-id="1f2df-167">相反, 请根据来自运行时库随机编号生成器的系统时间使用随机数字。</span><span class="sxs-lookup"><span data-stu-id="1f2df-167">Instead, use random numbers based on the system time from the run-time library's random number generator.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1f2df-168">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="1f2df-168">MFCMAPI reference</span></span>

<span data-ttu-id="1f2df-169">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1f2df-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1f2df-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="1f2df-170">**File**</span></span>|<span data-ttu-id="1f2df-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="1f2df-171">**Function**</span></span>|<span data-ttu-id="1f2df-172">**备注**</span><span class="sxs-lookup"><span data-stu-id="1f2df-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1f2df-173">文件 .cpp</span><span class="sxs-lookup"><span data-stu-id="1f2df-173">File.cpp</span></span>  <br/> |<span data-ttu-id="1f2df-174">LoadFromTNEF</span><span class="sxs-lookup"><span data-stu-id="1f2df-174">LoadFromTNEF</span></span>  <br/> |<span data-ttu-id="1f2df-175">MFCMAPI 使用**OpenTnefStreamEx**方法打开 TNEF 文件上的流, 以便可以提取属性。</span><span class="sxs-lookup"><span data-stu-id="1f2df-175">MFCMAPI uses the **OpenTnefStreamEx** method to open a stream on the TNEF file so properties may be extracted.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1f2df-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f2df-176">See also</span></span>

- [<span data-ttu-id="1f2df-177">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1f2df-177">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
- [<span data-ttu-id="1f2df-178">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="1f2df-178">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
- [<span data-ttu-id="1f2df-179">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1f2df-179">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

