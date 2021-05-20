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
ms.openlocfilehash: 28315c5a09eba32816a0b63513cb98d1c30a96bb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431104"
---
# <a name="imapicontainergetcontentstable"></a><span data-ttu-id="2eedc-103">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="2eedc-103">IMAPIContainer::GetContentsTable</span></span>

  
  
<span data-ttu-id="2eedc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2eedc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2eedc-105">返回一个指向容器内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-105">Returns a pointer to the container's contents table.</span></span>
  
```cpp
HRESULT GetContentsTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="2eedc-106">参数</span><span class="sxs-lookup"><span data-stu-id="2eedc-106">Parameters</span></span>

 <span data-ttu-id="2eedc-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2eedc-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2eedc-108">[in]控制如何返回内容表的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2eedc-108">[in] A bitmask of flags that controls how the contents table is returned.</span></span> <span data-ttu-id="2eedc-109">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="2eedc-109">The following flags can be set:</span></span>
    
<span data-ttu-id="2eedc-110">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="2eedc-110">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="2eedc-111">应返回容器的关联内容表，而不是标准内容表。</span><span class="sxs-lookup"><span data-stu-id="2eedc-111">The container's associated contents table should be returned instead of the standard contents table.</span></span> <span data-ttu-id="2eedc-112">此标志仅用于文件夹。</span><span class="sxs-lookup"><span data-stu-id="2eedc-112">This flag is used only with folders.</span></span> <span data-ttu-id="2eedc-113">关联内容表中包含的消息是在对 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法的调用中设置的 MAPI_ASSOCIATED 标志创建的。</span><span class="sxs-lookup"><span data-stu-id="2eedc-113">The messages that are included in the associated contents table were created with the MAPI_ASSOCIATED flag set in the call to the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="2eedc-114">客户端通常使用关联的内容表检索表单、视图和其他隐藏邮件。</span><span class="sxs-lookup"><span data-stu-id="2eedc-114">Clients typically use the associated contents table to retrieve forms, views, and other hidden messages.</span></span> 
    
<span data-ttu-id="2eedc-115">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="2eedc-115">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="2eedc-116">启用对 frightsFreeBusySimple 和 frightsFreeBusyDetailed 权限 **PR_MEMBER_RIGHTS。**</span><span class="sxs-lookup"><span data-stu-id="2eedc-116">Enables access to the frightsFreeBusySimple and frightsFreeBusyDetailed rights in **PR_MEMBER_RIGHTS**.</span></span>
    
<span data-ttu-id="2eedc-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="2eedc-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="2eedc-118">**GetContentsTable** 可以成功返回，可能在表对调用方可用之前。</span><span class="sxs-lookup"><span data-stu-id="2eedc-118">**GetContentsTable** can return successfully, possibly before the table is made available to the caller.</span></span> <span data-ttu-id="2eedc-119">如果表不可用，则进行后续表调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="2eedc-119">If the table is not available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="2eedc-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2eedc-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2eedc-121">请求以 Unicode 格式返回包含字符串数据的列。</span><span class="sxs-lookup"><span data-stu-id="2eedc-121">Requests that the columns that contain string data be returned in the Unicode format.</span></span> <span data-ttu-id="2eedc-122">如果未MAPI_UNICODE，则应该以 ANSI 格式返回字符串。</span><span class="sxs-lookup"><span data-stu-id="2eedc-122">If the MAPI_UNICODE flag is not set, the strings should be returned in the ANSI format.</span></span> 
    
<span data-ttu-id="2eedc-123">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="2eedc-123">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="2eedc-124">显示当前标记为软删除的项目，即它们处于已删除项目的保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="2eedc-124">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="2eedc-125">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="2eedc-125">_lppTable_</span></span>
  
> <span data-ttu-id="2eedc-126">[out]指向指向内容表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-126">[out] A pointer to a pointer to the contents table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2eedc-127">返回值</span><span class="sxs-lookup"><span data-stu-id="2eedc-127">Return value</span></span>

<span data-ttu-id="2eedc-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="2eedc-128">S_OK</span></span> 
  
> <span data-ttu-id="2eedc-129">已成功检索内容表。</span><span class="sxs-lookup"><span data-stu-id="2eedc-129">The contents table was successfully retrieved.</span></span>
    
<span data-ttu-id="2eedc-130">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="2eedc-130">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="2eedc-131">设置 MAPI_UNICODE 标志，而实现不支持 Unicode，或者MAPI_UNICODE未设置，并且实现仅支持 Unicode。</span><span class="sxs-lookup"><span data-stu-id="2eedc-131">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="2eedc-132">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2eedc-132">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="2eedc-133">容器没有内容，并且无法提供内容表。</span><span class="sxs-lookup"><span data-stu-id="2eedc-133">The container has no contents and cannot provide a contents table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2eedc-134">备注</span><span class="sxs-lookup"><span data-stu-id="2eedc-134">Remarks</span></span>

<span data-ttu-id="2eedc-135">**IMAPIContainer：：GetContentsTable** 方法返回指向容器的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-135">The **IMAPIContainer::GetContentsTable** method returns a pointer to the contents table of a container.</span></span> <span data-ttu-id="2eedc-136">内容表包含有关容器中对象的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="2eedc-136">A contents table contains summary information about objects in the container.</span></span> 
  
<span data-ttu-id="2eedc-137">内容表具有长列集。</span><span class="sxs-lookup"><span data-stu-id="2eedc-137">Contents tables have lengthy column sets.</span></span> <span data-ttu-id="2eedc-138">有关内容表中必需列和可选列的完整列表，请参阅[Contents Tables。](contents-tables.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-138">For a complete list of the required and optional columns in contents tables, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="2eedc-139">某些容器可能没有内容。</span><span class="sxs-lookup"><span data-stu-id="2eedc-139">It is possible for some containers to have no contents.</span></span> <span data-ttu-id="2eedc-140">这些容器从MAPI_E_NO_SUPPORT **GetContentsTable 的实现中返回值**。</span><span class="sxs-lookup"><span data-stu-id="2eedc-140">These containers return MAPI_E_NO_SUPPORT from their implementations of **GetContentsTable**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2eedc-141">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2eedc-141">Notes to implementers</span></span>

<span data-ttu-id="2eedc-142">如果支持容器的内容表，则还必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2eedc-142">If you support a contents table for your container, you must also do the following:</span></span>
  
- <span data-ttu-id="2eedc-143">支持调用容器 [的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法以打开 PR_CONTAINER_CONTENTS **(** [PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2eedc-143">Support calls to the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="2eedc-144">返回 **PR_CONTAINER_CONTENTS** 响应对容器的调用</span><span class="sxs-lookup"><span data-stu-id="2eedc-144">Return **PR_CONTAINER_CONTENTS** in response to a call to the container's</span></span> 
    
    <span data-ttu-id="2eedc-145">[IMAPIProp：：GetProps](imapiprop-getprops.md) 和 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="2eedc-145">[IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::GetPropList](imapiprop-getproplist.md) methods.</span></span> 
    
<span data-ttu-id="2eedc-146">远程传输提供程序的此方法实现必须返回一个指向传入 **GetContentsTable** 方法的 _ppTable_ 参数中的 [IMAPITable ： IUnknown](imapitableiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-146">A remote transport provider's implementation of this method must return a pointer to an [IMAPITable : IUnknown](imapitableiunknown.md) interface in the  _ppTable_ parameter passed into the **GetContentsTable** method.</span></span> <span data-ttu-id="2eedc-147">如果您的传输提供程序具有现有内容表，则足以返回指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-147">If your transport provider has an existing contents table, it is sufficient to return a pointer to it.</span></span> <span data-ttu-id="2eedc-148">如果没有，此方法必须创建新的 [IMAPITable ： IUnknown](imapitableiunknown.md) 对象，使用消息头 (（如果有可用) ）填充表，并返回指向新表的指针。</span><span class="sxs-lookup"><span data-stu-id="2eedc-148">If not, this method must create a new [IMAPITable : IUnknown](imapitableiunknown.md) object, populate the table with message headers (if any are available), and return a pointer to the new table.</span></span> <span data-ttu-id="2eedc-149">[ITableData：：HrGetView](itabledata-hrgetview.md)方法可用于生成返回值，以及将表指针存储在 _ppTable_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="2eedc-149">The [ITableData::HrGetView](itabledata-hrgetview.md) method is useful for generating a return value and storing the table pointer in the  _ppTable_ parameter.</span></span> <span data-ttu-id="2eedc-150">contents 表必须至少支持以下属性列：</span><span class="sxs-lookup"><span data-stu-id="2eedc-150">The contents table must support at least the following property columns:</span></span> 
  
- <span data-ttu-id="2eedc-151">**PR_ENTRYID (** [PidTagEntryID](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-151">**PR_ENTRYID** ([PidTagEntryID](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-152">**PR_SENDER_NAME (** [PidTagSenderName](pidtagsendername-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-152">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-153">**PR_SENT_REPRESENTING_NAME (** [PidTagSentRepresentingName)](pidtagsentrepresentingname-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-153">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-154">**PR_DISPLAY_TO (** [PidTagDisplayTo](pidtagdisplayto-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-154">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-155">**PR_SUBJECT (** [PidTagSubject)](pidtagsubject-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-155">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-156">**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-156">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-157">**PR_MESSAGE_FLAGS (** [PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-157">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-158">**PR_MESSAGE_SIZE (** [PidTagMessageSize](pidtagmessagesize-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-158">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-159">**PR_PRIORITY (** [PidTagPriority)](pidtagpriority-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-159">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-160">**PR_IMPORTANCE (** [PidTagImportance)](pidtagimportance-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-160">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-161">**PR_SENSITIVITY (** [PidTagSensitivity)](pidtagsensitivity-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-161">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-162">**PR_MESSAGE_DELIVERY_TIME (** [PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-162">**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-163">**PR_MSG_STATUS (** [PidTagMessageStatus)](pidtagmessagestatus-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-163">**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-164">**PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-164">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-165">**PR_HASATTACH (** [PidTagHasAttachments)](pidtaghasattachments-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-165">**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-166">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-166">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-167">**PR_INSTANCE_KEY (** [PidTagInstanceKey](pidtaginstancekey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="2eedc-167">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="2eedc-168">**PR_NORMALIZED_SUBJECT (** [PidTagNormalizedSubject)](pidtagnormalizedsubject-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="2eedc-168">**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="2eedc-169">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2eedc-169">Notes to callers</span></span>

<span data-ttu-id="2eedc-170">字符串和二进制内容表列可能会被截断。</span><span class="sxs-lookup"><span data-stu-id="2eedc-170">String and binary contents table columns can be truncated.</span></span> <span data-ttu-id="2eedc-171">通常，提供程序返回 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="2eedc-171">Typically, providers return 255 characters.</span></span> <span data-ttu-id="2eedc-172">由于无法事先知道表是否包含截断的列，因此假定如果列的长度为 255 或 510 字节，则会截断列。</span><span class="sxs-lookup"><span data-stu-id="2eedc-172">Because you cannot know beforehand whether a table includes truncated columns, assume that a column is truncated if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="2eedc-173">您始终可以在需要时直接从对象检索截断列的完整值，方法是使用其条目标识符打开它，然后调用 **IMAPIProp：：GetProps** 方法。</span><span class="sxs-lookup"><span data-stu-id="2eedc-173">You can always retrieve the full value of a truncated column, if necessary, directly from the object by using its entry identifier to open it and then calling the **IMAPIProp::GetProps** method.</span></span> 
  
<span data-ttu-id="2eedc-174">根据提供程序的实现，限制和排序操作可应用于所有字符串或该字符串的截断版本。</span><span class="sxs-lookup"><span data-stu-id="2eedc-174">Depending on the provider's implementation, restrictions and sorting operations can apply to all of a string or to the truncated version of that string.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2eedc-175">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2eedc-175">MFCMAPI reference</span></span>

<span data-ttu-id="2eedc-176">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2eedc-176">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2eedc-177">**文件**</span><span class="sxs-lookup"><span data-stu-id="2eedc-177">**File**</span></span>|<span data-ttu-id="2eedc-178">**函数**</span><span class="sxs-lookup"><span data-stu-id="2eedc-178">**Function**</span></span>|<span data-ttu-id="2eedc-179">**备注**</span><span class="sxs-lookup"><span data-stu-id="2eedc-179">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2eedc-180">ContentsTableDialog.cpp</span><span class="sxs-lookup"><span data-stu-id="2eedc-180">ContentsTableDialog.cpp</span></span>  <br/> |<span data-ttu-id="2eedc-181">CContentsTableDlg：：CContentsTableDlg</span><span class="sxs-lookup"><span data-stu-id="2eedc-181">CContentsTableDlg::CContentsTableDlg</span></span>  <br/> |<span data-ttu-id="2eedc-182">**CContentsTableDlg** 类使用 **GetContentsTable** 获取内容表中的条目。</span><span class="sxs-lookup"><span data-stu-id="2eedc-182">The **CContentsTableDlg** class uses **GetContentsTable** to obtain the entries in a contents table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2eedc-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2eedc-183">See also</span></span>



[<span data-ttu-id="2eedc-184">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="2eedc-184">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="2eedc-185">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="2eedc-185">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="2eedc-186">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="2eedc-186">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="2eedc-187">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2eedc-187">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="2eedc-188">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="2eedc-188">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="2eedc-189">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2eedc-189">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="2eedc-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2eedc-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

