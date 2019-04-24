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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9f80130279e3437dd9be947de97d3f0d4181165e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287026"
---
# <a name="iabcontainercreateentry"></a><span data-ttu-id="8b6d8-103">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="8b6d8-103">IABContainer::CreateEntry</span></span>

  
  
<span data-ttu-id="8b6d8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b6d8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b6d8-105">创建一个新的条目, 该条目可以是邮件用户、通讯组列表或其他容器。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-105">Creates a new entry, which can be a messaging user, a distribution list, or another container.</span></span>
  
```cpp
HRESULT CreateEntry(
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulCreateFlags,
  LPMAPIPROP FAR * lppMAPIPropEntry
);
```

## <a name="parameters"></a><span data-ttu-id="8b6d8-106">参数</span><span class="sxs-lookup"><span data-stu-id="8b6d8-106">Parameters</span></span>

 <span data-ttu-id="8b6d8-107">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="8b6d8-107">_cbEntryID_</span></span>
  
> <span data-ttu-id="8b6d8-108">实时由_lpEntryID_参数指向的条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-108">[in] The count of the bytes in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="8b6d8-109">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="8b6d8-109">_lpEntryID_</span></span>
  
> <span data-ttu-id="8b6d8-110">实时一个指针, 指向用于创建特定类型的新条目的模板的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-110">[in] A pointer to the entry identifier of a template for creating new entries of a particular type.</span></span> 
    
 <span data-ttu-id="8b6d8-111">_ulCreateFlags_</span><span class="sxs-lookup"><span data-stu-id="8b6d8-111">_ulCreateFlags_</span></span>
  
> <span data-ttu-id="8b6d8-112">实时用于控制如何执行条目创建的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-112">[in] A bitmask of flags that controls how entry creation is performed.</span></span> <span data-ttu-id="8b6d8-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="8b6d8-113">The following flags can be set:</span></span>
    
<span data-ttu-id="8b6d8-114">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="8b6d8-114">CREATE_CHECK_DUP_LOOSE</span></span> 
  
> <span data-ttu-id="8b6d8-115">应执行重复项检查的松散级别。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-115">A loose level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="8b6d8-116">松散重复项检查的实现是特定于提供程序的。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-116">The implementation of loose duplicate entry checking is provider specific.</span></span> <span data-ttu-id="8b6d8-117">例如, 提供程序可以将松散匹配定义为任意两个具有相同显示名称的条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-117">For example, a provider can define a loose match as any two entries that have the same display name.</span></span>
    
<span data-ttu-id="8b6d8-118">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="8b6d8-118">CREATE_CHECK_DUP_STRICT</span></span> 
  
> <span data-ttu-id="8b6d8-119">应执行严格的重复项检查级别。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-119">A strict level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="8b6d8-120">严格的重复项检查实现是特定于提供程序的。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-120">The implementation of strict duplicate entry checking is provider specific.</span></span> <span data-ttu-id="8b6d8-121">例如, 提供程序可以将一个严格的匹配定义为两个具有相同的显示名称和邮件地址的条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-121">For example, a provider can define a strict match as any two entries that have both the same display name and messaging address.</span></span>
    
<span data-ttu-id="8b6d8-122">CREATE_REPLACE</span><span class="sxs-lookup"><span data-stu-id="8b6d8-122">CREATE_REPLACE</span></span> 
  
> <span data-ttu-id="8b6d8-123">如果确定两个是重复的, 则新条目应替换现有条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-123">A new entry should replace an existing one if it is determined that the two are duplicates.</span></span>
    
 <span data-ttu-id="8b6d8-124">_lppMAPIPropEntry_</span><span class="sxs-lookup"><span data-stu-id="8b6d8-124">_lppMAPIPropEntry_</span></span>
  
> <span data-ttu-id="8b6d8-125">排除指向新创建的项的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-125">[out] A pointer to a pointer to the newly created entry.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8b6d8-126">返回值</span><span class="sxs-lookup"><span data-stu-id="8b6d8-126">Return value</span></span>

<span data-ttu-id="8b6d8-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b6d8-127">S_OK</span></span> 
  
> <span data-ttu-id="8b6d8-128">已成功创建新条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-128">The new entry was successfully created.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8b6d8-129">注解</span><span class="sxs-lookup"><span data-stu-id="8b6d8-129">Remarks</span></span>

<span data-ttu-id="8b6d8-130">**IABContainer:: CreateEntry**方法在指定的容器中创建特定类型的新条目, 返回指向接口实现的指针, 以便进一步访问该条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-130">The **IABContainer::CreateEntry** method creates a new entry of a particular type in the specified container, returning a pointer to an interface implementation for further access to the entry.</span></span> <span data-ttu-id="8b6d8-131">通过使用已从其一次性表中发布的容器列表中选择的模板来创建新条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-131">The new entry is created by using a template that has been selected from the container's list of available templates published in its one-off table.</span></span> <span data-ttu-id="8b6d8-132">调用方通过调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并请求**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性来访问容器的一次性表。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-132">Callers access a container's one-off table by calling its [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method and requesting the **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="8b6d8-133">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="8b6d8-133">Notes to implementers</span></span>

<span data-ttu-id="8b6d8-134">支持**IABContainer:: CreateEntry**方法的所有容器都必须是可修改的。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-134">All containers that support the **IABContainer::CreateEntry** method must be modifiable.</span></span> <span data-ttu-id="8b6d8-135">在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置容器的 AB_MODIFIABLE 标志, 以指示它是可修改的。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-135">Set your container's AB_MODIFIABLE flag in its **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property to indicate that it is modifiable.</span></span> 
  
<span data-ttu-id="8b6d8-136">您应支持所有_ulCreateFlags_标志。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-136">You should support all of the  _ulCreateFlags_ flags.</span></span> <span data-ttu-id="8b6d8-137">但是, 这些标志的解释和使用是特定于实现的, 也就是说, 您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 的语义在实现的上下文中的含义。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-137">However, the interpretation and use of these flags is implementation specific—that is, you can determine what the semantics of CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT mean in the context of your implementation.</span></span> <span data-ttu-id="8b6d8-138">如果不能或不确定某个条目是否重复, 则始终允许创建该条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-138">If you cannot or do not determine whether an entry is a duplicate, always allow the entry to be created.</span></span> 
  
<span data-ttu-id="8b6d8-139">某些提供程序通过在条目中匹配显示名称、邮件地址和搜索关键字来实现严格的条目检查。其他提供程序将匹配项限制为显示名称和地址。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-139">Some providers implement strict entry checking by matching the display name, messaging address, and search key in an entry; other providers limit the match to display name and address.</span></span> <span data-ttu-id="8b6d8-140">通常只通过检查显示名称来实现松散条目检查。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-140">Loose entry checking is often implemented by checking the display name only.</span></span> 
  
## <a name="notes-to-host-address-book-provider-implementers"></a><span data-ttu-id="8b6d8-141">主机通讯簿提供程序实施者注意事项</span><span class="sxs-lookup"><span data-stu-id="8b6d8-141">Notes to Host Address Book Provider Implementers</span></span>

<span data-ttu-id="8b6d8-142">如果您的容器可以从其他提供程序的模板中创建条目, 则**CreateEntry**的实现应为与创建的条目关联的部分或所有属性提供存储空间。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-142">If your container can create entries from the templates of other providers, your implementation of **CreateEntry** should provide storage for some or all of the properties associated with the created entries.</span></span> <span data-ttu-id="8b6d8-143">例如, 如果为条目的**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性提供存储空间, 则可以生成其详细信息对话框, 而无需依赖于外部提供程序。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-143">For example, if you provide storage for an entry's **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property, you can generate its details dialog box without having to depend on the foreign provider.</span></span> 
  
<span data-ttu-id="8b6d8-144">如果您的容器可以创建支持**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的条目, 则您的**CreateEntry**实现必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="8b6d8-144">If your container can create entries that support the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property, your implementation of **CreateEntry** must do the following:</span></span> 
  
1. <span data-ttu-id="8b6d8-145">调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-145">Call the [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) method.</span></span> <span data-ttu-id="8b6d8-146">**OpenTemplateID**为项启用外部提供程序的代码, 以便绑定到要创建的新项。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-146">**OpenTemplateID** enables the foreign provider's code for the entry to bind to the new entry being created.</span></span> <span data-ttu-id="8b6d8-147">外部提供程序支持此绑定过程, 以保持对从其模板中创建的条目的控制, 使其成为主机通讯簿提供程序的容器。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-147">Foreign providers support this binding process to maintain control over entries created from their templates into the containers of host address book providers.</span></span> 
    
2. <span data-ttu-id="8b6d8-148">执行任何必要的初始化, 并使用来自外部提供程序中的条目的所有属性填充新对象, 该对象从**OpenTemplateID**的_lppMAPIPropNew_参数中返回。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-148">Perform any necessary initialization, and populate the new object with all of the properties from the entry in the foreign provider that the object returned in the  _lppMAPIPropNew_ parameter from **OpenTemplateID**.</span></span>
    
<span data-ttu-id="8b6d8-149">如果**OpenTemplateID**成功, 请将属性复制到_lppMAPIPropNew_参数所指向的实现, 而不是直接指向_lpMAPIPropData_参数指向的实现。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-149">If **OpenTemplateID** succeeds, copy the properties to the implementation pointed to by the  _lppMAPIPropNew_ parameter rather than directly to the implementation pointed to by the  _lpMAPIPropData_ parameter.</span></span> <span data-ttu-id="8b6d8-150">像对待外部提供程序中的任何其他条目一样, 初始化新条目以供脱机使用。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-150">Initialize the new entry for offline use as you would any other entry from a foreign provider.</span></span> 
  
<span data-ttu-id="8b6d8-151">如果**OpenTemplateID**返回一个错误, **CreateEntry**应失败。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-151">If **OpenTemplateID** returns an error, **CreateEntry** should fail.</span></span> <span data-ttu-id="8b6d8-152">不允许创建该条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-152">Do not allow the entry to be created.</span></span> <span data-ttu-id="8b6d8-153">由于外部提供程序可以对提供程序中的数据进行假设, 因此不要创建具有未成功绑定到外部提供程序的模板标识符的条目。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-153">Because the foreign provider can make assumptions about the data in your provider, do not create an entry with a template identifier that has not been successfully bound to the foreign provider.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="8b6d8-154">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="8b6d8-154">Notes to callers</span></span>

<span data-ttu-id="8b6d8-155">当**CreateEntry**返回时, 您可能会 (也可能不能) 立即访问新条目的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-155">When **CreateEntry** returns, you may or may not be able to immediately access the entry identifier for the new entry.</span></span> <span data-ttu-id="8b6d8-156">在您调用新条目的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 一些通讯簿提供程序不会使其可用。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-156">Some address book providers do not make it available until after you have called the new entry's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> 
  
<span data-ttu-id="8b6d8-157">尽管将重复的检查标志作为参数传递给**CreateEntry**, 但在调用**SaveChanges**之前不会发生重复的检查操作。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-157">Although duplicate checking flags are passed as parameters to **CreateEntry**, the duplicate checking operation does not occur until **SaveChanges** is called.</span></span> <span data-ttu-id="8b6d8-158">因此, 诸如 MAPI_E_COLLISION 的相关错误 (表示试图创建已有条目) 由**SaveChanges**而不是**CreateEntry**返回。</span><span class="sxs-lookup"><span data-stu-id="8b6d8-158">Therefore, related errors such as MAPI_E_COLLISION, which indicates that an attempt was made to create an already existing entry, are returned by **SaveChanges** rather than **CreateEntry**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b6d8-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b6d8-159">See also</span></span>



[<span data-ttu-id="8b6d8-160">IABContainer::CopyEntries</span><span class="sxs-lookup"><span data-stu-id="8b6d8-160">IABContainer::CopyEntries</span></span>](iabcontainer-copyentries.md)
  
[<span data-ttu-id="8b6d8-161">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="8b6d8-161">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="8b6d8-162">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="8b6d8-162">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="8b6d8-163">PidTagCreateTemplates 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b6d8-163">PidTagCreateTemplates Canonical Property</span></span>](pidtagcreatetemplates-canonical-property.md)
  
[<span data-ttu-id="8b6d8-164">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="8b6d8-164">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

