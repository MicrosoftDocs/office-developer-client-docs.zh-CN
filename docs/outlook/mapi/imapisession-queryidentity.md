---
title: IMAPISessionQueryIdentity
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.QueryIdentity
api_type:
- COM
ms.assetid: a2cdda90-5457-49a7-b98c-7273ffe5cbbc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 396320c6b39553da09aa1f45d0c755f40a939382
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428219"
---
# <a name="imapisessionqueryidentity"></a><span data-ttu-id="b1648-103">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="b1648-103">IMAPISession::QueryIdentity</span></span>

  
  
<span data-ttu-id="b1648-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1648-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1648-105">返回提供会话的主标识的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b1648-105">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="b1648-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1648-106">Parameters</span></span>

 <span data-ttu-id="b1648-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b1648-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="b1648-108">[out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="b1648-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b1648-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="b1648-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="b1648-110">[out]指向指向提供主标识的对象的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b1648-110">[out] A pointer to a pointer to the entry identifier of the object that provides the primary identity.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b1648-111">返回值</span><span class="sxs-lookup"><span data-stu-id="b1648-111">Return value</span></span>

<span data-ttu-id="b1648-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1648-112">S_OK</span></span> 
  
> <span data-ttu-id="b1648-113">已成功返回主标识。</span><span class="sxs-lookup"><span data-stu-id="b1648-113">The primary identity was successfully returned.</span></span>
    
<span data-ttu-id="b1648-114">MAPI_W_NO_SERVICE</span><span class="sxs-lookup"><span data-stu-id="b1648-114">MAPI_W_NO_SERVICE</span></span> 
  
> <span data-ttu-id="b1648-115">调用成功，但没有会话的主标识。</span><span class="sxs-lookup"><span data-stu-id="b1648-115">The call succeeded, but there is no primary identity for the session.</span></span> <span data-ttu-id="b1648-116">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="b1648-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="b1648-117">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="b1648-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="b1648-118">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="b1648-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b1648-119">备注</span><span class="sxs-lookup"><span data-stu-id="b1648-119">Remarks</span></span>

<span data-ttu-id="b1648-120">**IMAPISession：：QueryIdentity** 方法检索当前会话的主标识，并通过 _lppEntryID_ 参数返回值。</span><span class="sxs-lookup"><span data-stu-id="b1648-120">The **IMAPISession::QueryIdentity** method retrieves the primary identity for the current session and returns the value through the  _lppEntryID_ parameter.</span></span> <span data-ttu-id="b1648-121">主标识是一个对象，通常为消息用户，表示会话的用户。</span><span class="sxs-lookup"><span data-stu-id="b1648-121">The primary identity is an object, typically a messaging user, that represents the user of a session.</span></span>  <span data-ttu-id="b1648-122">_lppEntryID_ 返回 [IMailUser](imailuserimapiprop.md) 对象的主标识，该对象也存储为 [PidTagEntryID](pidtagentryid-canonical-property.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="b1648-122">_lppEntryID_ returns the primary identity for an [IMailUser](imailuserimapiprop.md) object, which is also stored as the [PidTagEntryID](pidtagentryid-canonical-property.md) property.</span></span> <span data-ttu-id="b1648-123">可以使用 _lppEntryID_ 中返回的值，使用 [IMAPISession：：OpenEntry](imapisession-openentry.md)打开 **IMailUser** 对象。</span><span class="sxs-lookup"><span data-stu-id="b1648-123">You can use the value returned in  _lppEntryID_ to open an **IMailUser** object using [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span>
  
<span data-ttu-id="b1648-124">尽管多个邮件服务中的许多服务提供商可以为会话提供主标识，但 MAPI 指定单个服务提供商。</span><span class="sxs-lookup"><span data-stu-id="b1648-124">Although many service providers in multiple message services can provide the primary identity for a session, MAPI designates a single service provider.</span></span> <span data-ttu-id="b1648-125">提供主标识的服务提供商将设置以下项：</span><span class="sxs-lookup"><span data-stu-id="b1648-125">The service provider that supplies the primary identity sets the following items:</span></span>
  
- <span data-ttu-id="b1648-126">STATUS_PRIMARY_IDENTITY [PidTagResourceFlags](pidtagresourceflags-canonical-property.md) PR_RESOURCE_FLAGS (标记) 标记。 </span><span class="sxs-lookup"><span data-stu-id="b1648-126">The STATUS_PRIMARY_IDENTITY flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="b1648-127">The **PR_IDENTITY_DISPLAY (** [PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="b1648-127">The **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="b1648-128">The **PR_IDENTITY_ENTRYID (** [PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="b1648-128">The **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="b1648-129">The **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="b1648-129">The **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="b1648-130">如果提供主标识的服务提供商属于邮件服务，则邮件服务中的其他服务提供商也会设置PR_IDENTITY属性。</span><span class="sxs-lookup"><span data-stu-id="b1648-130">If the service provider that supplies the primary identity belongs to a message service, the other service providers in the message service also set the PR_IDENTITY properties.</span></span> <span data-ttu-id="b1648-131">这些属性在会话的状态表中发布。</span><span class="sxs-lookup"><span data-stu-id="b1648-131">These properties are published in the session's status table.</span></span> 
  
<span data-ttu-id="b1648-132">如果可能 **，QueryIdentity** 会从用PR_IDENTITY_ENTRYID 标记的状态行中返回 STATUS_PRIMARY_IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="b1648-132">If possible, **QueryIdentity** returns the value for the **PR_IDENTITY_ENTRYID** property from the status row tagged with STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="b1648-133">如果 **主PR_IDENTITY_ENTRYID** 行中缺少属性 **，QueryIdentity** 将返回使用该行中其他信息构建的一键式条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b1648-133">If the **PR_IDENTITY_ENTRYID** property is missing from the primary identity row, **QueryIdentity** returns a one-off entry identifier built with other information from that row.</span></span> 
  
<span data-ttu-id="b1648-134">如果STATUS_PRIMARY_IDENTITY表中的所有列都缺少 PR_RESOURCE_FLAG 标志 **，QueryIdentity** 将返回它找到的第一个条目标识符。 </span><span class="sxs-lookup"><span data-stu-id="b1648-134">If the STATUS_PRIMARY_IDENTITY flag is missing from all of the **PR_RESOURCE_FLAG** columns in the status table, **QueryIdentity** returns the first entry identifier that it finds.</span></span> <span data-ttu-id="b1648-135">如果没有要返回的适当条目标识符 **，QueryIdentity** 将成功返回警告MAPI_W_NO_SERVICE将  _lppEntryID_ 指向硬编码的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="b1648-135">When there is no appropriate entry identifier to return, **QueryIdentity** succeeds with the warning MAPI_W_NO_SERVICE and points  _lppEntryID_ to a hard-coded entry identifier.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="b1648-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b1648-136">Notes to callers</span></span>

<span data-ttu-id="b1648-137">可以调用 [IMsgServiceAdmin：：SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) 方法为邮件服务分配提供会话的主标识的任务。</span><span class="sxs-lookup"><span data-stu-id="b1648-137">You can call the [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) method to assign a message service the task of supplying the session's primary identity.</span></span> 
  
<span data-ttu-id="b1648-138">另一种检索主标识的方式是，在状态表中搜索行，PR_RESOURCE_FLAGS **列设置为** STATUS_PRIMARY_IDENTITY。</span><span class="sxs-lookup"><span data-stu-id="b1648-138">Another way to retrieve the primary identity is by searching the status table for the row with the **PR_RESOURCE_FLAGS** columns set to STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="b1648-139">有关检索标识信息的备用方法详细信息，请参阅 [状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="b1648-139">For more information about this alternate way of retrieving identity information, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  
<span data-ttu-id="b1648-140">使用 **QueryIdentity** 返回的主标识的条目标识符完成后，通过调用 [MAPIFreeBuffer](mapifreebuffer.md) 函数释放内存。</span><span class="sxs-lookup"><span data-stu-id="b1648-140">When you are finished using the entry identifier for the primary identity returned by **QueryIdentity**, free its memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="b1648-141">有关标识的一般详细信息，请参阅 [MAPI Primary Identity](mapi-primary-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="b1648-141">For more information about identity in general, see [MAPI Primary Identity](mapi-primary-identity.md).</span></span> 
  
<span data-ttu-id="b1648-142">有关检索 MAPI 会话标识的信息，请参阅检索 [主标识和提供程序标识](retrieving-primary-and-provider-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="b1648-142">For more information about retrieving MAPI session identity, see [Retrieving Primary and Provider Identity](retrieving-primary-and-provider-identity.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="b1648-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="b1648-143">MFCMAPI reference</span></span>

<span data-ttu-id="b1648-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b1648-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="b1648-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="b1648-145">**File**</span></span>|<span data-ttu-id="b1648-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="b1648-146">**Function**</span></span>|<span data-ttu-id="b1648-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="b1648-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b1648-148">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="b1648-148">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="b1648-149">CMainDlg：：OnQueryIdentity</span><span class="sxs-lookup"><span data-stu-id="b1648-149">CMainDlg::OnQueryIdentity</span></span>  <br/> |<span data-ttu-id="b1648-150">MFCMAPI 使用 **IMAPISession：：QueryIdentity** 方法打开会话的主标识的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="b1648-150">MFCMAPI uses the **IMAPISession::QueryIdentity** method to open the address book entry for the primary identity of the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b1648-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1648-151">See also</span></span>



[<span data-ttu-id="b1648-152">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="b1648-152">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
  
[<span data-ttu-id="b1648-153">IMsgServiceAdmin::SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="b1648-153">IMsgServiceAdmin::SetPrimaryIdentity</span></span>](imsgserviceadmin-setprimaryidentity.md)
  
[<span data-ttu-id="b1648-154">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="b1648-154">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="b1648-155">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b1648-155">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="b1648-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="b1648-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="b1648-157">MAPI 主标识</span><span class="sxs-lookup"><span data-stu-id="b1648-157">MAPI Primary Identity</span></span>](mapi-primary-identity.md)
  
[<span data-ttu-id="b1648-158">检索主标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="b1648-158">Retrieving Primary and Provider Identity</span></span>](retrieving-primary-and-provider-identity.md)
  
[<span data-ttu-id="b1648-159">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="b1648-159">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)
  
[<span data-ttu-id="b1648-160">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="b1648-160">Status Table and Status Objects</span></span>](status-table-and-status-objects.md)

