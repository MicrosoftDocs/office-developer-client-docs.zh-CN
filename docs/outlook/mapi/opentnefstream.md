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
ms.openlocfilehash: c5abd3a80a9736a4d71525805e4bc38289975c34
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577805"
---
# <a name="opentnefstream"></a><span data-ttu-id="476e9-103">OpenTnefStream</span><span class="sxs-lookup"><span data-stu-id="476e9-103">OpenTnefStream</span></span>

<span data-ttu-id="476e9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="476e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="476e9-105">由传输提供程序启动 MAPI 传输中性封装格式 (TNEF) 会话调用。</span><span class="sxs-lookup"><span data-stu-id="476e9-105">Called by a transport provider to initiate a MAPI Transport Neutral Encapsulation Format (TNEF) session.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="476e9-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="476e9-106">Header file:</span></span>  <br/> |<span data-ttu-id="476e9-107">Tnef.h</span><span class="sxs-lookup"><span data-stu-id="476e9-107">Tnef.h</span></span>  <br/> |
|<span data-ttu-id="476e9-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="476e9-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="476e9-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="476e9-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="476e9-110">调用：</span><span class="sxs-lookup"><span data-stu-id="476e9-110">Called by:</span></span>  <br/> |<span data-ttu-id="476e9-111">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="476e9-111">Transport providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="476e9-112">参数</span><span class="sxs-lookup"><span data-stu-id="476e9-112">Parameters</span></span>

<span data-ttu-id="476e9-113">_lpvSupport_</span><span class="sxs-lookup"><span data-stu-id="476e9-113">_lpvSupport_</span></span>
  
> <span data-ttu-id="476e9-114">[in]通过一个支持对象，或传入 NULL。</span><span class="sxs-lookup"><span data-stu-id="476e9-114">[in] Passes a support object, or passes in NULL.</span></span> 
    
<span data-ttu-id="476e9-115">_lpStream_</span><span class="sxs-lookup"><span data-stu-id="476e9-115">_lpStream_</span></span>
  
> <span data-ttu-id="476e9-116">[in]指向提供源或目标 TNEF 流消息存储 stream 对象 OLE **IStream**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="476e9-116">[in] Pointer to a storage stream object OLE **IStream** interface providing a source or destination for a TNEF stream message.</span></span> 
    
<span data-ttu-id="476e9-117">_lpszStreamName_</span><span class="sxs-lookup"><span data-stu-id="476e9-117">_lpszStreamName_</span></span>
  
> <span data-ttu-id="476e9-118">[in]指针，指向 TNEF 对象使用的数据流的名称。</span><span class="sxs-lookup"><span data-stu-id="476e9-118">[in] Pointer to the name of the data stream that the TNEF object uses.</span></span> <span data-ttu-id="476e9-119">如果呼叫者具有**OpenTnefStream**其调用设置 TNEF_ENCODE 标志 （ _ulFlags_参数）， _lpszName_参数必须指定一个非空指向视为有效命名文件任何个字符组成的非空字符串。</span><span class="sxs-lookup"><span data-stu-id="476e9-119">If the caller has set the TNEF_ENCODE flag ( _ulFlags_ parameter) in its call to **OpenTnefStream**, the  _lpszName_ parameter must specify a non-null pointer to a non-null string consisting of any characters considered valid for naming a file.</span></span> <span data-ttu-id="476e9-120">MAPI 不允许包括字符的字符串名称"["，"]"，或":"，即使在文件系统允许其使用。</span><span class="sxs-lookup"><span data-stu-id="476e9-120">MAPI does not allow string names including the characters "[", "]", or ":", even if the file system permits their use.</span></span> <span data-ttu-id="476e9-121">为_lpszName_传递的字符串的大小不能超过 MAX_PATH，包含路径名称的字符串的最大长度的值。</span><span class="sxs-lookup"><span data-stu-id="476e9-121">The size of the string passed for  _lpszName_ must not exceed the value of MAX_PATH, the maximum length of a string that contains a path name.</span></span> 
    
<span data-ttu-id="476e9-122">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="476e9-122">_ulFlags_</span></span>
  
> <span data-ttu-id="476e9-123">[in]用于指示该函数的模式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="476e9-123">[in] Bitmask of flags used to indicate the mode of the function.</span></span> <span data-ttu-id="476e9-124">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="476e9-124">The following flags can be set:</span></span>
    
<span data-ttu-id="476e9-125">TNEF_BEST_DATA</span><span class="sxs-lookup"><span data-stu-id="476e9-125">TNEF_BEST_DATA</span></span> 
  
> <span data-ttu-id="476e9-126">所有可能的属性映射到其下层属性，但存在由于转换到低级别属性可能的数据丢失时，请封装还编码的属性。</span><span class="sxs-lookup"><span data-stu-id="476e9-126">All possible properties are mapped into their down-level attributes, but when there is a possible data loss due to the conversion to a down-level attribute, the property is also encoded in the encapsulations.</span></span> <span data-ttu-id="476e9-127">请注意，这将导致 TNEF 用于将 stream 中的重复信息。</span><span class="sxs-lookup"><span data-stu-id="476e9-127">Note that this will cause the duplication of information in the TNEF stream.</span></span> <span data-ttu-id="476e9-128">如果未不指定任何其他模式，则 TNEF_BEST_DATA 是默认值。</span><span class="sxs-lookup"><span data-stu-id="476e9-128">TNEF_BEST_DATA is the default if no other modes are specified.</span></span> 
    
<span data-ttu-id="476e9-129">TNEF_COMPATIBILITY</span><span class="sxs-lookup"><span data-stu-id="476e9-129">TNEF_COMPATIBILITY</span></span> 
  
> <span data-ttu-id="476e9-130">提供向后兼容的旧客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="476e9-130">Provides backward compatibility with the older client applications.</span></span> <span data-ttu-id="476e9-131">TNEF 流编码使用此标志将所有可能的属性映射到其相应的向下级属性。</span><span class="sxs-lookup"><span data-stu-id="476e9-131">TNEF streams encoded with this flag will map all possible properties into their corresponding down-level attribute.</span></span> <span data-ttu-id="476e9-132">此模式也会导致下层客户端所需的某些属性的默认设置。</span><span class="sxs-lookup"><span data-stu-id="476e9-132">This mode also causes the defaulting of some properties that are required by down-level clients.</span></span> 
    
  > [!CAUTION]
  > <span data-ttu-id="476e9-133">此标志已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="476e9-133">This flag is obsolete and should not be used.</span></span> 
  
<span data-ttu-id="476e9-134">TNEF_DECODE</span><span class="sxs-lookup"><span data-stu-id="476e9-134">TNEF_DECODE</span></span> 
  
> <span data-ttu-id="476e9-135">指示流上的 TNEF 对象打开具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="476e9-135">The TNEF object on the indicated stream is opened with read-only access.</span></span> <span data-ttu-id="476e9-136">传输提供程序必须设置此标志，如果想要用于初始化后续解码的对象的函数。</span><span class="sxs-lookup"><span data-stu-id="476e9-136">The transport provider must set this flag if it wants the function to initialize the object for subsequent decoding.</span></span>
    
<span data-ttu-id="476e9-137">TNEF_ENCODE</span><span class="sxs-lookup"><span data-stu-id="476e9-137">TNEF_ENCODE</span></span> 
  
> <span data-ttu-id="476e9-138">指示流上的 TNEF 对象为读/写权限打开。</span><span class="sxs-lookup"><span data-stu-id="476e9-138">The TNEF object on the indicated stream is opened for read/write permission.</span></span> <span data-ttu-id="476e9-139">传输提供程序必须设置此标志，如果想要用于初始化后续编码的对象的函数。</span><span class="sxs-lookup"><span data-stu-id="476e9-139">The transport provider must set this flag if it wants the function to initialize the object for subsequent encoding.</span></span>
    
<span data-ttu-id="476e9-140">TNEF_PURE</span><span class="sxs-lookup"><span data-stu-id="476e9-140">TNEF_PURE</span></span> 
  
> <span data-ttu-id="476e9-141">编码为的 MAPI 封装基块的所有属性。</span><span class="sxs-lookup"><span data-stu-id="476e9-141">Encodes all properties into the MAPI encapsulation blocks.</span></span> <span data-ttu-id="476e9-142">因此，一个"纯"TNEF 文件包含，在大多数，attMAPIProps attAttachment，attRenddata，和 attRecipTable。</span><span class="sxs-lookup"><span data-stu-id="476e9-142">Therefore, a "pure" TNEF file will consist of, at most, attMAPIProps, attAttachment, attRenddata, and attRecipTable.</span></span> <span data-ttu-id="476e9-143">需要无向后兼容性时，此模式非常适合于使用。</span><span class="sxs-lookup"><span data-stu-id="476e9-143">This mode is ideal for use when no backward compatibility is required.</span></span>
    
<span data-ttu-id="476e9-144">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="476e9-144">_lpMessage_</span></span>
  
> <span data-ttu-id="476e9-145">[in]邮件作为附件已解码的消息的目标或带附件的编码邮件的源对象的指针。</span><span class="sxs-lookup"><span data-stu-id="476e9-145">[in] Pointer to a message object as a destination for a decoded message with attachments or a source for an encoded message with attachments.</span></span> <span data-ttu-id="476e9-146">编码的邮件的属性可能会被覆盖目标邮件的任何属性。</span><span class="sxs-lookup"><span data-stu-id="476e9-146">Any properties of a destination message might be overwritten by the properties of an encoded message.</span></span>
    
<span data-ttu-id="476e9-147">_wKey_</span><span class="sxs-lookup"><span data-stu-id="476e9-147">_wKey_</span></span>
  
> <span data-ttu-id="476e9-148">[in]TNEF 对象用于匹配附件消息文本中插入的文本标记搜索键。</span><span class="sxs-lookup"><span data-stu-id="476e9-148">[in] A search key that the TNEF object uses to match attachments to the text tags inserted in the message text.</span></span> <span data-ttu-id="476e9-149">此值应该消息是相对唯一。</span><span class="sxs-lookup"><span data-stu-id="476e9-149">This value should be relatively unique across messages.</span></span>
    
<span data-ttu-id="476e9-150">_lppTNEF_</span><span class="sxs-lookup"><span data-stu-id="476e9-150">_lppTNEF_</span></span>
  
> <span data-ttu-id="476e9-151">[输出]为新的 TNEF 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="476e9-151">[out] Pointer to the new TNEF object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="476e9-152">返回值</span><span class="sxs-lookup"><span data-stu-id="476e9-152">Return value</span></span>

<span data-ttu-id="476e9-153">S_OK</span><span class="sxs-lookup"><span data-stu-id="476e9-153">S_OK</span></span> 
  
> <span data-ttu-id="476e9-154">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="476e9-154">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="476e9-155">注解</span><span class="sxs-lookup"><span data-stu-id="476e9-155">Remarks</span></span>

<span data-ttu-id="476e9-156">更高版本创建**OpenTnefStream**函数的 TNEF 对象调用 OLE 方法**IUnknown::AddRef**添加支持对象、 stream 对象中，和 message 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="476e9-156">A TNEF object created by the **OpenTnefStream** function later calls the OLE method **IUnknown::AddRef** to add references for the support object, the stream object, and the message object.</span></span> <span data-ttu-id="476e9-157">传输提供程序可以发布给 OLE 方法**IUnknown::Release** TNEF 对象上的单个调用进行的所有三个对象的引用。</span><span class="sxs-lookup"><span data-stu-id="476e9-157">The transport provider can release the references for all three objects with a single call to the OLE method **IUnknown::Release** on the TNEF object.</span></span> 
  
<span data-ttu-id="476e9-158">**OpenTnefStream**分配并初始化到 TNEF 流邮件编码的 MAPI 邮件**IMessage**界面中使用的提供程序的 TNEF 对象**ITnef**界面。</span><span class="sxs-lookup"><span data-stu-id="476e9-158">**OpenTnefStream** allocates and initializes a TNEF object **ITnef** interface for the provider to use in encoding a MAPI message **IMessage** interface into a TNEF stream message.</span></span> <span data-ttu-id="476e9-159">此外，该函数可以设置到 MAPI 邮件解码 TNEF 流消息后面对[ITnef::ExtractProps](itnef-extractprops.md)中使用的提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="476e9-159">Alternatively, the function can set up the object for the provider to use in subsequent calls to [ITnef::ExtractProps](itnef-extractprops.md) to decode a TNEF stream message into a MAPI message.</span></span> <span data-ttu-id="476e9-160">若要释放 TNEF 对象和关闭会话，传输提供程序必须在对象上调用继承的**IUnknown::Release**方法。</span><span class="sxs-lookup"><span data-stu-id="476e9-160">To free the TNEF object and close the session, the transport provider must call the inherited **IUnknown::Release** method on the object.</span></span> 
  
<span data-ttu-id="476e9-161">此函数是 TNEF 访问的原始入口点和已由[OpenTnefStreamEx](opentnefstreamex.md)取代但仍为那些已使用 TNEF 使用兼容性。</span><span class="sxs-lookup"><span data-stu-id="476e9-161">This function is the original entry point for TNEF access and has been replaced by [OpenTnefStreamEx](opentnefstreamex.md) but is still used for compatibility for those already using TNEF.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="476e9-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="476e9-162">See also</span></span>

- [<span data-ttu-id="476e9-163">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="476e9-163">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)
- [<span data-ttu-id="476e9-164">IXPProvider::TransportLogon</span><span class="sxs-lookup"><span data-stu-id="476e9-164">IXPProvider::TransportLogon</span></span>](ixpprovider-transportlogon.md)

