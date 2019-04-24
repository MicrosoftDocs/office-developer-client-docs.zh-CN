---
title: IMAPIPropOpenProperty
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp.OpenProperty
api_type:
- COM
ms.assetid: e400e6cc-4e36-43fc-9304-b688a0a7fd77
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7bf1d6912e44319c36e288cd3870218e8c4e45ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319808"
---
# <a name="imapipropopenproperty"></a><span data-ttu-id="ea4e9-103">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="ea4e9-103">IMAPIProp::OpenProperty</span></span>

<span data-ttu-id="ea4e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ea4e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ea4e9-105">返回指向可用于访问属性的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-105">Returns a pointer to an interface that can be used to access a property.</span></span>
  
```cpp
HRESULT OpenProperty(
  ULONG ulPropTag,
  LPCIID lpiid,
  ULONG ulInterfaceOptions,
  ULONG ulFlags,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="ea4e9-106">参数</span><span class="sxs-lookup"><span data-stu-id="ea4e9-106">Parameters</span></span>

 <span data-ttu-id="ea4e9-107">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="ea4e9-107">_ulPropTag_</span></span>
  
> <span data-ttu-id="ea4e9-108">实时要访问的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-108">[in] The property tag for the property to be accessed.</span></span> <span data-ttu-id="ea4e9-109">标识符和类型都必须包含在属性标记中。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-109">Both the identifier and the type must be included in the property tag.</span></span>
    
 <span data-ttu-id="ea4e9-110">_lpiid_</span><span class="sxs-lookup"><span data-stu-id="ea4e9-110">_lpiid_</span></span>
  
> <span data-ttu-id="ea4e9-111">实时指向要用于访问属性的接口的标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-111">[in] A pointer to the identifier for the interface to be used to access the property.</span></span> <span data-ttu-id="ea4e9-112">_lpiid_参数不能为**null**。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-112">The  _lpiid_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="ea4e9-113">_ulInterfaceOptions_</span><span class="sxs-lookup"><span data-stu-id="ea4e9-113">_ulInterfaceOptions_</span></span>
  
> <span data-ttu-id="ea4e9-114">实时与_lpiid_参数标识的接口相关的数据。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-114">[in] Data that relates to the interface identified by the  _lpiid_ parameter.</span></span> 
    
 <span data-ttu-id="ea4e9-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ea4e9-115">_ulFlags_</span></span>
  
> <span data-ttu-id="ea4e9-116">实时控制对属性的访问权限的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-116">[in] A bitmask of flags that controls access to the property.</span></span> <span data-ttu-id="ea4e9-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-117">The following flags can be set:</span></span>
    
<span data-ttu-id="ea4e9-118">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="ea4e9-118">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="ea4e9-119">如果该属性不存在, 则应创建该属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-119">If the property does not exist, it should be created.</span></span> <span data-ttu-id="ea4e9-120">如果属性存在, 则应放弃属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-120">If the property does exist, the current value of the property should be discarded.</span></span> <span data-ttu-id="ea4e9-121">当呼叫者设置 MAPI_CREATE 标志时, 它还应设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-121">When a caller sets the MAPI_CREATE flag, it should also set the MAPI_MODIFY flag.</span></span>
    
<span data-ttu-id="ea4e9-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="ea4e9-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="ea4e9-123">允许**OpenProperty**成功返回, 这可能是在将对象完全提供给调用程序之前。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-123">Allows **OpenProperty** to return successfully, possibly before the object is fully available to the caller.</span></span> <span data-ttu-id="ea4e9-124">如果该对象不可用, 则进行后续的对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-124">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="ea4e9-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="ea4e9-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="ea4e9-126">在以下情况下, MAPI_MODIFY 是必需的:</span><span class="sxs-lookup"><span data-stu-id="ea4e9-126">MAPI_MODIFY is required in these situations:</span></span>
    
  - <span data-ttu-id="ea4e9-127">打开 stream 属性 (如**IID_IStream**) 进行修改时。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-127">When opening a stream property, such as **IID_IStream**, to modify it.</span></span>
    
  - <span data-ttu-id="ea4e9-128">打开嵌入的邮件附件 (如使用**IID_IMessage**打开的[PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md)时), 以对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-128">When opening an embedded message attachment, such as [PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md) opened with **IID_IMessage**, to modify it.</span></span>
    
 <span data-ttu-id="ea4e9-129">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="ea4e9-129">_lppUnk_</span></span>
  
> <span data-ttu-id="ea4e9-130">排除指向要用于属性访问的请求接口的指针。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-130">[out] A pointer to the requested interface to be used for property access.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ea4e9-131">返回值</span><span class="sxs-lookup"><span data-stu-id="ea4e9-131">Return value</span></span>

<span data-ttu-id="ea4e9-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="ea4e9-132">S_OK</span></span> 
  
> <span data-ttu-id="ea4e9-133">已成功返回请求的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-133">The requested interface pointer was successfully returned.</span></span>
    
<span data-ttu-id="ea4e9-134">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="ea4e9-134">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="ea4e9-135">此属性不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-135">The requested interface is not supported for this property.</span></span>
    
<span data-ttu-id="ea4e9-136">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="ea4e9-136">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="ea4e9-137">调用方权限不足, 无法访问属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-137">The caller has insufficient permissions to access the property.</span></span>
    
<span data-ttu-id="ea4e9-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="ea4e9-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="ea4e9-139">对象无法通过请求的接口提供对此属性的访问。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-139">The object cannot provide access to this property through the requested interface.</span></span>
    
<span data-ttu-id="ea4e9-140">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="ea4e9-140">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="ea4e9-141">请求的属性不存在, 并且未在_ulFlags_参数中设置 MAPI_CREATE。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-141">The requested property does not exist and MAPI_CREATE was not set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="ea4e9-142">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="ea4e9-142">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="ea4e9-143">将标记中的属性类型设置为 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-143">The property type in the tag is set to PT_UNSPECIFIED.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ea4e9-144">注解</span><span class="sxs-lookup"><span data-stu-id="ea4e9-144">Remarks</span></span>

<span data-ttu-id="ea4e9-145">**IMAPIProp:: OpenProperty**方法通过特定接口提供对属性的访问。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-145">The **IMAPIProp::OpenProperty** method provides access to a property through a particular interface.</span></span> <span data-ttu-id="ea4e9-146">**OpenProperty**是[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: SetProps](imapiprop-setprops.md)方法的替代方法。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-146">**OpenProperty** is an alternative to the [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::SetProps](imapiprop-setprops.md) methods.</span></span> <span data-ttu-id="ea4e9-147">当**GetProps**或**SetProps**由于属性太大或太复杂而失败时, 请调用**OpenProperty**。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-147">When either **GetProps** or **SetProps** fails because the property is too large or too complex, call **OpenProperty**.</span></span> <span data-ttu-id="ea4e9-148">**OpenProperty**通常用于访问 PT_OBJECT 类型的属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-148">**OpenProperty** is typically used to access properties of type PT_OBJECT.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="ea4e9-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ea4e9-149">Notes to callers</span></span>

<span data-ttu-id="ea4e9-150">若要访问邮件附件, 请使用不同的接口标识符打开**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性, 具体取决于附件的类型。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-150">To access message attachments, open the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property with a different interface identifier, depending on the type of attachment.</span></span> <span data-ttu-id="ea4e9-151">下表介绍了如何为不同类型的附件调用**OpenProperty** :</span><span class="sxs-lookup"><span data-stu-id="ea4e9-151">The following table describes how to call **OpenProperty** for the different types of attachments:</span></span> 
  
|<span data-ttu-id="ea4e9-152">**附件的类型**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-152">**Type of attachment**</span></span>|<span data-ttu-id="ea4e9-153">**要使用的接口标识符**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-153">**Interface identifier to use**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea4e9-154">Binary</span><span class="sxs-lookup"><span data-stu-id="ea4e9-154">Binary</span></span>  <br/> |<span data-ttu-id="ea4e9-155">IID_IStream</span><span class="sxs-lookup"><span data-stu-id="ea4e9-155">IID_IStream</span></span>  <br/> |
|<span data-ttu-id="ea4e9-156">字符串</span><span class="sxs-lookup"><span data-stu-id="ea4e9-156">String</span></span>  <br/> |<span data-ttu-id="ea4e9-157">IID_IStream</span><span class="sxs-lookup"><span data-stu-id="ea4e9-157">IID_IStream</span></span>  <br/> |
|<span data-ttu-id="ea4e9-158">消息</span><span class="sxs-lookup"><span data-stu-id="ea4e9-158">Message</span></span>  <br/> |<span data-ttu-id="ea4e9-159">IID_IMessage</span><span class="sxs-lookup"><span data-stu-id="ea4e9-159">IID_IMessage</span></span>  <br/> |
|<span data-ttu-id="ea4e9-160">OLE 2。0</span><span class="sxs-lookup"><span data-stu-id="ea4e9-160">OLE 2.0</span></span>  <br/> |<span data-ttu-id="ea4e9-161">IID_IStreamDocfile</span><span class="sxs-lookup"><span data-stu-id="ea4e9-161">IID_IStreamDocfile</span></span>  <br/> |
   
<span data-ttu-id="ea4e9-162">**IStreamDocfile**是基于 OLE 2.0 复合文件的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口的导数。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-162">**IStreamDocfile** is a derivative of the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface that is based on an OLE 2.0 compound file.</span></span> <span data-ttu-id="ea4e9-163">**IStreamDocfile**是访问 OLE 2.0 附件的最佳选择, 因为它涉及最少量的开销。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-163">**IStreamDocfile** is the best choice for accessing OLE 2.0 attachments because it involves the least amount of overhead.</span></span> <span data-ttu-id="ea4e9-164">您可以将 IID_IStreamDocFile 用于包含通过[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)接口提供的结构化存储区中存储的数据的那些属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-164">You can use IID_IStreamDocFile for those properties that contain data stored in structured storage available through the [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) interface.</span></span> 
  
<span data-ttu-id="ea4e9-165">有关如何将**OpenProperty**与附件一起使用的详细信息, 请参阅**PR_ATTACH_DATA_OBJ**属性和[打开附件](opening-an-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-165">For more information about how to use **OpenProperty** with attachments, see the **PR_ATTACH_DATA_OBJ** property and [Opening an Attachment](opening-an-attachment.md).</span></span>
  
<span data-ttu-id="ea4e9-166">请勿使用您收到的**IStream**指针调用其[Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx)或[SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx)方法, 除非您使用零位置或大小变量。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-166">Do not use the **IStream** pointer that you receive to call either its [Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx) or [SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx) method unless you use a zero position or size variable.</span></span> <span data-ttu-id="ea4e9-167">此外, 不要依赖于从**Seek**调用返回的_plibNewPosition_输出参数的值。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-167">Also, do not rely on the value of the  _plibNewPosition_ output parameter returned from the **Seek** call.</span></span> 
  
<span data-ttu-id="ea4e9-168">如果调用**OpenProperty**以使用**IStream**接口访问属性, 请仅使用该接口对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-168">If you call **OpenProperty** to access a property with the **IStream** interface, use only that interface to make changes to it.</span></span> <span data-ttu-id="ea4e9-169">请勿尝试使用任何其他[IMAPIProp: IUnknown](imapipropiunknown.md)方法 (如**SetProps**或[IMAPIProp::D eleteprops](imapiprop-deleteprops.md)) 更新属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-169">Do not attempt to update the property with any of the other [IMAPIProp : IUnknown](imapipropiunknown.md) methods, such as **SetProps** or [IMAPIProp::DeleteProps](imapiprop-deleteprops.md).</span></span> 
  
<span data-ttu-id="ea4e9-170">请勿尝试多次打开**OpenProperty**属性。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-170">Do not try to open a property with **OpenProperty** more than once.</span></span> <span data-ttu-id="ea4e9-171">结果是不确定的, 因为它们可能因提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-171">The results are undefined because they can vary from provider to provider.</span></span> 
  
<span data-ttu-id="ea4e9-172">如果需要修改要打开的属性, 请设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-172">If you need to modify the property to be opened, set the MAPI_MODIFY flag.</span></span> <span data-ttu-id="ea4e9-173">如果您不确定对象是否支持该属性, 但您认为它是应的, 请设置 MAPI_CREATE 和 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-173">If you are not sure whether the object supports the property but you think it should, set the MAPI_CREATE and MAPI_MODIFY flags.</span></span> <span data-ttu-id="ea4e9-174">只要设置了 MAPI_CREATE, 也必须设置 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-174">Whenever MAPI_CREATE is set, MAPI_MODIFY must also be set.</span></span>
  
<span data-ttu-id="ea4e9-175">您负责将_lppUnk_参数中返回的接口指针 recasting 为一个适用于_lpiid_参数中指定的接口的接口指针。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-175">You are responsible for recasting the interface pointer returned in the  _lppUnk_ parameter to one that is appropriate for the interface specified in the  _lpiid_ parameter.</span></span> <span data-ttu-id="ea4e9-176">完成后, 还必须使用返回的指针调用其[IUnknown:: Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-176">You must also use the returned pointer to call its [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method when you are finished with it.</span></span> 
  
<span data-ttu-id="ea4e9-177">有时, 在_ulFlags_参数中设置标志不足以指示对所需属性的访问类型。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-177">Sometimes setting the flags in the  _ulFlags_ parameter is not enough to indicate the type of access to the property that is required.</span></span> <span data-ttu-id="ea4e9-178">您可以在_ulInterfaceOptions_参数中放置其他数据 (如 flags)。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-178">You can put additional data, such as flags, in the  _ulInterfaceOptions_ parameter.</span></span> <span data-ttu-id="ea4e9-179">此数据依赖于接口。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-179">This data is interface dependent.</span></span> <span data-ttu-id="ea4e9-180">某些接口 (如**IStream**) 使用它, 而其他接口则不使用。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-180">Some interfaces (such as **IStream**) use it, and others do not.</span></span> <span data-ttu-id="ea4e9-181">例如, 当您打开要使用**IStream**修改的属性时, 除了 MAPI_MODIFY 之外, 还应在_ulInterfaceOptions_参数中设置 STGM_WRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-181">For example, when you open a property to be modified with **IStream**, set the STGM_WRITE flag in the  _ulInterfaceOptions_ parameter in addition to MAPI_MODIFY.</span></span> <span data-ttu-id="ea4e9-182">使用[IMAPITable](imapitableiunknown.md)接口打开表格时, 可以将_ulInterfaceOptions_设置为 MAPI_UNICODE, 以指示是否保留字符串属性的表中的列应采用 UNICODE 格式。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-182">When you open a table by using the [IMAPITable](imapitableiunknown.md) interface, you can set  _ulInterfaceOptions_ to MAPI_UNICODE to indicate whether the columns in the table that hold string properties should be in Unicode format.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ea4e9-183">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ea4e9-183">MFCMAPI reference</span></span>

<span data-ttu-id="ea4e9-184">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-184">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ea4e9-185">**文件**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-185">**File**</span></span>|<span data-ttu-id="ea4e9-186">**函数**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-186">**Function**</span></span>|<span data-ttu-id="ea4e9-187">**备注**</span><span class="sxs-lookup"><span data-stu-id="ea4e9-187">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea4e9-188">StreamEditor</span><span class="sxs-lookup"><span data-stu-id="ea4e9-188">StreamEditor.cpp</span></span>  <br/> |<span data-ttu-id="ea4e9-189">CStreamEditor:: ReadTextStreamFromProperty</span><span class="sxs-lookup"><span data-stu-id="ea4e9-189">CStreamEditor::ReadTextStreamFromProperty</span></span>  <br/> |<span data-ttu-id="ea4e9-190">MFCMAPI 使用**IMAPIProp:: OpenProperty**方法检索大型 text 和 binary 属性的 stream 接口。</span><span class="sxs-lookup"><span data-stu-id="ea4e9-190">MFCMAPI uses the **IMAPIProp::OpenProperty** method to retrieve a stream interface for large text and binary properties.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ea4e9-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea4e9-191">See also</span></span>

- [<span data-ttu-id="ea4e9-192">HrIStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="ea4e9-192">HrIStorageFromStream</span></span>](hristoragefromstream.md) 
- [<span data-ttu-id="ea4e9-193">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="ea4e9-193">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md) 
- [<span data-ttu-id="ea4e9-194">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="ea4e9-194">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
- [<span data-ttu-id="ea4e9-195">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="ea4e9-195">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
- [<span data-ttu-id="ea4e9-196">IMAPISupport::IStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="ea4e9-196">IMAPISupport::IStorageFromStream</span></span>](imapisupport-istoragefromstream.md)
- [<span data-ttu-id="ea4e9-197">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ea4e9-197">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
- [<span data-ttu-id="ea4e9-198">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ea4e9-198">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
- [<span data-ttu-id="ea4e9-199">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ea4e9-199">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
- [<span data-ttu-id="ea4e9-200">打开附件</span><span class="sxs-lookup"><span data-stu-id="ea4e9-200">Opening an Attachment</span></span>](opening-an-attachment.md)

