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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 52fd844954f41d5d09b5e78f7c23ff6f7469bb43
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776573"
---
# <a name="opentnefstreamex"></a><span data-ttu-id="ba02d-103">OpenTnefStreamEx</span><span class="sxs-lookup"><span data-stu-id="ba02d-103">OpenTnefStreamEx</span></span>

<span data-ttu-id="ba02d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ba02d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ba02d-105">创建可用于编码或到使用 TNEF 数据流解码 message 对象由传输或网关和消息存储传输中性封装格式 (TNEF) 对象。</span><span class="sxs-lookup"><span data-stu-id="ba02d-105">Creates a Transport-Neutral Encapsulation Format (TNEF) object that can be used to encode or decode a message object into a TNEF data stream for use by transports or gateways and message stores.</span></span> <span data-ttu-id="ba02d-106">这是 TNEF 访问的入口点。</span><span class="sxs-lookup"><span data-stu-id="ba02d-106">This is the entry point for TNEF access.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ba02d-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="ba02d-107">Header file:</span></span>  <br/> |<span data-ttu-id="ba02d-108">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="ba02d-108">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="ba02d-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ba02d-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="ba02d-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="ba02d-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="ba02d-111">调用：</span><span class="sxs-lookup"><span data-stu-id="ba02d-111">Called by:</span></span>  <br/> |<span data-ttu-id="ba02d-112">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="ba02d-112">Transport providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="ba02d-113">参数</span><span class="sxs-lookup"><span data-stu-id="ba02d-113">Parameters</span></span>

<span data-ttu-id="ba02d-114">_lpvSupport_</span><span class="sxs-lookup"><span data-stu-id="ba02d-114">_lpvSupport_</span></span>
  
> <span data-ttu-id="ba02d-115">[in]通过一个支持对象，或传入 NULL。</span><span class="sxs-lookup"><span data-stu-id="ba02d-115">[in] Passes a support object, or passes in NULL.</span></span> <span data-ttu-id="ba02d-116">如果为空，则_lpAddressBook_参数应为非空。</span><span class="sxs-lookup"><span data-stu-id="ba02d-116">If NULL, the  _lpAddressBook_ parameter should be non-null.</span></span> 
    
<span data-ttu-id="ba02d-117">_lpStream_</span><span class="sxs-lookup"><span data-stu-id="ba02d-117">_lpStream_</span></span>
  
> <span data-ttu-id="ba02d-118">[in]指向存储 stream 对象，如提供源或目标 TNEF 流邮件 OLE **IStream**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ba02d-118">[in] Pointer to a storage stream object, such as an OLE **IStream** interface, providing a source or destination for a TNEF stream message.</span></span> 
    
<span data-ttu-id="ba02d-119">_lpszStreamName_</span><span class="sxs-lookup"><span data-stu-id="ba02d-119">_lpszStreamName_</span></span>
  
> <span data-ttu-id="ba02d-120">[in]指针，指向 TNEF 对象使用的数据流的名称。</span><span class="sxs-lookup"><span data-stu-id="ba02d-120">[in] Pointer to the name of the data stream that the TNEF object uses.</span></span> <span data-ttu-id="ba02d-121">如果呼叫者具有**OpenTnefStream**其调用设置 TNEF_ENCODE 标志 （ _ulFlags_参数）， _lpszName_参数必须指定一个非空指向视为有效命名文件任何个字符组成的非空字符串。</span><span class="sxs-lookup"><span data-stu-id="ba02d-121">If the caller has set the TNEF_ENCODE flag ( _ulFlags_ parameter) in its call to **OpenTnefStream**, the  _lpszName_ parameter must specify a non-null pointer to a non-null string consisting of any characters considered valid for naming a file.</span></span> <span data-ttu-id="ba02d-122">MAPI 不允许包括字符的字符串名称"["，"]"，或":"，即使在文件系统允许其使用。</span><span class="sxs-lookup"><span data-stu-id="ba02d-122">MAPI does not allow string names including the characters "[", "]", or ":", even if the file system permits their use.</span></span> <span data-ttu-id="ba02d-123">为_lpszName_参数传递的字符串的大小不能超过 MAX_PATH，包含路径名称的字符串的最大长度的值。</span><span class="sxs-lookup"><span data-stu-id="ba02d-123">The size of the string passed for the  _lpszName_ parameter must not exceed the value of MAX_PATH, the maximum length of a string that contains a path name.</span></span> 
    
<span data-ttu-id="ba02d-124">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ba02d-124">_ulFlags_</span></span>
  
> <span data-ttu-id="ba02d-125">[in]用于指示该函数的模式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="ba02d-125">[in] Bitmask of flags used to indicate the mode of the function.</span></span> <span data-ttu-id="ba02d-126">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="ba02d-126">The following flags can be set:</span></span>
    
<span data-ttu-id="ba02d-127">TNEF_BEST_DATA</span><span class="sxs-lookup"><span data-stu-id="ba02d-127">TNEF_BEST_DATA</span></span> 
  
> <span data-ttu-id="ba02d-128">所有可能的属性映射到其下层属性，但存在由于转换到低级别属性可能的数据丢失时，请封装还编码的属性。</span><span class="sxs-lookup"><span data-stu-id="ba02d-128">All possible properties are mapped into their down-level attributes, but when there is a possible data loss due to the conversion to a down-level attribute, the property is also encoded in the encapsulations.</span></span> <span data-ttu-id="ba02d-129">请注意，这将导致 TNEF 用于将 stream 中的重复信息。</span><span class="sxs-lookup"><span data-stu-id="ba02d-129">Note that this will cause the duplication of information in the TNEF stream.</span></span> <span data-ttu-id="ba02d-130">如果未不指定任何其他模式，则 TNEF_BEST_DATA 是默认值。</span><span class="sxs-lookup"><span data-stu-id="ba02d-130">TNEF_BEST_DATA is the default if no other modes are specified.</span></span> 
    
<span data-ttu-id="ba02d-131">TNEF_COMPATIBILITY</span><span class="sxs-lookup"><span data-stu-id="ba02d-131">TNEF_COMPATIBILITY</span></span> 
  
> <span data-ttu-id="ba02d-132">提供向后兼容的旧客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba02d-132">Provides backward compatibility with older client applications.</span></span> <span data-ttu-id="ba02d-133">TNEF 流编码使用此标志将所有可能的属性映射到其相应的向下级属性。</span><span class="sxs-lookup"><span data-stu-id="ba02d-133">TNEF streams encoded with this flag will map all possible properties into their corresponding down-level attribute.</span></span> <span data-ttu-id="ba02d-134">此模式也会导致下层客户端所需的某些属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="ba02d-134">This mode also causes the defaulting of some properties that are required by down-level clients.</span></span> 
    
  > [!CAUTION]
  > <span data-ttu-id="ba02d-135">此标志已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="ba02d-135">This flag is obsolete and should not be used.</span></span> 
  
<span data-ttu-id="ba02d-136">TNEF_DECODE</span><span class="sxs-lookup"><span data-stu-id="ba02d-136">TNEF_DECODE</span></span> 
  
> <span data-ttu-id="ba02d-137">指示流上的 TNEF 对象打开具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="ba02d-137">The TNEF object on the indicated stream is opened with read-only access.</span></span> <span data-ttu-id="ba02d-138">传输提供程序必须设置此标志，如果函数初始化后续解码的对象。</span><span class="sxs-lookup"><span data-stu-id="ba02d-138">The transport provider must set this flag if the function is to initialize the object for subsequent decoding.</span></span>
    
<span data-ttu-id="ba02d-139">TNEF_ENCODE</span><span class="sxs-lookup"><span data-stu-id="ba02d-139">TNEF_ENCODE</span></span> 
  
> <span data-ttu-id="ba02d-140">指示流上的 TNEF 对象为读/写权限打开。</span><span class="sxs-lookup"><span data-stu-id="ba02d-140">The TNEF object on the indicated stream is opened for read/write permission.</span></span> <span data-ttu-id="ba02d-141">传输提供程序必须设置此标志，如果函数初始化后续编码的对象。</span><span class="sxs-lookup"><span data-stu-id="ba02d-141">The transport provider must set this flag if the function is to initialize the object for subsequent encoding.</span></span>
    
<span data-ttu-id="ba02d-142">TNEF_PURE</span><span class="sxs-lookup"><span data-stu-id="ba02d-142">TNEF_PURE</span></span> 
  
> <span data-ttu-id="ba02d-143">编码为的 MAPI 封装基块的所有属性。</span><span class="sxs-lookup"><span data-stu-id="ba02d-143">Encodes all properties into the MAPI encapsulation blocks.</span></span> <span data-ttu-id="ba02d-144">因此，一个"纯"TNEF 文件组成，最属性 attMAPIProps、 attAttachment、 attRenddata 和 attRecipTable。</span><span class="sxs-lookup"><span data-stu-id="ba02d-144">Therefore, a "pure" TNEF file will consist of, at most, the attributes attMAPIProps, attAttachment, attRenddata, and attRecipTable.</span></span> <span data-ttu-id="ba02d-145">需要无向后兼容性时，此模式非常适合于使用。</span><span class="sxs-lookup"><span data-stu-id="ba02d-145">This mode is ideal for use when no backward compatibility is required.</span></span>
    
<span data-ttu-id="ba02d-146">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="ba02d-146">_lpMessage_</span></span>
  
> <span data-ttu-id="ba02d-147">[in]邮件作为附件已解码的消息的目标或带附件的编码邮件的源对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ba02d-147">[in] Pointer to a message object as a destination for a decoded message with attachments or a source for an encoded message with attachments.</span></span> <span data-ttu-id="ba02d-148">编码的邮件的属性时可以覆盖目标邮件的任何属性。</span><span class="sxs-lookup"><span data-stu-id="ba02d-148">Any properties of a destination message can be overwritten by the properties of an encoded message.</span></span>
    
<span data-ttu-id="ba02d-149">_wKeyVal_</span><span class="sxs-lookup"><span data-stu-id="ba02d-149">_wKeyVal_</span></span>
  
> <span data-ttu-id="ba02d-150">[in]TNEF 对象用于匹配附件消息文本中插入的文本标记搜索键。</span><span class="sxs-lookup"><span data-stu-id="ba02d-150">[in] A search key that the TNEF object uses to match attachments to the text tags inserted in the message text.</span></span> <span data-ttu-id="ba02d-151">此值应该消息是相对唯一。</span><span class="sxs-lookup"><span data-stu-id="ba02d-151">This value should be relatively unique across messages.</span></span> 
    
<span data-ttu-id="ba02d-152">_lpAddressBook_</span><span class="sxs-lookup"><span data-stu-id="ba02d-152">_lpAddressBook_</span></span>
  
> <span data-ttu-id="ba02d-153">[in]指向用于获取寻址信息项标识符的通讯簿对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ba02d-153">[in] Pointer to an address book object used to get addressing information for entry identifiers.</span></span> 
    
<span data-ttu-id="ba02d-154">_lppTNEF_</span><span class="sxs-lookup"><span data-stu-id="ba02d-154">_lppTNEF_</span></span>
  
> <span data-ttu-id="ba02d-155">[输出]为新的 TNEF 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="ba02d-155">[out] Pointer to the new TNEF object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ba02d-156">返回值</span><span class="sxs-lookup"><span data-stu-id="ba02d-156">Return value</span></span>

<span data-ttu-id="ba02d-157">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba02d-157">S_OK</span></span> 
  
> <span data-ttu-id="ba02d-158">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="ba02d-158">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ba02d-159">备注</span><span class="sxs-lookup"><span data-stu-id="ba02d-159">Remarks</span></span>

<span data-ttu-id="ba02d-160">**OpenTnefStreamEx**函数是[OpenTnefStream](opentnefstream.md)，TNEF 访问的原始入口点的建议的替代。</span><span class="sxs-lookup"><span data-stu-id="ba02d-160">The **OpenTnefStreamEx** function is the recommended replacement for [OpenTnefStream](opentnefstream.md), the original entry point for TNEF access.</span></span> 
  
<span data-ttu-id="ba02d-161">更高版本创建**OpenTnefStreamEx**函数的 TNEF 对象调用 OLE 方法**IUnknown::AddRef**添加支持对象、 stream 对象中，和 message 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="ba02d-161">A TNEF object created by the **OpenTnefStreamEx** function later calls the OLE method **IUnknown::AddRef** to add references for the support object, the stream object, and the message object.</span></span> <span data-ttu-id="ba02d-162">传输提供程序可以发布给 OLE 方法**IUnknown::Release** TNEF 对象上的单个调用进行的所有三个对象的引用。</span><span class="sxs-lookup"><span data-stu-id="ba02d-162">The transport provider can release the references for all three objects with a single call to the OLE method **IUnknown::Release** on the TNEF object.</span></span> 
  
<span data-ttu-id="ba02d-163">**OpenTnefStreamEx**分配并初始化 TNEF 对象的 MAPI 邮件编码到 TNEF 流邮件中使用的提供程序。</span><span class="sxs-lookup"><span data-stu-id="ba02d-163">**OpenTnefStreamEx** allocates and initializes a TNEF object for the provider to use in encoding a MAPI message into a TNEF stream message.</span></span> <span data-ttu-id="ba02d-164">此外，此函数可以设置到 MAPI 邮件解码 TNEF 流消息后面对[ITnef::ExtractProps](itnef-extractprops.md)中使用的提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="ba02d-164">Alternatively, this function can set up the object for the provider to use in subsequent calls to [ITnef::ExtractProps](itnef-extractprops.md) to decode a TNEF stream message into a MAPI message.</span></span> <span data-ttu-id="ba02d-165">若要释放 TNEF 对象和关闭会话，传输提供程序必须在对象上调用继承的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="ba02d-165">To free the TNEF object and close the session, the transport provider must call the inherited **IUnknown::Release** method on the object.</span></span> 
  
<span data-ttu-id="ba02d-166">_WKeyVal_参数的基本值不能为零，不应**OpenTnefStreamEx**每次调用相同。</span><span class="sxs-lookup"><span data-stu-id="ba02d-166">The base value for the  _wKeyVal_ parameter must not be zero and should not be the same for every call to **OpenTnefStreamEx**.</span></span> <span data-ttu-id="ba02d-167">而是使用随机数基于从运行时库的随机数字生成器系统时间。</span><span class="sxs-lookup"><span data-stu-id="ba02d-167">Instead, use random numbers based on the system time from the run-time library's random number generator.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ba02d-168">MFCMAPI 参考</span><span class="sxs-lookup"><span data-stu-id="ba02d-168">MFCMAPI reference</span></span>

<span data-ttu-id="ba02d-169">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ba02d-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ba02d-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="ba02d-170">**File**</span></span>|<span data-ttu-id="ba02d-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="ba02d-171">**Function**</span></span>|<span data-ttu-id="ba02d-172">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ba02d-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ba02d-173">File.cpp</span><span class="sxs-lookup"><span data-stu-id="ba02d-173">File.cpp</span></span>  <br/> |<span data-ttu-id="ba02d-174">LoadFromTNEF</span><span class="sxs-lookup"><span data-stu-id="ba02d-174">LoadFromTNEF</span></span>  <br/> |<span data-ttu-id="ba02d-175">MFCMAPI 使用**OpenTnefStreamEx**方法打开 TNEF 文件流，因此可能提取属性。</span><span class="sxs-lookup"><span data-stu-id="ba02d-175">MFCMAPI uses the **OpenTnefStreamEx** method to open a stream on the TNEF file so properties may be extracted.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ba02d-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba02d-176">See also</span></span>

- [<span data-ttu-id="ba02d-177">IMAPISupport: IUnknown</span><span class="sxs-lookup"><span data-stu-id="ba02d-177">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
- [<span data-ttu-id="ba02d-178">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="ba02d-178">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)
- [<span data-ttu-id="ba02d-179">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="ba02d-179">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

