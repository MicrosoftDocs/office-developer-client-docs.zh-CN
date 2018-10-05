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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395803"
---
# <a name="imapipropopenproperty"></a><span data-ttu-id="b6b7e-103">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="b6b7e-103">IMAPIProp::OpenProperty</span></span>

<span data-ttu-id="b6b7e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6b7e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6b7e-105">返回可用于访问属性的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-105">Returns a pointer to an interface that can be used to access a property.</span></span>
  
```cpp
HRESULT OpenProperty(
  ULONG ulPropTag,
  LPCIID lpiid,
  ULONG ulInterfaceOptions,
  ULONG ulFlags,
  LPUNKNOWN FAR * lppUnk
);
```

## <a name="parameters"></a><span data-ttu-id="b6b7e-106">参数</span><span class="sxs-lookup"><span data-stu-id="b6b7e-106">Parameters</span></span>

 <span data-ttu-id="b6b7e-107">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="b6b7e-107">_ulPropTag_</span></span>
  
> <span data-ttu-id="b6b7e-108">[in]要访问的属性属性标记。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-108">[in] The property tag for the property to be accessed.</span></span> <span data-ttu-id="b6b7e-109">必须属性标记中包含的标识符和类型。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-109">Both the identifier and the type must be included in the property tag.</span></span>
    
 <span data-ttu-id="b6b7e-110">_lpiid_</span><span class="sxs-lookup"><span data-stu-id="b6b7e-110">_lpiid_</span></span>
  
> <span data-ttu-id="b6b7e-111">[in]指向要用于访问属性的接口的标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-111">[in] A pointer to the identifier for the interface to be used to access the property.</span></span> <span data-ttu-id="b6b7e-112">_Lpiid_参数不为**null**。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-112">The  _lpiid_ parameter must not be **null**.</span></span>
    
 <span data-ttu-id="b6b7e-113">_ulInterfaceOptions_</span><span class="sxs-lookup"><span data-stu-id="b6b7e-113">_ulInterfaceOptions_</span></span>
  
> <span data-ttu-id="b6b7e-114">[in]与_lpiid_参数标识的界面相关的数据。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-114">[in] Data that relates to the interface identified by the  _lpiid_ parameter.</span></span> 
    
 <span data-ttu-id="b6b7e-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b6b7e-115">_ulFlags_</span></span>
  
> <span data-ttu-id="b6b7e-116">[in]控制在对属性的访问的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-116">[in] A bitmask of flags that controls access to the property.</span></span> <span data-ttu-id="b6b7e-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b6b7e-117">The following flags can be set:</span></span>
    
<span data-ttu-id="b6b7e-118">MAPI_CREATE</span><span class="sxs-lookup"><span data-stu-id="b6b7e-118">MAPI_CREATE</span></span> 
  
> <span data-ttu-id="b6b7e-119">如果该属性不存在，应创建它。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-119">If the property does not exist, it should be created.</span></span> <span data-ttu-id="b6b7e-120">如果属性不存在，则应丢弃属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-120">If the property does exist, the current value of the property should be discarded.</span></span> <span data-ttu-id="b6b7e-121">当呼叫者设置 MAPI_CREATE 标志时，它也应设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-121">When a caller sets the MAPI_CREATE flag, it should also set the MAPI_MODIFY flag.</span></span>
    
<span data-ttu-id="b6b7e-122">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="b6b7e-122">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="b6b7e-123">允许**OpenProperty**返回成功，原因可能是之前的对象是对呼叫者完全可用。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-123">Allows **OpenProperty** to return successfully, possibly before the object is fully available to the caller.</span></span> <span data-ttu-id="b6b7e-124">如果对象不可用，则进行后续对象呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-124">If the object is not available, making a subsequent object call can raise an error.</span></span> 
    
<span data-ttu-id="b6b7e-125">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="b6b7e-125">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="b6b7e-126">MAPI_MODIFY 是在这些情况下所必需的：</span><span class="sxs-lookup"><span data-stu-id="b6b7e-126">MAPI_MODIFY is required in these situations:</span></span>
    
  - <span data-ttu-id="b6b7e-127">当打开一个流属性，如**IID_IStream**，对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-127">When opening a stream property, such as **IID_IStream**, to modify it.</span></span>
    
  - <span data-ttu-id="b6b7e-128">当打开嵌入的邮件附件，如[PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md)打开**IID_IMessage**，对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-128">When opening an embedded message attachment, such as [PR_ATTACH_DATA_OBJ](pidtagattachdataobject-canonical-property.md) opened with **IID_IMessage**, to modify it.</span></span>
    
 <span data-ttu-id="b6b7e-129">_lppUnk_</span><span class="sxs-lookup"><span data-stu-id="b6b7e-129">_lppUnk_</span></span>
  
> <span data-ttu-id="b6b7e-130">[输出]指向要用于属性访问所请求的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-130">[out] A pointer to the requested interface to be used for property access.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b6b7e-131">返回值</span><span class="sxs-lookup"><span data-stu-id="b6b7e-131">Return value</span></span>

<span data-ttu-id="b6b7e-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6b7e-132">S_OK</span></span> 
  
> <span data-ttu-id="b6b7e-133">已成功返回请求的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-133">The requested interface pointer was successfully returned.</span></span>
    
<span data-ttu-id="b6b7e-134">MAPI_E_INTERFACE_NOT_SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="b6b7e-134">MAPI_E_INTERFACE_NOT_SUPPORTED</span></span> 
  
> <span data-ttu-id="b6b7e-135">此属性不支持所请求的接口。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-135">The requested interface is not supported for this property.</span></span>
    
<span data-ttu-id="b6b7e-136">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="b6b7e-136">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="b6b7e-137">呼叫者具有权限不足，无法访问的属性。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-137">The caller has insufficient permissions to access the property.</span></span>
    
<span data-ttu-id="b6b7e-138">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="b6b7e-138">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="b6b7e-139">对象不能提供给请求的接口通过此属性的访问。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-139">The object cannot provide access to this property through the requested interface.</span></span>
    
<span data-ttu-id="b6b7e-140">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="b6b7e-140">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="b6b7e-141">请求的属性不存在，MAPI_CREATE _ulFlags_参数中未设置。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-141">The requested property does not exist and MAPI_CREATE was not set in the  _ulFlags_ parameter.</span></span> 
    
<span data-ttu-id="b6b7e-142">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="b6b7e-142">MAPI_E_INVALID_PARAMETER</span></span> 
  
> <span data-ttu-id="b6b7e-143">属性类型标记中的设置为 PT_UNSPECIFIED。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-143">The property type in the tag is set to PT_UNSPECIFIED.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b6b7e-144">说明</span><span class="sxs-lookup"><span data-stu-id="b6b7e-144">Remarks</span></span>

<span data-ttu-id="b6b7e-145">**IMAPIProp::OpenProperty**方法提供了访问通过特定接口属性。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-145">The **IMAPIProp::OpenProperty** method provides access to a property through a particular interface.</span></span> <span data-ttu-id="b6b7e-146">**OpenProperty**是[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::SetProps](imapiprop-setprops.md)方法的替代方法。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-146">**OpenProperty** is an alternative to the [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::SetProps](imapiprop-setprops.md) methods.</span></span> <span data-ttu-id="b6b7e-147">当**GetProps**或**SetProps**失败由于属性是太长或太复杂时，调用**OpenProperty**。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-147">When either **GetProps** or **SetProps** fails because the property is too large or too complex, call **OpenProperty**.</span></span> <span data-ttu-id="b6b7e-148">**OpenProperty**通常用于访问类型 PT_OBJECT 的属性。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-148">**OpenProperty** is typically used to access properties of type PT_OBJECT.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b6b7e-149">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b6b7e-149">Notes to callers</span></span>

<span data-ttu-id="b6b7e-150">若要访问邮件附件，打开具有不同的接口标识符，具体取决于附件的类型的**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-150">To access message attachments, open the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property with a different interface identifier, depending on the type of attachment.</span></span> <span data-ttu-id="b6b7e-151">下表介绍如何为不同类型的附件调用**OpenProperty** :</span><span class="sxs-lookup"><span data-stu-id="b6b7e-151">The following table describes how to call **OpenProperty** for the different types of attachments:</span></span> 
  
|<span data-ttu-id="b6b7e-152">**附件的类型**</span><span class="sxs-lookup"><span data-stu-id="b6b7e-152">**Type of attachment**</span></span>|<span data-ttu-id="b6b7e-153">**要使用的接口标识符**</span><span class="sxs-lookup"><span data-stu-id="b6b7e-153">**Interface identifier to use**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6b7e-154">二进制数</span><span class="sxs-lookup"><span data-stu-id="b6b7e-154">Binary</span></span>  <br/> |<span data-ttu-id="b6b7e-155">IID_IStream</span><span class="sxs-lookup"><span data-stu-id="b6b7e-155">IID_IStream</span></span>  <br/> |
|<span data-ttu-id="b6b7e-156">String</span><span class="sxs-lookup"><span data-stu-id="b6b7e-156">String</span></span>  <br/> |<span data-ttu-id="b6b7e-157">IID_IStream</span><span class="sxs-lookup"><span data-stu-id="b6b7e-157">IID_IStream</span></span>  <br/> |
|<span data-ttu-id="b6b7e-158">Message</span><span class="sxs-lookup"><span data-stu-id="b6b7e-158">Message</span></span>  <br/> |<span data-ttu-id="b6b7e-159">IID_IMessage</span><span class="sxs-lookup"><span data-stu-id="b6b7e-159">IID_IMessage</span></span>  <br/> |
|<span data-ttu-id="b6b7e-160">OLE 2.0</span><span class="sxs-lookup"><span data-stu-id="b6b7e-160">OLE 2.0</span></span>  <br/> |<span data-ttu-id="b6b7e-161">IID_IStreamDocfile</span><span class="sxs-lookup"><span data-stu-id="b6b7e-161">IID_IStreamDocfile</span></span>  <br/> |
   
<span data-ttu-id="b6b7e-162">**IStreamDocfile**是基于 OLE 2.0 复合文件的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口导数。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-162">**IStreamDocfile** is a derivative of the [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface that is based on an OLE 2.0 compound file.</span></span> <span data-ttu-id="b6b7e-163">**IStreamDocfile**是用于访问 OLE 2.0 附件，因为它涉及开销最少的最佳选择。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-163">**IStreamDocfile** is the best choice for accessing OLE 2.0 attachments because it involves the least amount of overhead.</span></span> <span data-ttu-id="b6b7e-164">包含可通过[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)接口的结构化存储中存储的数据的这些属性，可以使用 IID_IStreamDocFile。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-164">You can use IID_IStreamDocFile for those properties that contain data stored in structured storage available through the [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) interface.</span></span> 
  
<span data-ttu-id="b6b7e-165">有关如何使用**OpenProperty**带附件的详细信息，请参阅**PR_ATTACH_DATA_OBJ**属性，然后[打开附件](opening-an-attachment.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-165">For more information about how to use **OpenProperty** with attachments, see the **PR_ATTACH_DATA_OBJ** property and [Opening an Attachment](opening-an-attachment.md).</span></span>
  
<span data-ttu-id="b6b7e-166">不要使用**IStream**指针接收调用其[Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx)或[SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx)方法，除非您使用零位置或大小变量。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-166">Do not use the **IStream** pointer that you receive to call either its [Seek](https://msdn.microsoft.com/library/aa380043%28v=VS.85%29.aspx) or [SetSize](https://msdn.microsoft.com/library/aa380044%28v=VS.85%29.aspx) method unless you use a zero position or size variable.</span></span> <span data-ttu-id="b6b7e-167">此外，不要依赖_plibNewPosition_输出参数从**Seek**调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-167">Also, do not rely on the value of the  _plibNewPosition_ output parameter returned from the **Seek** call.</span></span> 
  
<span data-ttu-id="b6b7e-168">如果您调用**OpenProperty**访问**IStream**接口的属性，请使用该接口仅对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-168">If you call **OpenProperty** to access a property with the **IStream** interface, use only that interface to make changes to it.</span></span> <span data-ttu-id="b6b7e-169">请务尝试使用任何其他更新属性[IMAPIProp: IUnknown](imapipropiunknown.md)方法，如**SetProps**或[IMAPIProp::DeleteProps](imapiprop-deleteprops.md)。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-169">Do not attempt to update the property with any of the other [IMAPIProp : IUnknown](imapipropiunknown.md) methods, such as **SetProps** or [IMAPIProp::DeleteProps](imapiprop-deleteprops.md).</span></span> 
  
<span data-ttu-id="b6b7e-170">不要尝试使用**OpenProperty**多次打开一个属性。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-170">Do not try to open a property with **OpenProperty** more than once.</span></span> <span data-ttu-id="b6b7e-171">结果不确定的因为它们可能会商的变化。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-171">The results are undefined because they can vary from provider to provider.</span></span> 
  
<span data-ttu-id="b6b7e-172">如果您需要修改以打开属性，请设置 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-172">If you need to modify the property to be opened, set the MAPI_MODIFY flag.</span></span> <span data-ttu-id="b6b7e-173">如果您不能确定对象是否支持属性，但是您认为应，设置 MAPI_CREATE 和 MAPI_MODIFY 标志。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-173">If you are not sure whether the object supports the property but you think it should, set the MAPI_CREATE and MAPI_MODIFY flags.</span></span> <span data-ttu-id="b6b7e-174">只要 MAPI_CREATE 设置，还必须设置 MAPI_MODIFY。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-174">Whenever MAPI_CREATE is set, MAPI_MODIFY must also be set.</span></span>
  
<span data-ttu-id="b6b7e-175">您负责改革到一个适合于_lpiid_参数中指定的接口返回_lppUnk_参数中的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-175">You are responsible for recasting the interface pointer returned in the  _lppUnk_ parameter to one that is appropriate for the interface specified in the  _lpiid_ parameter.</span></span> <span data-ttu-id="b6b7e-176">您还必须使用返回的指针完与其调用其[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-176">You must also use the returned pointer to call its [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28v=VS.85%29.aspx) method when you are finished with it.</span></span> 
  
<span data-ttu-id="b6b7e-177">有时_ulFlags_参数中设置标志没有足够可用于指示对所需的属性的访问类型。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-177">Sometimes setting the flags in the  _ulFlags_ parameter is not enough to indicate the type of access to the property that is required.</span></span> <span data-ttu-id="b6b7e-178">您可以将其他数据，如标志，放在_ulInterfaceOptions_参数。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-178">You can put additional data, such as flags, in the  _ulInterfaceOptions_ parameter.</span></span> <span data-ttu-id="b6b7e-179">此数据是相关的接口。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-179">This data is interface dependent.</span></span> <span data-ttu-id="b6b7e-180">一些接口 （如**IStream**) 使用它，而且有些则没有。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-180">Some interfaces (such as **IStream**) use it, and others do not.</span></span> <span data-ttu-id="b6b7e-181">例如，当打开**IStream**与要修改的属性时，除了 MAPI_MODIFY _ulInterfaceOptions_参数中设置 STGM_WRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-181">For example, when you open a property to be modified with **IStream**, set the STGM_WRITE flag in the  _ulInterfaceOptions_ parameter in addition to MAPI_MODIFY.</span></span> <span data-ttu-id="b6b7e-182">通过使用[IMAPITable](imapitableiunknown.md)界面打开一个表，可以将_ulInterfaceOptions_设为 MAPI_UNICODE 以指示是否保留字符串属性表中的列应为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-182">When you open a table by using the [IMAPITable](imapitableiunknown.md) interface, you can set  _ulInterfaceOptions_ to MAPI_UNICODE to indicate whether the columns in the table that hold string properties should be in Unicode format.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b6b7e-183">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b6b7e-183">MFCMAPI reference</span></span>

<span data-ttu-id="b6b7e-184">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-184">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b6b7e-185">**文件**</span><span class="sxs-lookup"><span data-stu-id="b6b7e-185">**File**</span></span>|<span data-ttu-id="b6b7e-186">**函数**</span><span class="sxs-lookup"><span data-stu-id="b6b7e-186">**Function**</span></span>|<span data-ttu-id="b6b7e-187">**备注**</span><span class="sxs-lookup"><span data-stu-id="b6b7e-187">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b6b7e-188">StreamEditor.cpp</span><span class="sxs-lookup"><span data-stu-id="b6b7e-188">StreamEditor.cpp</span></span>  <br/> |<span data-ttu-id="b6b7e-189">CStreamEditor::ReadTextStreamFromProperty</span><span class="sxs-lookup"><span data-stu-id="b6b7e-189">CStreamEditor::ReadTextStreamFromProperty</span></span>  <br/> |<span data-ttu-id="b6b7e-190">MFCMAPI 使用**IMAPIProp::OpenProperty**方法检索到大型文本和二进制属性流接口。</span><span class="sxs-lookup"><span data-stu-id="b6b7e-190">MFCMAPI uses the **IMAPIProp::OpenProperty** method to retrieve a stream interface for large text and binary properties.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b6b7e-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6b7e-191">See also</span></span>

- [<span data-ttu-id="b6b7e-192">HrIStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="b6b7e-192">HrIStorageFromStream</span></span>](hristoragefromstream.md) 
- [<span data-ttu-id="b6b7e-193">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="b6b7e-193">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md) 
- [<span data-ttu-id="b6b7e-194">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="b6b7e-194">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
- [<span data-ttu-id="b6b7e-195">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="b6b7e-195">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
- [<span data-ttu-id="b6b7e-196">IMAPISupport::IStorageFromStream</span><span class="sxs-lookup"><span data-stu-id="b6b7e-196">IMAPISupport::IStorageFromStream</span></span>](imapisupport-istoragefromstream.md)
- [<span data-ttu-id="b6b7e-197">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6b7e-197">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
- [<span data-ttu-id="b6b7e-198">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b6b7e-198">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md)
- [<span data-ttu-id="b6b7e-199">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b6b7e-199">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
- [<span data-ttu-id="b6b7e-200">打开附件</span><span class="sxs-lookup"><span data-stu-id="b6b7e-200">Opening an Attachment</span></span>](opening-an-attachment.md)

