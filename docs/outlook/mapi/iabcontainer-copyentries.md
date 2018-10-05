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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ddb730ed92db4c8d281e7c8d5d9b18bc44505598
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382944"
---
# <a name="iabcontainercopyentries"></a><span data-ttu-id="679de-103">IABContainer::CopyEntries</span><span class="sxs-lookup"><span data-stu-id="679de-103">IABContainer::CopyEntries</span></span>

  
  
<span data-ttu-id="679de-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="679de-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="679de-105">复制一个或多个条目，通常消息的用户或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="679de-105">Copies one or more entries, typically messaging users or distribution lists.</span></span>
  
```cpp
HRESULT CopyEntries(
  LPENTRYLIST lpEntries,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="679de-106">参数</span><span class="sxs-lookup"><span data-stu-id="679de-106">Parameters</span></span>

 <span data-ttu-id="679de-107">_lpEntries_</span><span class="sxs-lookup"><span data-stu-id="679de-107">_lpEntries_</span></span>
  
> <span data-ttu-id="679de-108">[in]指向包含要复制的项的项标识符的[ENTRYLIST](entrylist.md)结构数组的指针。</span><span class="sxs-lookup"><span data-stu-id="679de-108">[in] A pointer to an array of [ENTRYLIST](entrylist.md) structures that contains the entry identifiers of the entries to copy.</span></span> 
    
 <span data-ttu-id="679de-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="679de-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="679de-110">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="679de-110">[in] The handle to the parent window of any dialog boxes or windows that this method displays.</span></span> <span data-ttu-id="679de-111">_UlUIParam_参数必须为零，如果_ulFlags_参数中设置 AB_NO_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="679de-111">The  _ulUIParam_ parameter must be zero if the AB_NO_DIALOG flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="679de-112">_lpProgress_</span><span class="sxs-lookup"><span data-stu-id="679de-112">_lpProgress_</span></span>
  
> <span data-ttu-id="679de-113">[in]指向显示进度指示器，则为 NULL 的进度对象的指针。</span><span class="sxs-lookup"><span data-stu-id="679de-113">[in] A pointer to a progress object that displays a progress indicator, or NULL.</span></span> <span data-ttu-id="679de-114">如果_lpProgress_为 NULL，则应使用由 MAPI 提供通过[IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md)方法的进度对象显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="679de-114">If  _lpProgress_ is NULL, a progress indicator should be displayed by using the progress object supplied by MAPI through the [IMAPISupport::DoProgressDialog](imapisupport-doprogressdialog.md) method.</span></span> <span data-ttu-id="679de-115">如果_ulFlags_中设置了 AB_NO_DIALOG 标志，则忽略_lpProgress_参数。</span><span class="sxs-lookup"><span data-stu-id="679de-115">The  _lpProgress_ parameter is ignored if the AB_NO_DIALOG flag is set in  _ulFlags_.</span></span>
    
 <span data-ttu-id="679de-116">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="679de-116">_ulFlags_</span></span>
  
> <span data-ttu-id="679de-117">[in]位掩码的标志，控制如何执行复制操作。</span><span class="sxs-lookup"><span data-stu-id="679de-117">[in] A bitmask of flags that controls how the copy operation is performed.</span></span> <span data-ttu-id="679de-118">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="679de-118">The following flags can be set:</span></span>
    
<span data-ttu-id="679de-119">AB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="679de-119">AB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="679de-120">禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="679de-120">Suppresses display of a progress indicator.</span></span> <span data-ttu-id="679de-121">如果未设置此标志，将显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="679de-121">If this flag is not set, a progress indicator is displayed.</span></span>
    
<span data-ttu-id="679de-122">CREATE_CHECK_DUP_LOOSE</span><span class="sxs-lookup"><span data-stu-id="679de-122">CREATE_CHECK_DUP_LOOSE</span></span> 
  
> <span data-ttu-id="679de-123">指示应执行的重复项检查松散级别。</span><span class="sxs-lookup"><span data-stu-id="679de-123">Indicates that a loose level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="679de-124">提供程序特定的松散重复项检查实现。</span><span class="sxs-lookup"><span data-stu-id="679de-124">The implementation of loose duplicate entry checking is provider specific.</span></span> <span data-ttu-id="679de-125">例如，提供程序可以定义松散匹配项，如任何具有相同的两个条目的显示名称。</span><span class="sxs-lookup"><span data-stu-id="679de-125">For example, a provider can define a loose match as any two entries that have the same display name.</span></span>
    
<span data-ttu-id="679de-126">CREATE_CHECK_DUP_STRICT</span><span class="sxs-lookup"><span data-stu-id="679de-126">CREATE_CHECK_DUP_STRICT</span></span> 
  
> <span data-ttu-id="679de-127">指示应执行的重复项检查严格级别。</span><span class="sxs-lookup"><span data-stu-id="679de-127">Indicates that a strict level of duplicate entry checking should be performed.</span></span> <span data-ttu-id="679de-128">提供程序特定的严格的重复项检查实现。</span><span class="sxs-lookup"><span data-stu-id="679de-128">The implementation of strict duplicate entry checking is provider specific.</span></span> <span data-ttu-id="679de-129">例如，提供程序可以定义严格匹配项，如任何具有两个相同的两个条目显示名称和消息地址。</span><span class="sxs-lookup"><span data-stu-id="679de-129">For example, a provider can define a strict match as any two entries that have both the same display name and messaging address.</span></span>
    
<span data-ttu-id="679de-130">CREATE_REPLACE</span><span class="sxs-lookup"><span data-stu-id="679de-130">CREATE_REPLACE</span></span> 
  
> <span data-ttu-id="679de-131">指示是否确定两个是重复项，新条目应替换现有的场。</span><span class="sxs-lookup"><span data-stu-id="679de-131">Indicates that a new entry should replace an existing one if it is determined that the two are duplicates.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="679de-132">返回值</span><span class="sxs-lookup"><span data-stu-id="679de-132">Return value</span></span>

<span data-ttu-id="679de-133">S_OK</span><span class="sxs-lookup"><span data-stu-id="679de-133">S_OK</span></span> 
  
> <span data-ttu-id="679de-134">复制操作已成功。</span><span class="sxs-lookup"><span data-stu-id="679de-134">The copy operation succeeded.</span></span>
    
<span data-ttu-id="679de-135">MAPI_W_PARTIAL_COMPLETION</span><span class="sxs-lookup"><span data-stu-id="679de-135">MAPI_W_PARTIAL_COMPLETION</span></span> 
  
> <span data-ttu-id="679de-136">复制操作成功总体上讲，但无法复制一个或多个条目。</span><span class="sxs-lookup"><span data-stu-id="679de-136">The copy operation succeeded overall, but one or more of the entries could not be copied.</span></span> <span data-ttu-id="679de-137">返回此值时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="679de-137">When this value is returned, the call should be handled as successful.</span></span> <span data-ttu-id="679de-138">若要测试此值，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="679de-138">To test for this value, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="679de-139">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="679de-139">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="679de-140">说明</span><span class="sxs-lookup"><span data-stu-id="679de-140">Remarks</span></span>

<span data-ttu-id="679de-141">**IABContainer::CopyEntries**方法将从同一个容器或其他容器复制条目。</span><span class="sxs-lookup"><span data-stu-id="679de-141">The **IABContainer::CopyEntries** method copies entries from the same container or a different container.</span></span> <span data-ttu-id="679de-142">调用**CopyEntries**功能上等效于调用以下为每个要复制的项：</span><span class="sxs-lookup"><span data-stu-id="679de-142">A call to **CopyEntries** is functionally equivalent to making the following calls for each entry to be copied:</span></span> 
  
1. <span data-ttu-id="679de-143">要创建新条目的[IABContainer::CreateEntry](iabcontainer-createentry.md)方法。</span><span class="sxs-lookup"><span data-stu-id="679de-143">The [IABContainer::CreateEntry](iabcontainer-createentry.md) method to create the new entry.</span></span> 
    
2. <span data-ttu-id="679de-144">要从要复制的项读取属性的[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="679de-144">The [IMAPIProp::GetProps](imapiprop-getprops.md) method to read properties from the entry to be copied.</span></span> 
    
3. <span data-ttu-id="679de-145">要属性写入新条目的[IMAPIProp::SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="679de-145">The [IMAPIProp::SetProps](imapiprop-setprops.md) method to write properties to the new entry.</span></span> 
    
4. <span data-ttu-id="679de-146">新条目的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法执行保存。</span><span class="sxs-lookup"><span data-stu-id="679de-146">The new entry's [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to perform a save.</span></span> 
    
5. <span data-ttu-id="679de-147">新条目的[IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx)方法来释放容器的引用。</span><span class="sxs-lookup"><span data-stu-id="679de-147">The new entry's [IUnknown::Release](https://msdn.microsoft.com/library/ms682317%28VS.85%29.aspx) method to release the container's reference.</span></span> 
    
## <a name="notes-to-implementers"></a><span data-ttu-id="679de-148">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="679de-148">Notes to implementers</span></span>

<span data-ttu-id="679de-149">所有容器都支持**IABContainer::CopyEntries**方法必须都进行修改。</span><span class="sxs-lookup"><span data-stu-id="679de-149">All containers that support the **IABContainer::CopyEntries** method must be modifiable.</span></span> <span data-ttu-id="679de-150">指示可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置您的容器 AB_MODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="679de-150">Set your container's AB_MODIFIABLE flag in its **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property to indicate that it is modifiable.</span></span> 
  
<span data-ttu-id="679de-151">您必须支持的所有标志;但是，解释和使用这些标志是实现特定 — 即，您可以确定 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志的语义实现的上下文中的含义。</span><span class="sxs-lookup"><span data-stu-id="679de-151">You must support all of the flags; however, the interpretation and use of these flags is implementation specific—that is, you can determine what the semantics of the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags mean in the context of your implementation.</span></span> <span data-ttu-id="679de-152">如果您不能或不确定条目是否重复，始终允许要复制的条目。</span><span class="sxs-lookup"><span data-stu-id="679de-152">If you cannot or do not determine whether an entry is a duplicate, always allow the entry to be copied.</span></span> 
  
<span data-ttu-id="679de-153">如果设置了 CREATE_REPLACE 标志，始终复制而不考虑是否设置 CREATE_CHECK_DUP_LOOSE 或 CREATE_CHECK_DUP_STRICT 和条目是否重复的条目。</span><span class="sxs-lookup"><span data-stu-id="679de-153">If the CREATE_REPLACE flag is set, always copy the entry regardless of whether CREATE_CHECK_DUP_LOOSE or CREATE_CHECK_DUP_STRICT is set and whether the entry is a duplicate.</span></span> 
  
<span data-ttu-id="679de-154">如果未设置 CREATE_REPLACE 并设置 CREATE_CHECK_DUP_STRICT，检查重复项。</span><span class="sxs-lookup"><span data-stu-id="679de-154">If CREATE_REPLACE is not set and CREATE_CHECK_DUP_STRICT is set, check for duplicates.</span></span> <span data-ttu-id="679de-155">如果条目确定要重复，不复制该条目。</span><span class="sxs-lookup"><span data-stu-id="679de-155">If an entry is determined to be a duplicate, do not copy the entry.</span></span> 
  
<span data-ttu-id="679de-156">不需要支持 CREATE_REPLACE;不支持 CREATE_REPLACE 意味着，您可以放心地忽略并且始终执行复制。</span><span class="sxs-lookup"><span data-stu-id="679de-156">You do not need to support CREATE_REPLACE; not supporting CREATE_REPLACE means that you can safely ignore it and always perform a copy.</span></span> 
  
<span data-ttu-id="679de-157">仅当未复制条目不能复制返回警告 MAPI_W_PARTIAL_COMPLETION。</span><span class="sxs-lookup"><span data-stu-id="679de-157">Return the warning MAPI_W_PARTIAL_COMPLETION only if a nonduplicate entry cannot be copied.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="679de-158">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="679de-158">Notes to callers</span></span>

<span data-ttu-id="679de-159">使用 CREATE_CHECK_DUP_LOOSE 和 CREATE_CHECK_DUP_STRICT 标志指示到提供程序所需的容器执行重复项检查的方式。</span><span class="sxs-lookup"><span data-stu-id="679de-159">Use the CREATE_CHECK_DUP_LOOSE and CREATE_CHECK_DUP_STRICT flags to indicate to the provider how you want the container to perform duplicate-entry checking.</span></span> <span data-ttu-id="679de-160">如果您需要具有添加无论它是否是重复的条目，既不设置这些标志任一或设置 CREATE_REPLACE 标志。</span><span class="sxs-lookup"><span data-stu-id="679de-160">If you need to have an entry added regardless of whether it is a duplicate, either do not set either of these flags or set the CREATE_REPLACE flag.</span></span> <span data-ttu-id="679de-161">CREATE_REPLACE 指示不关心是否条目是重复;希望它始终以替换原始条目。</span><span class="sxs-lookup"><span data-stu-id="679de-161">CREATE_REPLACE indicates that you do not care if an entry is a duplicate; you always want it to replace the original entry.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="679de-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="679de-162">See also</span></span>



[<span data-ttu-id="679de-163">ENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="679de-163">ENTRYLIST</span></span>](entrylist.md)
  
[<span data-ttu-id="679de-164">IABContainer::CreateEntry</span><span class="sxs-lookup"><span data-stu-id="679de-164">IABContainer::CreateEntry</span></span>](iabcontainer-createentry.md)
  
[<span data-ttu-id="679de-165">IMAPIProgress : IUnknown</span><span class="sxs-lookup"><span data-stu-id="679de-165">IMAPIProgress : IUnknown</span></span>](imapiprogressiunknown.md)
  
[<span data-ttu-id="679de-166">IMAPIProp::SaveChanges</span><span class="sxs-lookup"><span data-stu-id="679de-166">IMAPIProp::SaveChanges</span></span>](imapiprop-savechanges.md)
  
[<span data-ttu-id="679de-167">IABContainer : IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="679de-167">IABContainer : IMAPIContainer</span></span>](iabcontainerimapicontainer.md)

