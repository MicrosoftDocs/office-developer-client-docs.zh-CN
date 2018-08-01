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
ms.openlocfilehash: c8f05707d63f922c9ce22e6e520c6c57e686f884
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775574"
---
# <a name="imapisessionqueryidentity"></a><span data-ttu-id="1188f-103">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="1188f-103">IMAPISession::QueryIdentity</span></span>

  
  
<span data-ttu-id="1188f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1188f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1188f-105">返回会话中提供的主要标识的对象的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1188f-105">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="1188f-106">参数</span><span class="sxs-lookup"><span data-stu-id="1188f-106">Parameters</span></span>

 <span data-ttu-id="1188f-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="1188f-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="1188f-108">[输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。</span><span class="sxs-lookup"><span data-stu-id="1188f-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="1188f-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="1188f-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="1188f-110">[输出]指向提供的主要标识的对象的项标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="1188f-110">[out] A pointer to a pointer to the entry identifier of the object that provides the primary identity.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1188f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1188f-111">Return value</span></span>

<span data-ttu-id="1188f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1188f-112">S_OK</span></span> 
  
> <span data-ttu-id="1188f-113">已成功返回的主标识。</span><span class="sxs-lookup"><span data-stu-id="1188f-113">The primary identity was successfully returned.</span></span>
    
<span data-ttu-id="1188f-114">MAPI_W_NO_SERVICE</span><span class="sxs-lookup"><span data-stu-id="1188f-114">MAPI_W_NO_SERVICE</span></span> 
  
> <span data-ttu-id="1188f-115">呼叫成功，但没有任何主标识会话。</span><span class="sxs-lookup"><span data-stu-id="1188f-115">The call succeeded, but there is no primary identity for the session.</span></span> <span data-ttu-id="1188f-116">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="1188f-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="1188f-117">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="1188f-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="1188f-118">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="1188f-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1188f-119">说明</span><span class="sxs-lookup"><span data-stu-id="1188f-119">Remarks</span></span>

<span data-ttu-id="1188f-120">**IMAPISession::QueryIdentity**方法检索当前会话的主标识，并返回通过_lppEntryID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="1188f-120">The **IMAPISession::QueryIdentity** method retrieves the primary identity for the current session and returns the value through the  _lppEntryID_ parameter.</span></span> <span data-ttu-id="1188f-121">主 identity 是一个对象，通常消息，表示用户会话的用户。</span><span class="sxs-lookup"><span data-stu-id="1188f-121">The primary identity is an object, typically a messaging user, that represents the user of a session.</span></span>  <span data-ttu-id="1188f-122">_lppEntryID_返回[IMailUser](imailuserimapiprop.md)对象，它还存储为[PidTagEntryID](pidtagentryid-canonical-property.md)属性的主标识。</span><span class="sxs-lookup"><span data-stu-id="1188f-122">_lppEntryID_ returns the primary identity for an [IMailUser](imailuserimapiprop.md) object, which is also stored as the [PidTagEntryID](pidtagentryid-canonical-property.md) property.</span></span> <span data-ttu-id="1188f-123">您可以使用_lppEntryID_中返回的值打开使用[IMAPISession::OpenEntry](imapisession-openentry.md) **IMailUser**对象。</span><span class="sxs-lookup"><span data-stu-id="1188f-123">You can use the value returned in  _lppEntryID_ to open an **IMailUser** object using [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span>
  
<span data-ttu-id="1188f-124">尽管在多个邮件服务中的许多服务提供商可以会话提供的主要标识，MAPI 指定单个服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1188f-124">Although many service providers in multiple message services can provide the primary identity for a session, MAPI designates a single service provider.</span></span> <span data-ttu-id="1188f-125">提供的主要标识服务提供商设置以下各项：</span><span class="sxs-lookup"><span data-stu-id="1188f-125">The service provider that supplies the primary identity sets the following items:</span></span>
  
- <span data-ttu-id="1188f-126">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中 STATUS_PRIMARY_IDENTITY 标志。</span><span class="sxs-lookup"><span data-stu-id="1188f-126">The STATUS_PRIMARY_IDENTITY flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="1188f-127">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="1188f-127">The **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="1188f-128">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="1188f-128">The **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="1188f-129">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="1188f-129">The **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="1188f-130">如果服务提供商提供的主要标识属于邮件服务，消息服务中的其他服务提供商还设置 PR_IDENTITY 属性。</span><span class="sxs-lookup"><span data-stu-id="1188f-130">If the service provider that supplies the primary identity belongs to a message service, the other service providers in the message service also set the PR_IDENTITY properties.</span></span> <span data-ttu-id="1188f-131">在会话的状态表中发布这些属性。</span><span class="sxs-lookup"><span data-stu-id="1188f-131">These properties are published in the session's status table.</span></span> 
  
<span data-ttu-id="1188f-132">如果可能， **QueryIdentity**从 STATUS_PRIMARY_IDENTITY 标记的状态行返回**PR_IDENTITY_ENTRYID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="1188f-132">If possible, **QueryIdentity** returns the value for the **PR_IDENTITY_ENTRYID** property from the status row tagged with STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="1188f-133">如果主身份行中缺少**PR_IDENTITY_ENTRYID**属性， **QueryIdentity**返回构建与该行中的其他信息的一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1188f-133">If the **PR_IDENTITY_ENTRYID** property is missing from the primary identity row, **QueryIdentity** returns a one-off entry identifier built with other information from that row.</span></span> 
  
<span data-ttu-id="1188f-134">如果中的所有**PR_RESOURCE_FLAG**列在状态表中缺少 STATUS_PRIMARY_IDENTITY 标志，则**QueryIdentity**返回找到的第一个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1188f-134">If the STATUS_PRIMARY_IDENTITY flag is missing from all of the **PR_RESOURCE_FLAG** columns in the status table, **QueryIdentity** returns the first entry identifier that it finds.</span></span> <span data-ttu-id="1188f-135">当没有返回没有适当的项标识符时， **QueryIdentity**警告 MAPI_W_NO_SERVICE 成功，并_lppEntryID_指向的硬编码的项标识符。</span><span class="sxs-lookup"><span data-stu-id="1188f-135">When there is no appropriate entry identifier to return, **QueryIdentity** succeeds with the warning MAPI_W_NO_SERVICE and points  _lppEntryID_ to a hard-coded entry identifier.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="1188f-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="1188f-136">Notes to callers</span></span>

<span data-ttu-id="1188f-137">您可以调用[IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)方法提供会话的主标识的任务分配的消息服务。</span><span class="sxs-lookup"><span data-stu-id="1188f-137">You can call the [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) method to assign a message service the task of supplying the session's primary identity.</span></span> 
  
<span data-ttu-id="1188f-138">通过搜索行的状态表设置为 STATUS_PRIMARY_IDENTITY **PR_RESOURCE_FLAGS**列与另一种方法来检索主标识。</span><span class="sxs-lookup"><span data-stu-id="1188f-138">Another way to retrieve the primary identity is by searching the status table for the row with the **PR_RESOURCE_FLAGS** columns set to STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="1188f-139">有关此另一种方法检索标识信息的详细信息，请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="1188f-139">For more information about this alternate way of retrieving identity information, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  
<span data-ttu-id="1188f-140">当您完成使用主标识**QueryIdentity**返回的项标识符时，通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放其内存。</span><span class="sxs-lookup"><span data-stu-id="1188f-140">When you are finished using the entry identifier for the primary identity returned by **QueryIdentity**, free its memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="1188f-141">标识有关详细信息，请参阅[MAPI 主标识](mapi-primary-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="1188f-141">For more information about identity in general, see [MAPI Primary Identity](mapi-primary-identity.md).</span></span> 
  
<span data-ttu-id="1188f-142">有关检索 MAPI 会话标识的详细信息，请参阅[检索主和提供程序的标识](retrieving-primary-and-provider-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="1188f-142">For more information about retrieving MAPI session identity, see [Retrieving Primary and Provider Identity](retrieving-primary-and-provider-identity.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="1188f-143">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="1188f-143">MFCMAPI reference</span></span>

<span data-ttu-id="1188f-144">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="1188f-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="1188f-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="1188f-145">**File**</span></span>|<span data-ttu-id="1188f-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="1188f-146">**Function**</span></span>|<span data-ttu-id="1188f-147">**Comment**</span><span class="sxs-lookup"><span data-stu-id="1188f-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1188f-148">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="1188f-148">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="1188f-149">CMainDlg::OnQueryIdentity</span><span class="sxs-lookup"><span data-stu-id="1188f-149">CMainDlg::OnQueryIdentity</span></span>  <br/> |<span data-ttu-id="1188f-150">MFCMAPI 使用**IMAPISession::QueryIdentity**方法打开主标识会话的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="1188f-150">MFCMAPI uses the **IMAPISession::QueryIdentity** method to open the address book entry for the primary identity of the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1188f-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1188f-151">See also</span></span>



[<span data-ttu-id="1188f-152">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="1188f-152">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
  
[<span data-ttu-id="1188f-153">IMsgServiceAdmin::SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="1188f-153">IMsgServiceAdmin::SetPrimaryIdentity</span></span>](imsgserviceadmin-setprimaryidentity.md)
  
[<span data-ttu-id="1188f-154">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="1188f-154">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="1188f-155">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1188f-155">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="1188f-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="1188f-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="1188f-157">MAPI 主标识</span><span class="sxs-lookup"><span data-stu-id="1188f-157">MAPI Primary Identity</span></span>](mapi-primary-identity.md)
  
[<span data-ttu-id="1188f-158">检索主要标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="1188f-158">Retrieving Primary and Provider Identity</span></span>](retrieving-primary-and-provider-identity.md)
  
[<span data-ttu-id="1188f-159">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="1188f-159">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)
  
[<span data-ttu-id="1188f-160">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="1188f-160">Status Table and Status Objects</span></span>](status-table-and-status-objects.md)

