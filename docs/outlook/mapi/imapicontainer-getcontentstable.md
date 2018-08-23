---
title: IMAPIContainerGetContentsTable
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIContainer.GetContentsTable
api_type:
- COM
ms.assetid: 88c7a666-875d-473a-b126-dbbb7009f7d9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9fb8919287420038b5c9165bb14b7d33d1ad2fe1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578862"
---
# <a name="imapicontainergetcontentstable"></a><span data-ttu-id="e8d69-103">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="e8d69-103">IMAPIContainer::GetContentsTable</span></span>

  
  
<span data-ttu-id="e8d69-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e8d69-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e8d69-105">返回到容器的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="e8d69-105">Returns a pointer to the container's contents table.</span></span>
  
```cpp
HRESULT GetContentsTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="e8d69-106">参数</span><span class="sxs-lookup"><span data-stu-id="e8d69-106">Parameters</span></span>

 <span data-ttu-id="e8d69-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e8d69-107">_ulFlags_</span></span>
  
> <span data-ttu-id="e8d69-108">[in]位掩码的标志，控制如何返回的内容表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-108">[in] A bitmask of flags that controls how the contents table is returned.</span></span> <span data-ttu-id="e8d69-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e8d69-109">The following flags can be set:</span></span>
    
<span data-ttu-id="e8d69-110">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="e8d69-110">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="e8d69-111">应返回容器的关联的内容表而不是标准内容表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-111">The container's associated contents table should be returned instead of the standard contents table.</span></span> <span data-ttu-id="e8d69-112">此标志仅用于文件夹。</span><span class="sxs-lookup"><span data-stu-id="e8d69-112">This flag is used only with folders.</span></span> <span data-ttu-id="e8d69-113">对[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法的调用中设置 MAPI_ASSOCIATED 标志创建关联的内容表中包含的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8d69-113">The messages that are included in the associated contents table were created with the MAPI_ASSOCIATED flag set in the call to the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="e8d69-114">客户端通常使用关联的内容表检索窗体、 视图和其他隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="e8d69-114">Clients typically use the associated contents table to retrieve forms, views, and other hidden messages.</span></span> 
    
<span data-ttu-id="e8d69-115">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="e8d69-115">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="e8d69-116">允许访问 frightsFreeBusySimple 和 frightsFreeBusyDetailed **PR_MEMBER_RIGHTS**中的权限。</span><span class="sxs-lookup"><span data-stu-id="e8d69-116">Enables access to the frightsFreeBusySimple and frightsFreeBusyDetailed rights in **PR_MEMBER_RIGHTS**.</span></span>
    
<span data-ttu-id="e8d69-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="e8d69-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="e8d69-118">**GetContentsTable**可以成功，可能之前返回表可用于将呼叫者。</span><span class="sxs-lookup"><span data-stu-id="e8d69-118">**GetContentsTable** can return successfully, possibly before the table is made available to the caller.</span></span> <span data-ttu-id="e8d69-119">如果表不可用，则进行后续表呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="e8d69-119">If the table is not available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="e8d69-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e8d69-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="e8d69-121">Unicode 格式返回包含字符串数据的列的请求。</span><span class="sxs-lookup"><span data-stu-id="e8d69-121">Requests that the columns that contain string data be returned in the Unicode format.</span></span> <span data-ttu-id="e8d69-122">如果未设置 MAPI_UNICODE 标志，应以 ANSI 格式返回字符串。</span><span class="sxs-lookup"><span data-stu-id="e8d69-122">If the MAPI_UNICODE flag is not set, the strings should be returned in the ANSI format.</span></span> 
    
<span data-ttu-id="e8d69-123">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="e8d69-123">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="e8d69-124">显示项目的当前标记为软删除 — 即，它们是中已删除的邮件保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="e8d69-124">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="e8d69-125">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="e8d69-125">_lppTable_</span></span>
  
> <span data-ttu-id="e8d69-126">[输出]指向内容表格的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e8d69-126">[out] A pointer to a pointer to the contents table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e8d69-127">返回值</span><span class="sxs-lookup"><span data-stu-id="e8d69-127">Return value</span></span>

<span data-ttu-id="e8d69-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8d69-128">S_OK</span></span> 
  
> <span data-ttu-id="e8d69-129">已成功检索内容表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-129">The contents table was successfully retrieved.</span></span>
    
<span data-ttu-id="e8d69-130">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="e8d69-130">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="e8d69-131">既设置了 MAPI_UNICODE 标志实现不支持 Unicode，或未设置 MAPI_UNICODE 并实现支持仅 Unicode。</span><span class="sxs-lookup"><span data-stu-id="e8d69-131">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="e8d69-132">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="e8d69-132">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="e8d69-133">容器未包含任何内容，并不能提供内容表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-133">The container has no contents and cannot provide a contents table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e8d69-134">注解</span><span class="sxs-lookup"><span data-stu-id="e8d69-134">Remarks</span></span>

<span data-ttu-id="e8d69-135">**IMAPIContainer::GetContentsTable**方法返回容器的内容表格的指针。</span><span class="sxs-lookup"><span data-stu-id="e8d69-135">The **IMAPIContainer::GetContentsTable** method returns a pointer to the contents table of a container.</span></span> <span data-ttu-id="e8d69-136">内容表包含有关容器中的对象的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="e8d69-136">A contents table contains summary information about objects in the container.</span></span> 
  
<span data-ttu-id="e8d69-137">内容表包含冗长列集。</span><span class="sxs-lookup"><span data-stu-id="e8d69-137">Contents tables have lengthy column sets.</span></span> <span data-ttu-id="e8d69-138">有关内容表中的必需的和可选的列的完整列表，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="e8d69-138">For a complete list of the required and optional columns in contents tables, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="e8d69-139">很可能为一些容器具有任何内容。</span><span class="sxs-lookup"><span data-stu-id="e8d69-139">It is possible for some containers to have no contents.</span></span> <span data-ttu-id="e8d69-140">这些容器返回 MAPI_E_NO_SUPPORT 从**GetContentsTable**其实现。</span><span class="sxs-lookup"><span data-stu-id="e8d69-140">These containers return MAPI_E_NO_SUPPORT from their implementations of **GetContentsTable**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="e8d69-141">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="e8d69-141">Notes to implementers</span></span>

<span data-ttu-id="e8d69-142">如果您为您的容器支持内容表，还必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8d69-142">If you support a contents table for your container, you must also do the following:</span></span>
  
- <span data-ttu-id="e8d69-143">支持对容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法的调用，以打开**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="e8d69-143">Support calls to the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="e8d69-144">对容器的呼叫的响应中返回**PR_CONTAINER_CONTENTS**</span><span class="sxs-lookup"><span data-stu-id="e8d69-144">Return **PR_CONTAINER_CONTENTS** in response to a call to the container's</span></span> 
    
    <span data-ttu-id="e8d69-145">[IMAPIProp::GetProps](imapiprop-getprops.md)和[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e8d69-145">[IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::GetPropList](imapiprop-getproplist.md) methods.</span></span> 
    
<span data-ttu-id="e8d69-146">远程传输提供程序实现此方法必须返回一个指向[IMAPITable: IUnknown](imapitableiunknown.md) _ppTable_参数传递到**GetContentsTable**方法中的接口。</span><span class="sxs-lookup"><span data-stu-id="e8d69-146">A remote transport provider's implementation of this method must return a pointer to an [IMAPITable : IUnknown](imapitableiunknown.md) interface in the  _ppTable_ parameter passed into the **GetContentsTable** method.</span></span> <span data-ttu-id="e8d69-147">如果您传输提供程序具有现有内容表，它就足以返回指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="e8d69-147">If your transport provider has an existing contents table, it is sufficient to return a pointer to it.</span></span> <span data-ttu-id="e8d69-148">如果没有，此方法必须创建一个新[IMAPITable: IUnknown](imapitableiunknown.md)对象、 填充 （如果可用） 的邮件头，具有表和一个指针返回到新表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-148">If not, this method must create a new [IMAPITable : IUnknown](imapitableiunknown.md) object, populate the table with message headers (if any are available), and return a pointer to the new table.</span></span> <span data-ttu-id="e8d69-149">[ITableData::HrGetView](itabledata-hrgetview.md)方法可用于生成的返回值和_ppTable_参数中存储表指针。</span><span class="sxs-lookup"><span data-stu-id="e8d69-149">The [ITableData::HrGetView](itabledata-hrgetview.md) method is useful for generating a return value and storing the table pointer in the  _ppTable_ parameter.</span></span> <span data-ttu-id="e8d69-150">将目录必须至少支持下列属性：</span><span class="sxs-lookup"><span data-stu-id="e8d69-150">The contents table must support at least the following property columns:</span></span> 
  
- <span data-ttu-id="e8d69-151">**PR_ENTRYID**([PidTagEntryID](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-151">**PR_ENTRYID** ([PidTagEntryID](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-152">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-152">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-153">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-153">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-154">**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-154">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-155">**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-155">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-156">**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-156">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-157">**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-157">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-158">**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-158">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-159">**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-159">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-160">**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-160">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-161">**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-161">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-162">**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-162">**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-163">**PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-163">**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-164">**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-164">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-165">**PR_HASATTACH**([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-165">**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-166">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-166">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-167">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-167">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="e8d69-168">**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e8d69-168">**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="e8d69-169">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="e8d69-169">Notes to callers</span></span>

<span data-ttu-id="e8d69-170">可以截断字符串和二进制内容表格列。</span><span class="sxs-lookup"><span data-stu-id="e8d69-170">String and binary contents table columns can be truncated.</span></span> <span data-ttu-id="e8d69-171">通常情况下，提供程序返回 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="e8d69-171">Typically, providers return 255 characters.</span></span> <span data-ttu-id="e8d69-172">因为您无法知道提前是否表包含截断的列，假定一列被截断如果列的长度为 255 个或 510 字节。</span><span class="sxs-lookup"><span data-stu-id="e8d69-172">Because you cannot know beforehand whether a table includes truncated columns, assume that a column is truncated if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="e8d69-173">直接从通过使用其条目标识符来打开它，然后调用**IMAPIProp::GetProps**方法的对象，总是可以检索有必要，截断列中的完整值。</span><span class="sxs-lookup"><span data-stu-id="e8d69-173">You can always retrieve the full value of a truncated column, if necessary, directly from the object by using its entry identifier to open it and then calling the **IMAPIProp::GetProps** method.</span></span> 
  
<span data-ttu-id="e8d69-174">具体取决于提供程序的实现、 限制和排序操作可以应用于所有字符串或该字符串的截断版本。</span><span class="sxs-lookup"><span data-stu-id="e8d69-174">Depending on the provider's implementation, restrictions and sorting operations can apply to all of a string or to the truncated version of that string.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="e8d69-175">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="e8d69-175">MFCMAPI reference</span></span>

<span data-ttu-id="e8d69-176">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e8d69-176">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e8d69-177">**文件**</span><span class="sxs-lookup"><span data-stu-id="e8d69-177">**File**</span></span>|<span data-ttu-id="e8d69-178">**函数**</span><span class="sxs-lookup"><span data-stu-id="e8d69-178">**Function**</span></span>|<span data-ttu-id="e8d69-179">**Comment**</span><span class="sxs-lookup"><span data-stu-id="e8d69-179">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8d69-180">ContentsTableDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="e8d69-180">ContentsTableDialog.cpp</span></span>  <br/> |<span data-ttu-id="e8d69-181">CContentsTableDlg::CContentsTableDlg</span><span class="sxs-lookup"><span data-stu-id="e8d69-181">CContentsTableDlg::CContentsTableDlg</span></span>  <br/> |<span data-ttu-id="e8d69-182">**CContentsTableDlg**类使用**GetContentsTable**获取内容表中的条目。</span><span class="sxs-lookup"><span data-stu-id="e8d69-182">The **CContentsTableDlg** class uses **GetContentsTable** to obtain the entries in a contents table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e8d69-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8d69-183">See also</span></span>



[<span data-ttu-id="e8d69-184">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="e8d69-184">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="e8d69-185">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="e8d69-185">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="e8d69-186">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="e8d69-186">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="e8d69-187">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e8d69-187">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="e8d69-188">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="e8d69-188">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="e8d69-189">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e8d69-189">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="e8d69-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="e8d69-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

