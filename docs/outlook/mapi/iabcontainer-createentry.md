---
title: IABContainerCreateEntry
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.CreateEntry
api_type:
- COM
ms.assetid: ea1daf74-d9e3-4304-bf5d-889afeea6ae9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: acf9cee9bf0713b909b0d82fc606b015ac28474e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775223"
---
# <a name="iabcontainercreateentry"></a><span data-ttu-id="e9d99-103">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="e9d99-103">IABContainer::CreateEntry</span></span>

  
  
<span data-ttu-id="e9d99-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e9d99-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e9d99-105">创建一个新项，可以是邮件用户、 通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="e9d99-105">Creates a new entry, which can be a messaging user, a distribution list, or another container.</span></span>
  
```cpp
HRESULT CreateEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulCreateFlags,
  LPMAPIPROP FAR * lppMAPIPropEntry
);
```

## <a name="parameters"></a><span data-ttu-id="e9d99-106">参数</span><span class="sxs-lookup"><span data-stu-id="e9d99-106">Parameters</span></span>

 <span data-ttu-id="e9d99-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="e9d99-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="e9d99-108">[in]中_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="e9d99-108">[in] The count of the bytes in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="e9d99-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="e9d99-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="e9d99-110">[in]指向用于创建特定类型的新条目的模板的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e9d99-110">[in] A pointer to the entry identifier of a template for creating new entries of a particular type.</span></span> 
    
 <span data-ttu-id="e9d99-111">_ulCreateFlags_</span><span class="sxs-lookup"><span data-stu-id="e9d99-111">_ulCreateFlags_</span></span>
  
> <span data-ttu-id="e9d99-112">[in]位掩码的标志控制如何执行项创建的。</span><span class="sxs-lookup"><span data-stu-id="e9d99-112">[in] A bitmask of flags that controls how entry creation is performed.</span></span> <span data-ttu-id="e9d99-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e9d99-113">The following flags can be set:</span></span>
    
<span data-ttu-id="e9d99-114">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="e9d99-114">CREATE_CHECK_DUP_LOOSE</span></span> 
  
> <span data-ttu-id="e9d99-115">应执行的重复项检查松散级别。</span><span class="sxs-lookup"><span data-stu-id="e9d99-115">A loose level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="e9d99-116">提供程序特定的松散重复项检查实现。</span><span class="sxs-lookup"><span data-stu-id="e9d99-116">The implementation of loose duplicate entry checking is provider specific.</span></span> <span data-ttu-id="e9d99-117">例如，提供程序可以定义松散匹配项，如任何具有相同的两个条目的显示名称。</span><span class="sxs-lookup"><span data-stu-id="e9d99-117">For example, a provider can define a loose match as any two entries that have the same display name.</span></span>
    
<span data-ttu-id="e9d99-118">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="e9d99-118">CREATE_CHECK_DUP_STRICT</span></span> 
  
> <span data-ttu-id="e9d99-119">应执行的重复项检查严格级别。</span><span class="sxs-lookup"><span data-stu-id="e9d99-119">A strict level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="e9d99-120">提供程序特定的严格的重复项检查实现。</span><span class="sxs-lookup"><span data-stu-id="e9d99-120">The implementation of strict duplicate entry checking is provider specific.</span></span> <span data-ttu-id="e9d99-121">例如，提供程序可以定义严格匹配项，如任何具有两个相同的两个条目显示名称和消息地址。</span><span class="sxs-lookup"><span data-stu-id="e9d99-121">For example, a provider can define a strict match as any two entries that have both the same display name and messaging address.</span></span>
    
<span data-ttu-id="e9d99-122">CREATE_REPLACE</span><span class="sxs-lookup"><span data-stu-id="e9d99-122">CREATE_REPLACE</span></span> 
  
> <span data-ttu-id="e9d99-123">如果确定两个是重复项，新条目应替换现有。</span><span class="sxs-lookup"><span data-stu-id="e9d99-123">A new entry should replace an existing one if it is determined that the two are duplicates.</span></span>
    
 <span data-ttu-id="e9d99-124">_lppMAPIPropEntry_</span><span class="sxs-lookup"><span data-stu-id="e9d99-124">_lppMAPIPropEntry_</span></span>
  
> <span data-ttu-id="e9d99-125">[输出]为指向新创建的项的指针。</span><span class="sxs-lookup"><span data-stu-id="e9d99-125">[out] A pointer to a pointer to the newly created entry.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e9d99-126">返回值</span><span class="sxs-lookup"><span data-stu-id="e9d99-126">Return value</span></span>

<span data-ttu-id="e9d99-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9d99-127">S_OK</span></span> 
  
> <span data-ttu-id="e9d99-128">已成功创建新条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-128">The new entry was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e9d99-129">说明</span><span class="sxs-lookup"><span data-stu-id="e9d99-129">Remarks</span></span>

<span data-ttu-id="e9d99-130">**IABContainer::CreateEntry**方法会返回一个指针接口实现进一步访问该条目指定容器中创建特定类型的新条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-130">The **IABContainer::CreateEntry** method creates a new entry of a particular type in the specified container, returning a pointer to an interface implementation for further access to the entry.</span></span> <span data-ttu-id="e9d99-131">使用已发布其一次性表中的可用模板的容器的列表中选择一个模板创建新条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-131">The new entry is created by using a template that has been selected from the container's list of available templates published in its one-off table.</span></span> <span data-ttu-id="e9d99-132">呼叫者通过调用其[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来访问容器的一次性表。</span><span class="sxs-lookup"><span data-stu-id="e9d99-132">Callers access a container's one-off table by calling its [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method and requesting the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e9d99-133">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e9d99-133">Notes to implementers</span></span>

<span data-ttu-id="e9d99-134">所有容器都支持**IABContainer::CreateEntry**方法必须都进行修改。</span><span class="sxs-lookup"><span data-stu-id="e9d99-134">All containers that support the **IABContainer::CreateEntry** method must be modifiable.</span></span> <span data-ttu-id="e9d99-135">指示可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置您的容器 AB_MODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="e9d99-135">Set your container's AB_MODIFIABLE flag in its **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property to indicate that it is modifiable.</span></span> 
  
<span data-ttu-id="e9d99-136">您应支持的所有_ulCreateFlags_标志。</span><span class="sxs-lookup"><span data-stu-id="e9d99-136">You should support all of the  _ulCreateFlags_ flags.</span></span> <span data-ttu-id="e9d99-137">但是，解释和使用这些标志是实现特定 — 即，您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 的语义实现的上下文中的含义。</span><span class="sxs-lookup"><span data-stu-id="e9d99-137">However, the interpretation and use of these flags is implementation specific—that is, you can determine what the semantics of CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT mean in the context of your implementation.</span></span> <span data-ttu-id="e9d99-138">如果您不能或不确定条目是否重复，始终允许创建的条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-138">If you cannot or do not determine whether an entry is a duplicate, always allow the entry to be created.</span></span> 
  
<span data-ttu-id="e9d99-139">某些提供程序实现严格条目匹配的显示名称，检查消息地址和中条目; 搜索键其他提供程序限制显示名称和地址匹配。</span><span class="sxs-lookup"><span data-stu-id="e9d99-139">Some providers implement strict entry checking by matching the display name, messaging address, and search key in an entry; other providers limit the match to display name and address.</span></span> <span data-ttu-id="e9d99-140">通常，通过检查的显示名称实现松散条目检查。</span><span class="sxs-lookup"><span data-stu-id="e9d99-140">Loose entry checking is often implemented by checking the display name only.</span></span> 
  
## <a name="notes-to-host-address-book-provider-implementers"></a><span data-ttu-id="e9d99-141">承载通讯簿提供程序实施者说明</span><span class="sxs-lookup"><span data-stu-id="e9d99-141">Notes to Host Address Book Provider Implementers</span></span>

<span data-ttu-id="e9d99-142">如果您的容器可以从其他提供程序的模板创建条目， **CreateEntry**的实现应提供存储为部分或全部与创建条目关联的属性。</span><span class="sxs-lookup"><span data-stu-id="e9d99-142">If your container can create entries from the templates of other providers, your implementation of **CreateEntry** should provide storage for some or all of the properties associated with the created entries.</span></span> <span data-ttu-id="e9d99-143">例如，如果您提供存储条目**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性，则可以而无需依赖于外的提供程序生成其详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="e9d99-143">For example, if you provide storage for an entry's **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property, you can generate its details dialog box without having to depend on the foreign provider.</span></span> 
  
<span data-ttu-id="e9d99-144">如果您的容器，可以创建支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的条目的**CreateEntry**实现必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e9d99-144">If your container can create entries that support the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property, your implementation of **CreateEntry** must do the following:</span></span> 
  
1. <span data-ttu-id="e9d99-145">调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e9d99-145">Call the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method.</span></span> <span data-ttu-id="e9d99-146">**OpenTemplateID**使外提供程序的代码要绑定到正在创建的新条目的条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-146">**OpenTemplateID** enables the foreign provider's code for the entry to bind to the new entry being created.</span></span> <span data-ttu-id="e9d99-147">外的提供程序支持此绑定进程控制通过其模板创建到主机地址簿提供程序的容器的条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-147">Foreign providers support this binding process to maintain control over entries created from their templates into the containers of host address book providers.</span></span> 
    
2. <span data-ttu-id="e9d99-148">执行任何必要的初始化，并填充的所有属性从项目中的外的提供程序从**OpenTemplateID** _lppMAPIPropNew_参数中返回的对象的新对象。</span><span class="sxs-lookup"><span data-stu-id="e9d99-148">Perform any necessary initialization, and populate the new object with all of the properties from the entry in the foreign provider that the object returned in the  _lppMAPIPropNew_ parameter from **OpenTemplateID**.</span></span>
    
<span data-ttu-id="e9d99-149">如果**OpenTemplateID**成功，则将属性复制_lppMAPIPropNew_参数指向的实现，而不是直接向_lpMAPIPropData_参数指向的实现。</span><span class="sxs-lookup"><span data-stu-id="e9d99-149">If **OpenTemplateID** succeeds, copy the properties to the implementation pointed to by the  _lppMAPIPropNew_ parameter rather than directly to the implementation pointed to by the  _lpMAPIPropData_ parameter.</span></span> <span data-ttu-id="e9d99-150">初始化脱机使用的新条目，就像外提供程序的任何其他项。</span><span class="sxs-lookup"><span data-stu-id="e9d99-150">Initialize the new entry for offline use as you would any other entry from a foreign provider.</span></span> 
  
<span data-ttu-id="e9d99-151">如果**OpenTemplateID**返回一个错误， **CreateEntry**应该会失败。</span><span class="sxs-lookup"><span data-stu-id="e9d99-151">If **OpenTemplateID** returns an error, **CreateEntry** should fail.</span></span> <span data-ttu-id="e9d99-152">不允许创建的条目。</span><span class="sxs-lookup"><span data-stu-id="e9d99-152">Do not allow the entry to be created.</span></span> <span data-ttu-id="e9d99-153">因为外的提供程序可以使数据作出假设您的提供商，不要创建一个条目具有不到外的提供程序成功绑定的模板标识符。</span><span class="sxs-lookup"><span data-stu-id="e9d99-153">Because the foreign provider can make assumptions about the data in your provider, do not create an entry with a template identifier that has not been successfully bound to the foreign provider.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="e9d99-154">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e9d99-154">Notes to callers</span></span>

<span data-ttu-id="e9d99-155">当**CreateEntry**返回时，则可能或可能无法立即访问新条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="e9d99-155">When **CreateEntry** returns, you may or may not be able to immediately access the entry identifier for the new entry.</span></span> <span data-ttu-id="e9d99-156">某些通讯簿提供程序后，不要做出它才可用以前呼叫过该新条目[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e9d99-156">Some address book providers do not make it available until after you have called the new entry's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="e9d99-157">尽管重复检查标志作为参数传递给**CreateEntry**，直到调用**SaveChanges**不会发生复制检查操作。</span><span class="sxs-lookup"><span data-stu-id="e9d99-157">Although duplicate checking flags are passed as parameters to **CreateEntry**, the duplicate checking operation does not occur until **SaveChanges** is called.</span></span> <span data-ttu-id="e9d99-158">因此，返回的**SaveChanges** ，而不是**CreateEntry**MAPI_E_COLLISION，这表明尝试创建现有条目，如相关的错误。</span><span class="sxs-lookup"><span data-stu-id="e9d99-158">Therefore, related errors such as MAPI_E_COLLISION, which indicates that an attempt was made to create an already existing entry, are returned by **SaveChanges** rather than **CreateEntry**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e9d99-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9d99-159">See also</span></span>



[<span data-ttu-id="e9d99-160">IABContainer::CopyEntries</span><span class="sxs-lookup"><span data-stu-id="e9d99-160">IABContainer::CopyEntries</span></span>](iabcontainer-copyentries.md)
  
[<span data-ttu-id="e9d99-161">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="e9d99-161">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="e9d99-162">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="e9d99-162">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="e9d99-163">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="e9d99-163">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="e9d99-164">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="e9d99-164">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

