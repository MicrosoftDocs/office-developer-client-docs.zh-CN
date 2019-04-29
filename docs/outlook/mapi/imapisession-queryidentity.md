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
# <a name="imapisessionqueryidentity"></a><span data-ttu-id="7fbf0-103">IMAPISession::QueryIdentity</span><span class="sxs-lookup"><span data-stu-id="7fbf0-103">IMAPISession::QueryIdentity</span></span>

  
  
<span data-ttu-id="7fbf0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7fbf0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7fbf0-105">返回为会话提供主要标识的对象的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-105">Returns the entry identifier of the object that provides the primary identity for the session.</span></span>
  
```cpp
HRESULT QueryIdentity(
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="7fbf0-106">参数</span><span class="sxs-lookup"><span data-stu-id="7fbf0-106">Parameters</span></span>

 <span data-ttu-id="7fbf0-107">_lpcbEntryID_</span><span class="sxs-lookup"><span data-stu-id="7fbf0-107">_lpcbEntryID_</span></span>
  
> <span data-ttu-id="7fbf0-108">排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-108">[out] A pointer to the byte count in the entry identifier pointed to by the  _lppEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="7fbf0-109">_lppEntryID_</span><span class="sxs-lookup"><span data-stu-id="7fbf0-109">_lppEntryID_</span></span>
  
> <span data-ttu-id="7fbf0-110">排除指向提供主要标识的对象的条目标识符的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-110">[out] A pointer to a pointer to the entry identifier of the object that provides the primary identity.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7fbf0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7fbf0-111">Return value</span></span>

<span data-ttu-id="7fbf0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fbf0-112">S_OK</span></span> 
  
> <span data-ttu-id="7fbf0-113">已成功返回主标识。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-113">The primary identity was successfully returned.</span></span>
    
<span data-ttu-id="7fbf0-114">MAPI_W_NO_SERVICE</span><span class="sxs-lookup"><span data-stu-id="7fbf0-114">MAPI_W_NO_SERVICE</span></span> 
  
> <span data-ttu-id="7fbf0-115">调用成功, 但没有会话的主标识。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-115">The call succeeded, but there is no primary identity for the session.</span></span> <span data-ttu-id="7fbf0-116">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-116">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="7fbf0-117">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-117">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="7fbf0-118">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-118">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7fbf0-119">说明</span><span class="sxs-lookup"><span data-stu-id="7fbf0-119">Remarks</span></span>

<span data-ttu-id="7fbf0-120">**IMAPISession:: QueryIdentity**方法检索当前会话的主标识, 并通过_lppEntryID_参数返回值。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-120">The **IMAPISession::QueryIdentity** method retrieves the primary identity for the current session and returns the value through the  _lppEntryID_ parameter.</span></span> <span data-ttu-id="7fbf0-121">主要标识是一个对象 (通常是邮件用户), 代表会话的用户。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-121">The primary identity is an object, typically a messaging user, that represents the user of a session.</span></span>  <span data-ttu-id="7fbf0-122">_lppEntryID_返回[IMailUser](imailuserimapiprop.md)对象的主标识, 该标识也存储为[PidTagEntryID](pidtagentryid-canonical-property.md)属性。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-122">_lppEntryID_ returns the primary identity for an [IMailUser](imailuserimapiprop.md) object, which is also stored as the [PidTagEntryID](pidtagentryid-canonical-property.md) property.</span></span> <span data-ttu-id="7fbf0-123">您可以使用_lppEntryID_中返回的值, 通过[IMAPISession:: OpenEntry](imapisession-openentry.md)打开**IMailUser**对象。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-123">You can use the value returned in  _lppEntryID_ to open an **IMailUser** object using [IMAPISession::OpenEntry](imapisession-openentry.md).</span></span>
  
<span data-ttu-id="7fbf0-124">虽然多个邮件服务中的许多服务提供商可以为会话提供主要标识, 但 MAPI 指定了单个服务提供商。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-124">Although many service providers in multiple message services can provide the primary identity for a session, MAPI designates a single service provider.</span></span> <span data-ttu-id="7fbf0-125">提供主标识的服务提供程序将设置以下各项:</span><span class="sxs-lookup"><span data-stu-id="7fbf0-125">The service provider that supplies the primary identity sets the following items:</span></span>
  
- <span data-ttu-id="7fbf0-126">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中的 STATUS_PRIMARY_IDENTITY 标志。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-126">The STATUS_PRIMARY_IDENTITY flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="7fbf0-127">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-127">The **PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="7fbf0-128">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-128">The **PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="7fbf0-129">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-129">The **PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md)) property.</span></span>
    
<span data-ttu-id="7fbf0-130">如果提供主标识的服务提供商属于某个邮件服务, 则邮件服务中的其他服务提供商也会设置 PR_IDENTITY 属性。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-130">If the service provider that supplies the primary identity belongs to a message service, the other service providers in the message service also set the PR_IDENTITY properties.</span></span> <span data-ttu-id="7fbf0-131">这些属性在会话的状态表中发布。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-131">These properties are published in the session's status table.</span></span> 
  
<span data-ttu-id="7fbf0-132">如果可能, **QueryIdentity**将从使用 STATUS_PRIMARY_IDENTITY 标记的状态行返回**PR_IDENTITY_ENTRYID**属性的值。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-132">If possible, **QueryIdentity** returns the value for the **PR_IDENTITY_ENTRYID** property from the status row tagged with STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="7fbf0-133">如果主标识行中缺少**PR_IDENTITY_ENTRYID**属性, 则**QueryIdentity**将返回使用该行中的其他信息生成的一次性条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-133">If the **PR_IDENTITY_ENTRYID** property is missing from the primary identity row, **QueryIdentity** returns a one-off entry identifier built with other information from that row.</span></span> 
  
<span data-ttu-id="7fbf0-134">如果状态表中的所有**PR_RESOURCE_FLAG**列中缺少 STATUS_PRIMARY_IDENTITY 标志, 则**QueryIdentity**将返回找到的第一个条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-134">If the STATUS_PRIMARY_IDENTITY flag is missing from all of the **PR_RESOURCE_FLAG** columns in the status table, **QueryIdentity** returns the first entry identifier that it finds.</span></span> <span data-ttu-id="7fbf0-135">当没有合适的条目标识符返回时, **QueryIdentity**将成功并将警告 MAPI_W_NO_SERVICE, 并将_lppEntryID_指向硬编码的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-135">When there is no appropriate entry identifier to return, **QueryIdentity** succeeds with the warning MAPI_W_NO_SERVICE and points  _lppEntryID_ to a hard-coded entry identifier.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="7fbf0-136">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="7fbf0-136">Notes to callers</span></span>

<span data-ttu-id="7fbf0-137">您可以调用[IMsgServiceAdmin:: SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md)方法将邮件服务分配给提供会话的主要标识的任务。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-137">You can call the [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md) method to assign a message service the task of supplying the session's primary identity.</span></span> 
  
<span data-ttu-id="7fbf0-138">检索主标识的另一种方法是, 在状态表中搜索**PR_RESOURCE_FLAGS**列设置为 STATUS_PRIMARY_IDENTITY 的行。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-138">Another way to retrieve the primary identity is by searching the status table for the row with the **PR_RESOURCE_FLAGS** columns set to STATUS_PRIMARY_IDENTITY.</span></span> <span data-ttu-id="7fbf0-139">有关检索标识信息的其他方法的详细信息, 请参阅[状态表和状态对象](status-table-and-status-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-139">For more information about this alternate way of retrieving identity information, see [Status Table and Status Objects](status-table-and-status-objects.md).</span></span>
  
<span data-ttu-id="7fbf0-140">使用**QueryIdentity**返回的主标识的条目标识符后, 通过调用[MAPIFreeBuffer](mapifreebuffer.md)函数释放其内存。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-140">When you are finished using the entry identifier for the primary identity returned by **QueryIdentity**, free its memory by calling the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> 
  
<span data-ttu-id="7fbf0-141">有关标识一般的详细信息, 请参阅[MAPI 主标识](mapi-primary-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-141">For more information about identity in general, see [MAPI Primary Identity](mapi-primary-identity.md).</span></span> 
  
<span data-ttu-id="7fbf0-142">有关检索 MAPI 会话标识的详细信息, 请参阅[检索主标识和提供程序标识](retrieving-primary-and-provider-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-142">For more information about retrieving MAPI session identity, see [Retrieving Primary and Provider Identity](retrieving-primary-and-provider-identity.md).</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="7fbf0-143">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="7fbf0-143">MFCMAPI reference</span></span>

<span data-ttu-id="7fbf0-144">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-144">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="7fbf0-145">**文件**</span><span class="sxs-lookup"><span data-stu-id="7fbf0-145">**File**</span></span>|<span data-ttu-id="7fbf0-146">**函数**</span><span class="sxs-lookup"><span data-stu-id="7fbf0-146">**Function**</span></span>|<span data-ttu-id="7fbf0-147">**备注**</span><span class="sxs-lookup"><span data-stu-id="7fbf0-147">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7fbf0-148">MainDlg</span><span class="sxs-lookup"><span data-stu-id="7fbf0-148">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="7fbf0-149">CMainDlg:: OnQueryIdentity</span><span class="sxs-lookup"><span data-stu-id="7fbf0-149">CMainDlg::OnQueryIdentity</span></span>  <br/> |<span data-ttu-id="7fbf0-150">MFCMAPI 使用**IMAPISession:: QueryIdentity**方法打开会话主要标识的通讯簿条目。</span><span class="sxs-lookup"><span data-stu-id="7fbf0-150">MFCMAPI uses the **IMAPISession::QueryIdentity** method to open the address book entry for the primary identity of the session.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7fbf0-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fbf0-151">See also</span></span>



[<span data-ttu-id="7fbf0-152">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="7fbf0-152">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
  
[<span data-ttu-id="7fbf0-153">IMsgServiceAdmin::SetPrimaryIdentity</span><span class="sxs-lookup"><span data-stu-id="7fbf0-153">IMsgServiceAdmin::SetPrimaryIdentity</span></span>](imsgserviceadmin-setprimaryidentity.md)
  
[<span data-ttu-id="7fbf0-154">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="7fbf0-154">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="7fbf0-155">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7fbf0-155">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="7fbf0-156">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="7fbf0-156">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
  
[<span data-ttu-id="7fbf0-157">MAPI 主标识</span><span class="sxs-lookup"><span data-stu-id="7fbf0-157">MAPI Primary Identity</span></span>](mapi-primary-identity.md)
  
[<span data-ttu-id="7fbf0-158">检索主标识和提供程序标识</span><span class="sxs-lookup"><span data-stu-id="7fbf0-158">Retrieving Primary and Provider Identity</span></span>](retrieving-primary-and-provider-identity.md)
  
[<span data-ttu-id="7fbf0-159">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="7fbf0-159">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)
  
[<span data-ttu-id="7fbf0-160">状态表和状态对象</span><span class="sxs-lookup"><span data-stu-id="7fbf0-160">Status Table and Status Objects</span></span>](status-table-and-status-objects.md)

