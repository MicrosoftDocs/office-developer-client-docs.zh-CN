---
title: IMAPISessionSetDefaultStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.SetDefaultStore
api_type:
- COM
ms.assetid: 456c207f-5d41-4d0c-94b6-0c58893a6bed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f4ff2a3897306ebe4f77c08630782c5f2c7d5d3d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426105"
---
# <a name="imapisessionsetdefaultstore"></a><span data-ttu-id="ceb96-103">IMAPISession::SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="ceb96-103">IMAPISession::SetDefaultStore</span></span>

  
  
<span data-ttu-id="ceb96-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ceb96-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ceb96-105">将邮件存储区建立为会话的默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-105">Establishes a message store as the default message store for the session.</span></span>
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="ceb96-106">参数</span><span class="sxs-lookup"><span data-stu-id="ceb96-106">Parameters</span></span>

 <span data-ttu-id="ceb96-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ceb96-107">_ulFlags_</span></span>
  
> <span data-ttu-id="ceb96-108">实时用于控制默认邮件存储的设置的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="ceb96-108">[in] A bitmask of flags that controls the setting of the default message store.</span></span> <span data-ttu-id="ceb96-109">这些标志是互斥的;只能设置下列标志之一:</span><span class="sxs-lookup"><span data-stu-id="ceb96-109">These flags are mutually exclusive; only one of the following flags can be set:</span></span>
    
<span data-ttu-id="ceb96-110">MAPI_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="ceb96-110">MAPI_DEFAULT_STORE</span></span>
  
> <span data-ttu-id="ceb96-111">将邮件存储区建立为会话默认值。</span><span class="sxs-lookup"><span data-stu-id="ceb96-111">Establishes the message store as the session default.</span></span> <span data-ttu-id="ceb96-112">通过在**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 列中设置 STATUS_DEFAULT_STORE 标志来更新邮件存储区的状态表行。</span><span class="sxs-lookup"><span data-stu-id="ceb96-112">Updates the message store's status table row by setting the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) column.</span></span>
    
<span data-ttu-id="ceb96-113">MAPI_PRIMARY_STORE</span><span class="sxs-lookup"><span data-stu-id="ceb96-113">MAPI_PRIMARY_STORE</span></span>
  
> <span data-ttu-id="ceb96-114">建立要在登录时使用的存储区的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-114">Establishes the message store as the store to be used at logon.</span></span> <span data-ttu-id="ceb96-115">如果邮件存储不是默认存储, 客户端应将其设为默认值。</span><span class="sxs-lookup"><span data-stu-id="ceb96-115">If the message store is not the default store, clients should make it the default.</span></span> <span data-ttu-id="ceb96-116">通过在**PR_RESOURCE_FLAGS**列中设置 STATUS_PRIMARY_STORE 标志来更新邮件存储区的状态表行。</span><span class="sxs-lookup"><span data-stu-id="ceb96-116">Updates the message store's status table row by setting the STATUS_PRIMARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="ceb96-117">MAPI_SECONDARY_STORE</span><span class="sxs-lookup"><span data-stu-id="ceb96-117">MAPI_SECONDARY_STORE</span></span>
  
> <span data-ttu-id="ceb96-118">将邮件存储区建立为当主邮件存储不可用时在登录时使用的存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-118">Establishes the message store as the store to be used at logon if the primary message store is not available.</span></span> <span data-ttu-id="ceb96-119">如果客户端无法打开主存储, 则应打开辅助存储并将其设置为默认存储。</span><span class="sxs-lookup"><span data-stu-id="ceb96-119">If a client cannot open the primary store, it should open the secondary store and set it as the default.</span></span> <span data-ttu-id="ceb96-120">通过在**PR_RESOURCE_FLAGS**列中设置 STATUS_SECONDARY_STORE 标志来更新邮件存储区的状态表行。</span><span class="sxs-lookup"><span data-stu-id="ceb96-120">Updates the message store's status table row by setting the STATUS_SECONDARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="ceb96-121">MAPI_SIMPLE_STORE_PERMANENT</span><span class="sxs-lookup"><span data-stu-id="ceb96-121">MAPI_SIMPLE_STORE_PERMANENT</span></span>
  
> <span data-ttu-id="ceb96-122">在邮件存储区的**PR_RESOURCE_FLAGS**属性中设置其状态表行、邮件存储表行和会话配置文件中的 STATUS_SIMPLE_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="ceb96-122">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row, message store table row, and in the session profile.</span></span> 
    
<span data-ttu-id="ceb96-123">MAPI_SIMPLE_STORE_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="ceb96-123">MAPI_SIMPLE_STORE_TEMPORARY</span></span>
  
> <span data-ttu-id="ceb96-124">在邮件存储的**PR_RESOURCE_FLAGS**属性中的状态表格行和邮件存储表行中设置 STATUS_SIMPLE_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="ceb96-124">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row and message store table row.</span></span> <span data-ttu-id="ceb96-125">不修改配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb96-125">The profile is not modified.</span></span> 
    
 <span data-ttu-id="ceb96-126">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="ceb96-126">_cbEntryID_</span></span>
  
> <span data-ttu-id="ceb96-127">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="ceb96-127">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="ceb96-128">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="ceb96-128">_lpEntryID_</span></span>
  
> <span data-ttu-id="ceb96-129">实时指向邮件存储的条目标识符的指针, 该邮件存储将作为默认值。</span><span class="sxs-lookup"><span data-stu-id="ceb96-129">[in] A pointer to the entry identifier of the message store that is intended as the default.</span></span> <span data-ttu-id="ceb96-130">如果客户端在_lpEntryID_中传递了 NULL, 则不会选择任何邮件存储区作为默认值。</span><span class="sxs-lookup"><span data-stu-id="ceb96-130">If a client passes NULL in  _lpEntryID_, no message store is selected as the default.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ceb96-131">返回值</span><span class="sxs-lookup"><span data-stu-id="ceb96-131">Return value</span></span>

<span data-ttu-id="ceb96-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="ceb96-132">S_OK</span></span> 
  
> <span data-ttu-id="ceb96-133">调用成功, 并返回了所需的一个或一些值。</span><span class="sxs-lookup"><span data-stu-id="ceb96-133">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ceb96-134">说明</span><span class="sxs-lookup"><span data-stu-id="ceb96-134">Remarks</span></span>

<span data-ttu-id="ceb96-135">**IMAPISession:: SetDefaultStore**方法将邮件存储区建立为以下内容之一:</span><span class="sxs-lookup"><span data-stu-id="ceb96-135">The **IMAPISession::SetDefaultStore** method establishes a message store as one of the following:</span></span> 
  
- <span data-ttu-id="ceb96-136">会话的默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-136">The default message store for the session.</span></span>
    
- <span data-ttu-id="ceb96-137">会话的主邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-137">The primary message store for the session.</span></span>
    
- <span data-ttu-id="ceb96-138">会话的辅助邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-138">The secondary message store for the session.</span></span>
    
<span data-ttu-id="ceb96-139">若要将邮件存储区设置为默认值, 邮件存储区的**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中必须设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="ceb96-139">To establish a message store as the default, the message store must have the following flags set in its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
  
- <span data-ttu-id="ceb96-140">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="ceb96-140">STORE_SUBMIT_OK</span></span>
    
- <span data-ttu-id="ceb96-141">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="ceb96-141">STORE_CREATE_OK</span></span>
    
- <span data-ttu-id="ceb96-142">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="ceb96-142">STORE_MODIFY_OK</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="ceb96-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="ceb96-143">Notes to callers</span></span>

<span data-ttu-id="ceb96-144">您可以通过检索状态表并在**PR_RESOURCE_FLAGS**列中搜索 STATUS_DEFAULT_STORE 标志的设置来确定会话的默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="ceb96-144">You can determine the default message store for the session by retrieving the status table and searching for the setting of the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> <span data-ttu-id="ceb96-145">具有此设置的行表示指定为会话默认值的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-145">The row that has this setting represents the message store that is designated as the session default.</span></span> 
  
<span data-ttu-id="ceb96-146">如果设置了 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志, MAPI 将更新配置文件、邮件存储表和状态表。</span><span class="sxs-lookup"><span data-stu-id="ceb96-146">When either the MAPI_DEFAULT_STORE or the MAPI_SIMPLE_STORE_PERMANENT flag is set, MAPI updates the profile, message store table, and status table.</span></span> 
  
<span data-ttu-id="ceb96-147">每当对邮件存储库默认设置进行更改时, 都会生成以下通知:</span><span class="sxs-lookup"><span data-stu-id="ceb96-147">Whenever a change is made to the message store default setting, the following notifications are generated:</span></span>
  
- <span data-ttu-id="ceb96-148">对于邮件存储和状态表中的每个受影响的行, 都会发出一个**fnevTableModified**事件通知。</span><span class="sxs-lookup"><span data-stu-id="ceb96-148">An **fnevTableModified** event notification is issued for each affected row in both the message store and status table.</span></span> 
    
- <span data-ttu-id="ceb96-149">向 MAPI 后台处理程序发出内部通知。</span><span class="sxs-lookup"><span data-stu-id="ceb96-149">An internal notification is issued to the MAPI spooler.</span></span> <span data-ttu-id="ceb96-150">已在进行中的操作已完成, 无需更改;将为新的默认存储区处理涉及默认邮件存储 (如邮件下载) 的新操作。</span><span class="sxs-lookup"><span data-stu-id="ceb96-150">Operations already in progress are completed without change; new operations that involve the default message store, such as message downloading, are processed for the new default store.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="ceb96-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ceb96-151">MFCMAPI reference</span></span>

<span data-ttu-id="ceb96-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ceb96-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ceb96-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="ceb96-153">**File**</span></span>|<span data-ttu-id="ceb96-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="ceb96-154">**Function**</span></span>|<span data-ttu-id="ceb96-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="ceb96-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ceb96-156">MainDlg</span><span class="sxs-lookup"><span data-stu-id="ceb96-156">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="ceb96-157">CMainDlg:: OnSetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="ceb96-157">CMainDlg::OnSetDefaultStore</span></span>  <br/> |<span data-ttu-id="ceb96-158">MFCMAPI 使用**IMAPISession:: SetDefaultStore**方法将选定存储区设置为默认存储区。</span><span class="sxs-lookup"><span data-stu-id="ceb96-158">MFCMAPI uses the **IMAPISession::SetDefaultStore** method to set the selected store as the default store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ceb96-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ceb96-159">See also</span></span>



[<span data-ttu-id="ceb96-160">PidTagResourceFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="ceb96-160">PidTagResourceFlags Canonical Property</span></span>](pidtagresourceflags-canonical-property.md)
  
[<span data-ttu-id="ceb96-161">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="ceb96-161">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)
  
[<span data-ttu-id="ceb96-162">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="ceb96-162">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="ceb96-163">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ceb96-163">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="ceb96-164">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="ceb96-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

