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
# <a name="imapisessionsetdefaultstore"></a><span data-ttu-id="9c62a-103">IMAPISession::SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="9c62a-103">IMAPISession::SetDefaultStore</span></span>

  
  
<span data-ttu-id="9c62a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9c62a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9c62a-105">将邮件存储建立为会话的默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-105">Establishes a message store as the default message store for the session.</span></span>
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="9c62a-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c62a-106">Parameters</span></span>

 <span data-ttu-id="9c62a-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="9c62a-107">_ulFlags_</span></span>
  
> <span data-ttu-id="9c62a-108">[in]控制默认邮件存储设置的位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="9c62a-108">[in] A bitmask of flags that controls the setting of the default message store.</span></span> <span data-ttu-id="9c62a-109">这些标志相互排斥;只能设置以下标志之一：</span><span class="sxs-lookup"><span data-stu-id="9c62a-109">These flags are mutually exclusive; only one of the following flags can be set:</span></span>
    
<span data-ttu-id="9c62a-110">MAPI_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="9c62a-110">MAPI_DEFAULT_STORE</span></span>
  
> <span data-ttu-id="9c62a-111">建立消息存储作为会话默认值。</span><span class="sxs-lookup"><span data-stu-id="9c62a-111">Establishes the message store as the session default.</span></span> <span data-ttu-id="9c62a-112">更新邮件存储的状态表行，STATUS_DEFAULT_STORE [PidTagResourceFlags PR_RESOURCE_FLAGS (PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 标记。 </span><span class="sxs-lookup"><span data-stu-id="9c62a-112">Updates the message store's status table row by setting the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) column.</span></span>
    
<span data-ttu-id="9c62a-113">MAPI_PRIMARY_STORE</span><span class="sxs-lookup"><span data-stu-id="9c62a-113">MAPI_PRIMARY_STORE</span></span>
  
> <span data-ttu-id="9c62a-114">将邮件存储建立为登录时所使用的存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-114">Establishes the message store as the store to be used at logon.</span></span> <span data-ttu-id="9c62a-115">如果邮件存储不是默认存储，客户端应设置为默认存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-115">If the message store is not the default store, clients should make it the default.</span></span> <span data-ttu-id="9c62a-116">通过设置"邮件存储"列中的"STATUS_PRIMARY_STORE"标记来更新 **PR_RESOURCE_FLAGS表行** 。</span><span class="sxs-lookup"><span data-stu-id="9c62a-116">Updates the message store's status table row by setting the STATUS_PRIMARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="9c62a-117">MAPI_SECONDARY_STORE</span><span class="sxs-lookup"><span data-stu-id="9c62a-117">MAPI_SECONDARY_STORE</span></span>
  
> <span data-ttu-id="9c62a-118">建立邮件存储作为在主邮件存储不可用时在登录时所使用的存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-118">Establishes the message store as the store to be used at logon if the primary message store is not available.</span></span> <span data-ttu-id="9c62a-119">如果客户端无法打开主存储，它应打开辅助存储，并设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="9c62a-119">If a client cannot open the primary store, it should open the secondary store and set it as the default.</span></span> <span data-ttu-id="9c62a-120">通过设置"邮件存储"列中的"STATUS_SECONDARY_STORE"标记来更新邮件 **PR_RESOURCE_FLAGS行。**</span><span class="sxs-lookup"><span data-stu-id="9c62a-120">Updates the message store's status table row by setting the STATUS_SECONDARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="9c62a-121">MAPI_SIMPLE_STORE_PERMANENT</span><span class="sxs-lookup"><span data-stu-id="9c62a-121">MAPI_SIMPLE_STORE_PERMANENT</span></span>
  
> <span data-ttu-id="9c62a-122">在STATUS_SIMPLE_STORE表行、邮件存储表行和会话 **配置文件** PR_RESOURCE_FLAGS邮件存储的 PR_RESOURCE_FLAGS 属性中设置该标志。</span><span class="sxs-lookup"><span data-stu-id="9c62a-122">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row, message store table row, and in the session profile.</span></span> 
    
<span data-ttu-id="9c62a-123">MAPI_SIMPLE_STORE_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="9c62a-123">MAPI_SIMPLE_STORE_TEMPORARY</span></span>
  
> <span data-ttu-id="9c62a-124">在STATUS_SIMPLE_STORE表行和邮件存储表PR_RESOURCE_FLAGS中设置邮件存储的 PR_RESOURCE_FLAGS 标记。</span><span class="sxs-lookup"><span data-stu-id="9c62a-124">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row and message store table row.</span></span> <span data-ttu-id="9c62a-125">不修改配置文件。</span><span class="sxs-lookup"><span data-stu-id="9c62a-125">The profile is not modified.</span></span> 
    
 <span data-ttu-id="9c62a-126">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="9c62a-126">_cbEntryID_</span></span>
  
> <span data-ttu-id="9c62a-127">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="9c62a-127">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="9c62a-128">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="9c62a-128">_lpEntryID_</span></span>
  
> <span data-ttu-id="9c62a-129">[in]指向默认的邮件存储的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="9c62a-129">[in] A pointer to the entry identifier of the message store that is intended as the default.</span></span> <span data-ttu-id="9c62a-130">如果客户端在  _lpEntryID_ 中传递 NULL，则不选择任何邮件存储作为默认值。</span><span class="sxs-lookup"><span data-stu-id="9c62a-130">If a client passes NULL in  _lpEntryID_, no message store is selected as the default.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9c62a-131">返回值</span><span class="sxs-lookup"><span data-stu-id="9c62a-131">Return value</span></span>

<span data-ttu-id="9c62a-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c62a-132">S_OK</span></span> 
  
> <span data-ttu-id="9c62a-133">调用成功并返回预期值。</span><span class="sxs-lookup"><span data-stu-id="9c62a-133">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9c62a-134">备注</span><span class="sxs-lookup"><span data-stu-id="9c62a-134">Remarks</span></span>

<span data-ttu-id="9c62a-135">**IMAPISession：：SetDefaultStore** 方法将邮件存储建立为以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="9c62a-135">The **IMAPISession::SetDefaultStore** method establishes a message store as one of the following:</span></span> 
  
- <span data-ttu-id="9c62a-136">会话的默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-136">The default message store for the session.</span></span>
    
- <span data-ttu-id="9c62a-137">会话的主邮件存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-137">The primary message store for the session.</span></span>
    
- <span data-ttu-id="9c62a-138">会话的辅助邮件存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-138">The secondary message store for the session.</span></span>
    
<span data-ttu-id="9c62a-139">若要将邮件存储建立为默认存储，邮件存储必须在其 **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="9c62a-139">To establish a message store as the default, the message store must have the following flags set in its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
  
- <span data-ttu-id="9c62a-140">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="9c62a-140">STORE_SUBMIT_OK</span></span>
    
- <span data-ttu-id="9c62a-141">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="9c62a-141">STORE_CREATE_OK</span></span>
    
- <span data-ttu-id="9c62a-142">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="9c62a-142">STORE_MODIFY_OK</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="9c62a-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="9c62a-143">Notes to callers</span></span>

<span data-ttu-id="9c62a-144">您可以通过检索状态表，并搜索 STATUS_DEFAULT_STORE 列中的 STATUS_DEFAULT_STORE 标志的设置来确定 **会话的默认PR_RESOURCE_FLAGS** 存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-144">You can determine the default message store for the session by retrieving the status table and searching for the setting of the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> <span data-ttu-id="9c62a-145">具有此设置的行表示指定为会话默认值的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-145">The row that has this setting represents the message store that is designated as the session default.</span></span> 
  
<span data-ttu-id="9c62a-146">当设置 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志时，MAPI 将更新配置文件、邮件存储表和状态表。</span><span class="sxs-lookup"><span data-stu-id="9c62a-146">When either the MAPI_DEFAULT_STORE or the MAPI_SIMPLE_STORE_PERMANENT flag is set, MAPI updates the profile, message store table, and status table.</span></span> 
  
<span data-ttu-id="9c62a-147">只要对邮件存储默认设置进行了更改，就会生成以下通知：</span><span class="sxs-lookup"><span data-stu-id="9c62a-147">Whenever a change is made to the message store default setting, the following notifications are generated:</span></span>
  
- <span data-ttu-id="9c62a-148">为邮件存储和状态表中的每个受影响的行发出 **fnevTableModified** 事件通知。</span><span class="sxs-lookup"><span data-stu-id="9c62a-148">An **fnevTableModified** event notification is issued for each affected row in both the message store and status table.</span></span> 
    
- <span data-ttu-id="9c62a-149">向 MAPI 后台处理程序发出内部通知。</span><span class="sxs-lookup"><span data-stu-id="9c62a-149">An internal notification is issued to the MAPI spooler.</span></span> <span data-ttu-id="9c62a-150">已完成进行中的操作，无需更改;涉及默认邮件存储的新操作（如邮件下载）将针对新的默认存储进行处理。</span><span class="sxs-lookup"><span data-stu-id="9c62a-150">Operations already in progress are completed without change; new operations that involve the default message store, such as message downloading, are processed for the new default store.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="9c62a-151">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="9c62a-151">MFCMAPI reference</span></span>

<span data-ttu-id="9c62a-152">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9c62a-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9c62a-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="9c62a-153">**File**</span></span>|<span data-ttu-id="9c62a-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="9c62a-154">**Function**</span></span>|<span data-ttu-id="9c62a-155">**备注**</span><span class="sxs-lookup"><span data-stu-id="9c62a-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c62a-156">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="9c62a-156">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="9c62a-157">CMainDlg：：OnSetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="9c62a-157">CMainDlg::OnSetDefaultStore</span></span>  <br/> |<span data-ttu-id="9c62a-158">MFCMAPI 使用 **IMAPISession：：SetDefaultStore** 方法将所选存储设置为默认存储。</span><span class="sxs-lookup"><span data-stu-id="9c62a-158">MFCMAPI uses the **IMAPISession::SetDefaultStore** method to set the selected store as the default store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9c62a-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c62a-159">See also</span></span>



[<span data-ttu-id="9c62a-160">PidTagResourceFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c62a-160">PidTagResourceFlags Canonical Property</span></span>](pidtagresourceflags-canonical-property.md)
  
[<span data-ttu-id="9c62a-161">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c62a-161">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)
  
[<span data-ttu-id="9c62a-162">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="9c62a-162">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="9c62a-163">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9c62a-163">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="9c62a-164">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="9c62a-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

