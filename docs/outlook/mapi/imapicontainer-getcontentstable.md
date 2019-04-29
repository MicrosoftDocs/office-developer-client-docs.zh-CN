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
# <a name="imapicontainergetcontentstable"></a><span data-ttu-id="2b3b0-103">IMAPIContainer::GetContentsTable</span><span class="sxs-lookup"><span data-stu-id="2b3b0-103">IMAPIContainer::GetContentsTable</span></span>

  
  
<span data-ttu-id="2b3b0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b3b0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b3b0-105">返回指向容器的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-105">Returns a pointer to the container's contents table.</span></span>
  
```cpp
HRESULT GetContentsTable(
  ULONG ulFlags,
  LPMAPITABLE FAR * lppTable
);
```

## <a name="parameters"></a><span data-ttu-id="2b3b0-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b3b0-106">Parameters</span></span>

 <span data-ttu-id="2b3b0-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="2b3b0-107">_ulFlags_</span></span>
  
> <span data-ttu-id="2b3b0-108">实时用于控制如何返回内容表的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-108">[in] A bitmask of flags that controls how the contents table is returned.</span></span> <span data-ttu-id="2b3b0-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="2b3b0-109">The following flags can be set:</span></span>
    
<span data-ttu-id="2b3b0-110">MAPI_ASSOCIATED</span><span class="sxs-lookup"><span data-stu-id="2b3b0-110">MAPI_ASSOCIATED</span></span> 
  
> <span data-ttu-id="2b3b0-111">应返回容器的关联内容表, 而不是标准内容表。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-111">The container's associated contents table should be returned instead of the standard contents table.</span></span> <span data-ttu-id="2b3b0-112">此标志仅用于文件夹。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-112">This flag is used only with folders.</span></span> <span data-ttu-id="2b3b0-113">"关联的内容" 表中包含的邮件是在对[IMAPIFolder:: CreateMessage](imapifolder-createmessage.md)方法的调用中设置的 MAPI_ASSOCIATED 标志创建的。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-113">The messages that are included in the associated contents table were created with the MAPI_ASSOCIATED flag set in the call to the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method.</span></span> <span data-ttu-id="2b3b0-114">客户端通常使用关联的内容表检索表单、视图和其他隐藏邮件。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-114">Clients typically use the associated contents table to retrieve forms, views, and other hidden messages.</span></span> 
    
<span data-ttu-id="2b3b0-115">ACLTABLE_FREEBUSY</span><span class="sxs-lookup"><span data-stu-id="2b3b0-115">ACLTABLE_FREEBUSY</span></span>
  
> <span data-ttu-id="2b3b0-116">启用对**PR_MEMBER_RIGHTS**中的 frightsFreeBusySimple 和 frightsFreeBusyDetailed 权限的访问。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-116">Enables access to the frightsFreeBusySimple and frightsFreeBusyDetailed rights in **PR_MEMBER_RIGHTS**.</span></span>
    
<span data-ttu-id="2b3b0-117">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="2b3b0-117">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="2b3b0-118">在将表提供给调用程序之前, 可能会成功返回**GetContentsTable** 。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-118">**GetContentsTable** can return successfully, possibly before the table is made available to the caller.</span></span> <span data-ttu-id="2b3b0-119">如果该表不可用, 则进行后续的表调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-119">If the table is not available, making a subsequent table call can raise an error.</span></span> 
    
<span data-ttu-id="2b3b0-120">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2b3b0-120">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="2b3b0-121">请求以 Unicode 格式返回包含字符串数据的列。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-121">Requests that the columns that contain string data be returned in the Unicode format.</span></span> <span data-ttu-id="2b3b0-122">如果未设置 MAPI_UNICODE 标志, 则应以 ANSI 格式返回字符串。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-122">If the MAPI_UNICODE flag is not set, the strings should be returned in the ANSI format.</span></span> 
    
<span data-ttu-id="2b3b0-123">SHOW_SOFT_DELETES</span><span class="sxs-lookup"><span data-stu-id="2b3b0-123">SHOW_SOFT_DELETES</span></span>
  
> <span data-ttu-id="2b3b0-124">显示当前标记为软删除的项目, 即它们处于 "已删除邮件" 保留时间阶段。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-124">Shows items that are currently marked as soft deleted—that is, they are in the deleted item retention time phase.</span></span>
    
 <span data-ttu-id="2b3b0-125">_lppTable_</span><span class="sxs-lookup"><span data-stu-id="2b3b0-125">_lppTable_</span></span>
  
> <span data-ttu-id="2b3b0-126">排除指向内容表的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-126">[out] A pointer to a pointer to the contents table.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2b3b0-127">返回值</span><span class="sxs-lookup"><span data-stu-id="2b3b0-127">Return value</span></span>

<span data-ttu-id="2b3b0-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b3b0-128">S_OK</span></span> 
  
> <span data-ttu-id="2b3b0-129">已成功检索内容表。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-129">The contents table was successfully retrieved.</span></span>
    
<span data-ttu-id="2b3b0-130">MAPI_E_BAD_CHARWIDTH</span><span class="sxs-lookup"><span data-stu-id="2b3b0-130">MAPI_E_BAD_CHARWIDTH</span></span> 
  
> <span data-ttu-id="2b3b0-131">设置了 MAPI_UNICODE 标志, 且实现不支持 unicode, 或者未设置 MAPI_UNICODE, 且实现仅支持 UNICODE。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-131">Either the MAPI_UNICODE flag was set and the implementation does not support Unicode, or MAPI_UNICODE was not set and the implementation supports only Unicode.</span></span>
    
<span data-ttu-id="2b3b0-132">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="2b3b0-132">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="2b3b0-133">容器没有内容, 无法提供内容表。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-133">The container has no contents and cannot provide a contents table.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2b3b0-134">说明</span><span class="sxs-lookup"><span data-stu-id="2b3b0-134">Remarks</span></span>

<span data-ttu-id="2b3b0-135">**IMAPIContainer:: GetContentsTable**方法返回指向容器的内容表的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-135">The **IMAPIContainer::GetContentsTable** method returns a pointer to the contents table of a container.</span></span> <span data-ttu-id="2b3b0-136">内容表包含容器中对象的摘要信息。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-136">A contents table contains summary information about objects in the container.</span></span> 
  
<span data-ttu-id="2b3b0-137">内容表具有冗长的列集。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-137">Contents tables have lengthy column sets.</span></span> <span data-ttu-id="2b3b0-138">有关内容表中必填和可选的列的完整列表, 请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-138">For a complete list of the required and optional columns in contents tables, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="2b3b0-139">某些容器可能不包含任何内容。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-139">It is possible for some containers to have no contents.</span></span> <span data-ttu-id="2b3b0-140">这些容器从其**GetContentsTable**的实现返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-140">These containers return MAPI_E_NO_SUPPORT from their implementations of **GetContentsTable**.</span></span>
  
## <a name="notes-to-implementers"></a><span data-ttu-id="2b3b0-141">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="2b3b0-141">Notes to implementers</span></span>

<span data-ttu-id="2b3b0-142">如果您支持容器的内容表, 还必须执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2b3b0-142">If you support a contents table for your container, you must also do the following:</span></span>
  
- <span data-ttu-id="2b3b0-143">支持对容器的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法的调用, 以打开**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-143">Support calls to the container's [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method to open the **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="2b3b0-144">返回**PR_CONTAINER_CONTENTS**以响应对容器的调用</span><span class="sxs-lookup"><span data-stu-id="2b3b0-144">Return **PR_CONTAINER_CONTENTS** in response to a call to the container's</span></span> 
    
    <span data-ttu-id="2b3b0-145">[IMAPIProp:: GetProps](imapiprop-getprops.md)和[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-145">[IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::GetPropList](imapiprop-getproplist.md) methods.</span></span> 
    
<span data-ttu-id="2b3b0-146">远程传输提供程序的此方法的实现必须在传递给**GetContentsTable**方法的_ppTable_参数中返回指向[IMAPITable: IUnknown](imapitableiunknown.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-146">A remote transport provider's implementation of this method must return a pointer to an [IMAPITable : IUnknown](imapitableiunknown.md) interface in the  _ppTable_ parameter passed into the **GetContentsTable** method.</span></span> <span data-ttu-id="2b3b0-147">如果您的传输提供程序具有现有的内容表, 则可以返回指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-147">If your transport provider has an existing contents table, it is sufficient to return a pointer to it.</span></span> <span data-ttu-id="2b3b0-148">如果不是, 则此方法必须创建一个新的[IMAPITable: IUnknown](imapitableiunknown.md)对象, 使用邮件头填充该表 (如果有的话), 并返回指向新表的指针。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-148">If not, this method must create a new [IMAPITable : IUnknown](imapitableiunknown.md) object, populate the table with message headers (if any are available), and return a pointer to the new table.</span></span> <span data-ttu-id="2b3b0-149">[ITableData:: HrGetView](itabledata-hrgetview.md)方法用于生成返回值并将表指针存储在_ppTable_参数中。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-149">The [ITableData::HrGetView](itabledata-hrgetview.md) method is useful for generating a return value and storing the table pointer in the  _ppTable_ parameter.</span></span> <span data-ttu-id="2b3b0-150">"内容" 表必须至少支持下列属性列:</span><span class="sxs-lookup"><span data-stu-id="2b3b0-150">The contents table must support at least the following property columns:</span></span> 
  
- <span data-ttu-id="2b3b0-151">**PR_ENTRYID**([PidTagEntryID](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-151">**PR_ENTRYID** ([PidTagEntryID](pidtagentryid-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-152">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-152">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-153">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-153">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-154">**PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-154">**PR_DISPLAY_TO** ([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-155">**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-155">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-156">**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-156">**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-157">**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-157">**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-158">**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-158">**PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-159">**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-159">**PR_PRIORITY** ([PidTagPriority](pidtagpriority-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-160">**PR_IMPORTANCE**([PidTagImportance](pidtagimportance-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-160">**PR_IMPORTANCE** ([PidTagImportance](pidtagimportance-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-161">**PR_SENSITIVITY**([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-161">**PR_SENSITIVITY** ([PidTagSensitivity](pidtagsensitivity-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-162">**PR_MESSAGE_DELIVERY_TIME**([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-162">**PR_MESSAGE_DELIVERY_TIME** ([PidTagMessageDeliveryTime](pidtagmessagedeliverytime-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-163">**PR_MSG_STATUS**([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-163">**PR_MSG_STATUS** ([PidTagMessageStatus](pidtagmessagestatus-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-164">**PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-164">**PR_MESSAGE_DOWNLOAD_TIME** ([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-165">**PR_HASATTACH**([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-165">**PR_HASATTACH** ([PidTagHasAttachments](pidtaghasattachments-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-166">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-166">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-167">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-167">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
    
- <span data-ttu-id="2b3b0-168">**PR_NORMALIZED_SUBJECT**([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="2b3b0-168">**PR_NORMALIZED_SUBJECT** ([PidTagNormalizedSubject](pidtagnormalizedsubject-canonical-property.md))</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="2b3b0-169">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="2b3b0-169">Notes to callers</span></span>

<span data-ttu-id="2b3b0-170">字符串和二进制内容表中的列可以被截断。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-170">String and binary contents table columns can be truncated.</span></span> <span data-ttu-id="2b3b0-171">通常, 提供程序返回255个字符。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-171">Typically, providers return 255 characters.</span></span> <span data-ttu-id="2b3b0-172">由于您无法事先知道表是否包括截断的列, 因此假定列的长度为255或510字节时, 将截断列。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-172">Because you cannot know beforehand whether a table includes truncated columns, assume that a column is truncated if the length of the column is either 255 or 510 bytes.</span></span> <span data-ttu-id="2b3b0-173">如果需要, 您始终可以从对象中直接检索已截断列的完整值, 方法是使用其条目标识符将其打开, 然后调用**IMAPIProp:: GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-173">You can always retrieve the full value of a truncated column, if necessary, directly from the object by using its entry identifier to open it and then calling the **IMAPIProp::GetProps** method.</span></span> 
  
<span data-ttu-id="2b3b0-174">根据提供程序的实现, 限制和排序操作可应用于所有字符串或该字符串的截断版本。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-174">Depending on the provider's implementation, restrictions and sorting operations can apply to all of a string or to the truncated version of that string.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2b3b0-175">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2b3b0-175">MFCMAPI reference</span></span>

<span data-ttu-id="2b3b0-176">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-176">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2b3b0-177">**文件**</span><span class="sxs-lookup"><span data-stu-id="2b3b0-177">**File**</span></span>|<span data-ttu-id="2b3b0-178">**函数**</span><span class="sxs-lookup"><span data-stu-id="2b3b0-178">**Function**</span></span>|<span data-ttu-id="2b3b0-179">**备注**</span><span class="sxs-lookup"><span data-stu-id="2b3b0-179">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b3b0-180">ContentsTableDialog</span><span class="sxs-lookup"><span data-stu-id="2b3b0-180">ContentsTableDialog.cpp</span></span>  <br/> |<span data-ttu-id="2b3b0-181">CContentsTableDlg:: CContentsTableDlg</span><span class="sxs-lookup"><span data-stu-id="2b3b0-181">CContentsTableDlg::CContentsTableDlg</span></span>  <br/> |<span data-ttu-id="2b3b0-182">**CContentsTableDlg**类使用**GetContentsTable**获取内容表中的项。</span><span class="sxs-lookup"><span data-stu-id="2b3b0-182">The **CContentsTableDlg** class uses **GetContentsTable** to obtain the entries in a contents table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2b3b0-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b3b0-183">See also</span></span>



[<span data-ttu-id="2b3b0-184">IMAPIProp::GetPropList</span><span class="sxs-lookup"><span data-stu-id="2b3b0-184">IMAPIProp::GetPropList</span></span>](imapiprop-getproplist.md)
  
[<span data-ttu-id="2b3b0-185">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="2b3b0-185">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="2b3b0-186">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="2b3b0-186">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="2b3b0-187">IMAPITable : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2b3b0-187">IMAPITable : IUnknown</span></span>](imapitableiunknown.md)
  
[<span data-ttu-id="2b3b0-188">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="2b3b0-188">PidTagContainerContents Canonical Property</span></span>](pidtagcontainercontents-canonical-property.md)
  
[<span data-ttu-id="2b3b0-189">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="2b3b0-189">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)


[<span data-ttu-id="2b3b0-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="2b3b0-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

