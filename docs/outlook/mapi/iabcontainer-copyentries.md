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
# <a name="iabcontainercopyentries"></a><span data-ttu-id="b0c2f-103">IABContainer::CopyEntries</span><span class="sxs-lookup"><span data-stu-id="b0c2f-103">IABContainer::CopyEntries</span></span>

  
  
<span data-ttu-id="b0c2f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0c2f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0c2f-105">复制一个或多个条目，通常为邮件用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-105">Copies one or more entries, typically messaging users or distribution lists.</span></span>
  
```cpp
HRESULT CopyEntries(
  LPENTRYLIST lpEntries,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="b0c2f-106">参数</span><span class="sxs-lookup"><span data-stu-id="b0c2f-106">Parameters</span></span>

 <span data-ttu-id="b0c2f-107">_lpEntries_</span><span class="sxs-lookup"><span data-stu-id="b0c2f-107">_lpEntries_</span></span>
  
> <span data-ttu-id="b0c2f-108">[in]指向包含要复制的条目的条目标识符的 [ENTRYLIST](entrylist.md) 结构的数组的指针。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that contains the entry identifiers of the entries to copy.</span></span> 
    
 <span data-ttu-id="b0c2f-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b0c2f-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="b0c2f-110">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-110">[in] The handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="b0c2f-111">如果在  _ulFlags_ 参数中设置了 AB_NO_DIALOG 标志，则  _ulUIParam_ 参数必须为零。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-111">The  _ulUIParam_ parameter must be zero if the AB_NO_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b0c2f-112">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="b0c2f-112">_lpProgress_</span></span>
  
> <span data-ttu-id="b0c2f-113">[in]指向显示进度指示器的进度对象的指针，或 NULL。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-113">[in] A pointer to a progress object that displays a progress indicator, or NULL.</span></span> <span data-ttu-id="b0c2f-114">如果  _lpProgress_ 为 NULL，则应该使用 MAPI 通过 [IMAPISupport：:D oProgressDialog](imapisupport-doprogressdialog.md) 方法提供的进度对象来显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-114">If  _lpProgress_ is NULL, a progress indicator should be displayed by using the progress object supplied by MAPI through the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method.</span></span> <span data-ttu-id="b0c2f-115">如果在 ulFlags 中设置了 AB_NO_DIALOG 标志，则  _忽略 lpProgress_  _参数_。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-115">The  _lpProgress_ parameter is ignored if the AB_NO_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="b0c2f-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b0c2f-116">_ulFlags_</span></span>
  
> <span data-ttu-id="b0c2f-117">[in]控制复制操作执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-117">[in] A bitmask of flags that controls how the copy operation is performed.</span></span> <span data-ttu-id="b0c2f-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b0c2f-118">The following flags can be set:</span></span>
    
<span data-ttu-id="b0c2f-119">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="b0c2f-119">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="b0c2f-120">禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-120">Suppresses display of a progress indicator.</span></span> <span data-ttu-id="b0c2f-121">如果未设置此标志，则显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-121">If this flag is not set, a progress indicator is displayed.</span></span>
    
<span data-ttu-id="b0c2f-122">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="b0c2f-122">CREATE_CHECK_DUP_LOOSE</span></span> 
  
> <span data-ttu-id="b0c2f-123">指示应执行松散级别的重复项检查。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-123">Indicates that a loose level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="b0c2f-124">松散重复项检查的实现特定于提供程序。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-124">The implementation of loose duplicate entry checking is provider specific.</span></span> <span data-ttu-id="b0c2f-125">例如，提供程序可以将松散匹配定义为任何两个具有相同的匹配显示名称。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-125">For example, a provider can define a loose match as any two entries that have the same display name.</span></span>
    
<span data-ttu-id="b0c2f-126">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="b0c2f-126">CREATE_CHECK_DUP_STRICT</span></span> 
  
> <span data-ttu-id="b0c2f-127">指示应执行严格的重复项检查级别。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-127">Indicates that a strict level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="b0c2f-128">严格重复项检查的实现特定于提供程序。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-128">The implementation of strict duplicate entry checking is provider specific.</span></span> <span data-ttu-id="b0c2f-129">例如，提供程序可以将严格匹配定义为任何两个条目，这些条目具有相同的显示名称地址。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-129">For example, a provider can define a strict match as any two entries that have both the same display name and messaging address.</span></span>
    
<span data-ttu-id="b0c2f-130">CREATE_REPLACE</span><span class="sxs-lookup"><span data-stu-id="b0c2f-130">CREATE_REPLACE</span></span> 
  
> <span data-ttu-id="b0c2f-131">指示如果确定两者是重复项，则新条目应替换现有的条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-131">Indicates that a new entry should replace an existing one if it is determined that the two are duplicates.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b0c2f-132">返回值</span><span class="sxs-lookup"><span data-stu-id="b0c2f-132">Return value</span></span>

<span data-ttu-id="b0c2f-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0c2f-133">S_OK</span></span> 
  
> <span data-ttu-id="b0c2f-134">复制操作成功。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-134">The copy operation succeeded.</span></span>
    
<span data-ttu-id="b0c2f-135">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="b0c2f-135">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="b0c2f-136">复制操作整体成功，但无法复制一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-136">The copy operation succeeded overall, but one or more of the entries could not be copied.</span></span> <span data-ttu-id="b0c2f-137">返回此值时，应成功处理调用。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-137">When this value is returned, the call should be handled as successful.</span></span> <span data-ttu-id="b0c2f-138">若要测试此值，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-138">To test for this value, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="b0c2f-139">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-139">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b0c2f-140">备注</span><span class="sxs-lookup"><span data-stu-id="b0c2f-140">Remarks</span></span>

<span data-ttu-id="b0c2f-141">**IABContainer：：CopyEntries** 方法从同一容器或不同容器复制条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-141">The **IABContainer::CopyEntries** method copies entries from the same container or a different container.</span></span> <span data-ttu-id="b0c2f-142">对 **CopyEntries** 的调用在功能上等效于对要复制的每个条目进行以下调用：</span><span class="sxs-lookup"><span data-stu-id="b0c2f-142">A call to **CopyEntries** is functionally equivalent to making the following calls for each entry to be copied:</span></span> 
  
1. <span data-ttu-id="b0c2f-143">用于 [创建新条目的 IABContainer：：CreateEntry](iabcontainer-createentry.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-143">The [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create the new entry.</span></span> 
    
2. <span data-ttu-id="b0c2f-144">用于读取要复制的条目中的属性的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-144">The [IMAPIProp::GetProps](imapiprop-getprops.md) method to read properties from the entry to be copied.</span></span> 
    
3. <span data-ttu-id="b0c2f-145">[用于将属性写入新条目的 IMAPIProp：：SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-145">The [IMAPIProp::SetProps](imapiprop-setprops.md) method to write properties to the new entry.</span></span> 
    
4. <span data-ttu-id="b0c2f-146">要执行保存的新 [条目的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-146">The new entry's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to perform a save.</span></span> 
    
5. <span data-ttu-id="b0c2f-147">新条目的 [IUnknown：：Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) 方法，用于释放容器的引用。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-147">The new entry's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) method to release the container's reference.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="b0c2f-148">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="b0c2f-148">Notes to implementers</span></span>

<span data-ttu-id="b0c2f-149">支持 **IABContainer：：CopyEntries** 方法的所有容器都必须可修改。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-149">All containers that support the **IABContainer::CopyEntries** method must be modifiable.</span></span> <span data-ttu-id="b0c2f-150">使用[PidTagContainerFlags AB_MODIFIABLE PidTagContainerFlags](pidtagcontainerflags-canonical-property.md) PR_CONTAINER_FLAGS (设置容器的) 标志，以指示它是可修改的。 </span><span class="sxs-lookup"><span data-stu-id="b0c2f-150">Set your container's AB_MODIFIABLE flag in its **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property to indicate that it is modifiable.</span></span> 
  
<span data-ttu-id="b0c2f-151">必须支持所有标志;但是，这些标志的解释和使用特定于实现，也就是说，你可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义在实现上下文中的含义。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-151">You must support all of the flags; however, the interpretation and use of these flags is implementation specific—that is, you can determine what the semantics of the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags mean in the context of your implementation.</span></span> <span data-ttu-id="b0c2f-152">如果无法确定条目是否是重复项，请始终允许复制该条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-152">If you cannot or do not determine whether an entry is a duplicate, always allow the entry to be copied.</span></span> 
  
<span data-ttu-id="b0c2f-153">如果CREATE_REPLACE，则始终复制条目，CREATE_CHECK_DUP_LOOSE或CREATE_CHECK_DUP_STRICT条目是否重复。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-153">If the CREATE_REPLACE flag is set, always copy the entry regardless of whether CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT is set and whether the entry is a duplicate.</span></span> 
  
<span data-ttu-id="b0c2f-154">如果未CREATE_REPLACE未设置CREATE_CHECK_DUP_STRICT，请检查重复项。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-154">If CREATE_REPLACE is not set and CREATE_CHECK_DUP_STRICT is set, check for duplicates.</span></span> <span data-ttu-id="b0c2f-155">如果某个条目被确定为重复项，则不要复制该条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-155">If an entry is determined to be a duplicate, do not copy the entry.</span></span> 
  
<span data-ttu-id="b0c2f-156">无需支持CREATE_REPLACE;不支持CREATE_REPLACE意味着可以安全地忽略它并始终执行副本。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-156">You do not need to support CREATE_REPLACE; not supporting CREATE_REPLACE means that you can safely ignore it and always perform a copy.</span></span> 
  
<span data-ttu-id="b0c2f-157">仅在无法MAPI_W_PARTIAL_COMPLETION重复条目时，才返回警告消息。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-157">Return the warning MAPI_W_PARTIAL_COMPLETION only if a nonduplicate entry cannot be copied.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b0c2f-158">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b0c2f-158">Notes to callers</span></span>

<span data-ttu-id="b0c2f-159">使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志向提供程序指示您希望容器如何执行重复项检查。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-159">Use the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags to indicate to the provider how you want the container to perform duplicate-entry checking.</span></span> <span data-ttu-id="b0c2f-160">如果需要添加一个条目，无论该条目是否是重复项，请不要设置这些标志中的任一标志或设置CREATE_REPLACE标记。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-160">If you need to have an entry added regardless of whether it is a duplicate, either do not set either of these flags or set the CREATE_REPLACE flag.</span></span> <span data-ttu-id="b0c2f-161">CREATE_REPLACE表示您不关心条目是否重复;始终希望它替换原始条目。</span><span class="sxs-lookup"><span data-stu-id="b0c2f-161">CREATE_REPLACE indicates that you do not care if an entry is a duplicate; you always want it to replace the original entry.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b0c2f-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0c2f-162">See also</span></span>



[<span data-ttu-id="b0c2f-163">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="b0c2f-163">ENTRYLIST</span></span>](entrylist.md)
  
[<span data-ttu-id="b0c2f-164">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="b0c2f-164">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="b0c2f-165">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b0c2f-165">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="b0c2f-166">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="b0c2f-166">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="b0c2f-167">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="b0c2f-167">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

