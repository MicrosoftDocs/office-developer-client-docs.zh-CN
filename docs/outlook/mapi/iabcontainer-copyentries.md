---
title: IABContainerCopyEntries
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABContainer.CopyEntries
api_type:
- COM
ms.assetid: 4e775228-5ceb-4002-9b68-999fb5889b86
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ddb730ed92db4c8d281e7c8d5d9b18bc44505598
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32346394"
---
# <a name="iabcontainercopyentries"></a><span data-ttu-id="b9db4-103">IABContainer::CopyEntries</span><span class="sxs-lookup"><span data-stu-id="b9db4-103">IABContainer::CopyEntries</span></span>

  
  
<span data-ttu-id="b9db4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b9db4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b9db4-105">复制一个或多个条目, 通常是邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b9db4-105">Copies one or more entries, typically messaging users or distribution lists.</span></span>
  
```cpp
HRESULT CopyEntries(
  LPENTRYLIST lpEntries,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="b9db4-106">参数</span><span class="sxs-lookup"><span data-stu-id="b9db4-106">Parameters</span></span>

 <span data-ttu-id="b9db4-107">_lpEntries_</span><span class="sxs-lookup"><span data-stu-id="b9db4-107">_lpEntries_</span></span>
  
> <span data-ttu-id="b9db4-108">实时一个指针, 指向[ENTRYLIST](entrylist.md)结构的数组, 其中包含要复制的条目的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b9db4-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that contains the entry identifiers of the entries to copy.</span></span> 
    
 <span data-ttu-id="b9db4-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b9db4-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="b9db4-110">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="b9db4-110">[in] The handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="b9db4-111">如果在_ulFlags_参数中设置了 AB_NO_DIALOG 标志, 则_ulUIParam_参数必须为零。</span><span class="sxs-lookup"><span data-stu-id="b9db4-111">The  _ulUIParam_ parameter must be zero if the AB_NO_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b9db4-112">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="b9db4-112">_lpProgress_</span></span>
  
> <span data-ttu-id="b9db4-113">实时指向显示进度指示器的进度对象的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="b9db4-113">[in] A pointer to a progress object that displays a progress indicator, or NULL.</span></span> <span data-ttu-id="b9db4-114">如果_lpProgress_为 NULL, 则应使用 MAPI 通过[IMAPISupport::D oprogressdialog](imapisupport-doprogressdialog.md)方法提供的进度对象显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b9db4-114">If  _lpProgress_ is NULL, a progress indicator should be displayed by using the progress object supplied by MAPI through the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method.</span></span> <span data-ttu-id="b9db4-115">如果在_ulFlags_中设置了 AB_NO_DIALOG 标志, 则将忽略_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="b9db4-115">The  _lpProgress_ parameter is ignored if the AB_NO_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="b9db4-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b9db4-116">_ulFlags_</span></span>
  
> <span data-ttu-id="b9db4-117">实时用于控制如何执行复制操作的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b9db4-117">[in] A bitmask of flags that controls how the copy operation is performed.</span></span> <span data-ttu-id="b9db4-118">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="b9db4-118">The following flags can be set:</span></span>
    
<span data-ttu-id="b9db4-119">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="b9db4-119">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="b9db4-120">禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b9db4-120">Suppresses display of a progress indicator.</span></span> <span data-ttu-id="b9db4-121">如果未设置此标志, 则显示一个进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b9db4-121">If this flag is not set, a progress indicator is displayed.</span></span>
    
<span data-ttu-id="b9db4-122">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="b9db4-122">CREATE_CHECK_DUP_LOOSE</span></span> 
  
> <span data-ttu-id="b9db4-123">指示应执行的是松散级别的重复项检查。</span><span class="sxs-lookup"><span data-stu-id="b9db4-123">Indicates that a loose level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="b9db4-124">松散重复项检查的实现是特定于提供程序的。</span><span class="sxs-lookup"><span data-stu-id="b9db4-124">The implementation of loose duplicate entry checking is provider specific.</span></span> <span data-ttu-id="b9db4-125">例如, 提供程序可以将松散匹配定义为任意两个具有相同显示名称的条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-125">For example, a provider can define a loose match as any two entries that have the same display name.</span></span>
    
<span data-ttu-id="b9db4-126">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="b9db4-126">CREATE_CHECK_DUP_STRICT</span></span> 
  
> <span data-ttu-id="b9db4-127">指示应执行严格的重复项检查级别。</span><span class="sxs-lookup"><span data-stu-id="b9db4-127">Indicates that a strict level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="b9db4-128">严格的重复项检查实现是特定于提供程序的。</span><span class="sxs-lookup"><span data-stu-id="b9db4-128">The implementation of strict duplicate entry checking is provider specific.</span></span> <span data-ttu-id="b9db4-129">例如, 提供程序可以将一个严格的匹配定义为两个具有相同的显示名称和邮件地址的条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-129">For example, a provider can define a strict match as any two entries that have both the same display name and messaging address.</span></span>
    
<span data-ttu-id="b9db4-130">CREATE_REPLACE</span><span class="sxs-lookup"><span data-stu-id="b9db4-130">CREATE_REPLACE</span></span> 
  
> <span data-ttu-id="b9db4-131">指示一个新的条目应替换现有的条目, 如果确定两者是重复的。</span><span class="sxs-lookup"><span data-stu-id="b9db4-131">Indicates that a new entry should replace an existing one if it is determined that the two are duplicates.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b9db4-132">返回值</span><span class="sxs-lookup"><span data-stu-id="b9db4-132">Return value</span></span>

<span data-ttu-id="b9db4-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9db4-133">S_OK</span></span> 
  
> <span data-ttu-id="b9db4-134">复制操作成功。</span><span class="sxs-lookup"><span data-stu-id="b9db4-134">The copy operation succeeded.</span></span>
    
<span data-ttu-id="b9db4-135">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="b9db4-135">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="b9db4-136">复制操作全部成功, 但无法复制一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-136">The copy operation succeeded overall, but one or more of the entries could not be copied.</span></span> <span data-ttu-id="b9db4-137">返回此值时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="b9db4-137">When this value is returned, the call should be handled as successful.</span></span> <span data-ttu-id="b9db4-138">若要测试此值, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="b9db4-138">To test for this value, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="b9db4-139">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="b9db4-139">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b9db4-140">注解</span><span class="sxs-lookup"><span data-stu-id="b9db4-140">Remarks</span></span>

<span data-ttu-id="b9db4-141">**IABContainer:: CopyEntries**方法从同一个容器或不同的容器复制条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-141">The **IABContainer::CopyEntries** method copies entries from the same container or a different container.</span></span> <span data-ttu-id="b9db4-142">对**CopyEntries**的调用在功能上等效于为要复制的每个条目进行以下调用:</span><span class="sxs-lookup"><span data-stu-id="b9db4-142">A call to **CopyEntries** is functionally equivalent to making the following calls for each entry to be copied:</span></span> 
  
1. <span data-ttu-id="b9db4-143">用于创建新条目的[IABContainer:: CreateEntry](iabcontainer-createentry.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b9db4-143">The [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create the new entry.</span></span> 
    
2. <span data-ttu-id="b9db4-144">[IMAPIProp:: GetProps](imapiprop-getprops.md)方法可读取要复制的项的属性。</span><span class="sxs-lookup"><span data-stu-id="b9db4-144">The [IMAPIProp::GetProps](imapiprop-getprops.md) method to read properties from the entry to be copied.</span></span> 
    
3. <span data-ttu-id="b9db4-145">[IMAPIProp:: SetProps](imapiprop-setprops.md)方法将属性写入新条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-145">The [IMAPIProp::SetProps](imapiprop-setprops.md) method to write properties to the new entry.</span></span> 
    
4. <span data-ttu-id="b9db4-146">新条目的[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来执行保存。</span><span class="sxs-lookup"><span data-stu-id="b9db4-146">The new entry's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to perform a save.</span></span> 
    
5. <span data-ttu-id="b9db4-147">新条目的[IUnknown:: release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法, 用于释放容器的引用。</span><span class="sxs-lookup"><span data-stu-id="b9db4-147">The new entry's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) method to release the container's reference.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="b9db4-148">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="b9db4-148">Notes to implementers</span></span>

<span data-ttu-id="b9db4-149">支持**IABContainer:: CopyEntries**方法的所有容器都必须是可修改的。</span><span class="sxs-lookup"><span data-stu-id="b9db4-149">All containers that support the **IABContainer::CopyEntries** method must be modifiable.</span></span> <span data-ttu-id="b9db4-150">在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置容器的 AB_MODIFIABLE 标志, 以指示它是可修改的。</span><span class="sxs-lookup"><span data-stu-id="b9db4-150">Set your container's AB_MODIFIABLE flag in its **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property to indicate that it is modifiable.</span></span> 
  
<span data-ttu-id="b9db4-151">您必须支持所有标志;但是, 这些标志的解释和使用是特定于实现的, 也就是说, 您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义在实现的上下文中的含义。</span><span class="sxs-lookup"><span data-stu-id="b9db4-151">You must support all of the flags; however, the interpretation and use of these flags is implementation specific—that is, you can determine what the semantics of the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags mean in the context of your implementation.</span></span> <span data-ttu-id="b9db4-152">如果不能或不确定某个条目是否重复, 则始终允许复制该条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-152">If you cannot or do not determine whether an entry is a duplicate, always allow the entry to be copied.</span></span> 
  
<span data-ttu-id="b9db4-153">如果设置了 CREATE_REPLACE 标志, 无论是否设置了 CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT 以及条目是否重复, 都始终复制该条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-153">If the CREATE_REPLACE flag is set, always copy the entry regardless of whether CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT is set and whether the entry is a duplicate.</span></span> 
  
<span data-ttu-id="b9db4-154">如果未设置 CREATE_REPLACE 且 CREATE_CHECK_DUP_STRICT 已设置, 请检查重复项。</span><span class="sxs-lookup"><span data-stu-id="b9db4-154">If CREATE_REPLACE is not set and CREATE_CHECK_DUP_STRICT is set, check for duplicates.</span></span> <span data-ttu-id="b9db4-155">如果确定某一项是重复项, 则不要复制该项。</span><span class="sxs-lookup"><span data-stu-id="b9db4-155">If an entry is determined to be a duplicate, do not copy the entry.</span></span> 
  
<span data-ttu-id="b9db4-156">您无需支持 CREATE_REPLACE;不支持 CREATE_REPLACE 意味着您可以安全地忽略它并始终执行复制。</span><span class="sxs-lookup"><span data-stu-id="b9db4-156">You do not need to support CREATE_REPLACE; not supporting CREATE_REPLACE means that you can safely ignore it and always perform a copy.</span></span> 
  
<span data-ttu-id="b9db4-157">仅当无法复制 nonduplicate 条目时, 才返回警告 MAPI_W_PARTIAL_COMPLETION。</span><span class="sxs-lookup"><span data-stu-id="b9db4-157">Return the warning MAPI_W_PARTIAL_COMPLETION only if a nonduplicate entry cannot be copied.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b9db4-158">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b9db4-158">Notes to callers</span></span>

<span data-ttu-id="b9db4-159">使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志向提供程序指明您希望容器执行重复项检查的方式。</span><span class="sxs-lookup"><span data-stu-id="b9db4-159">Use the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags to indicate to the provider how you want the container to perform duplicate-entry checking.</span></span> <span data-ttu-id="b9db4-160">如果您需要添加一个条目, 而不考虑它是否重复, 则要么不设置这些标志中的任何一个, 要么设置 CREATE_REPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="b9db4-160">If you need to have an entry added regardless of whether it is a duplicate, either do not set either of these flags or set the CREATE_REPLACE flag.</span></span> <span data-ttu-id="b9db4-161">CREATE_REPLACE 指示您不介意条目是否重复;您始终希望它替换原始条目。</span><span class="sxs-lookup"><span data-stu-id="b9db4-161">CREATE_REPLACE indicates that you do not care if an entry is a duplicate; you always want it to replace the original entry.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b9db4-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9db4-162">See also</span></span>



[<span data-ttu-id="b9db4-163">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="b9db4-163">ENTRYLIST</span></span>](entrylist.md)
  
[<span data-ttu-id="b9db4-164">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="b9db4-164">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="b9db4-165">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b9db4-165">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="b9db4-166">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="b9db4-166">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="b9db4-167">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="b9db4-167">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

