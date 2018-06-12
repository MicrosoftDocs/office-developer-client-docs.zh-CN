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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: e3c4125bf4fcf1881a0cba9b04a8bb6aa71f527d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775569"
---
# <a name="imapisessionsetdefaultstore"></a><span data-ttu-id="74bb6-103">IMAPISession::SetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="74bb6-103">IMAPISession::SetDefaultStore</span></span>

  
  
<span data-ttu-id="74bb6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="74bb6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="74bb6-105">建立会话，作为默认的邮件存储的消息存储。</span><span class="sxs-lookup"><span data-stu-id="74bb6-105">Establishes a message store as the default message store for the session.</span></span>
  
```cpp
HRESULT SetDefaultStore(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a><span data-ttu-id="74bb6-106">参数</span><span class="sxs-lookup"><span data-stu-id="74bb6-106">Parameters</span></span>

 <span data-ttu-id="74bb6-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="74bb6-107">_ulFlags_</span></span>
  
> <span data-ttu-id="74bb6-108">[in]位掩码的标志控制默认的邮件存储的设置的。</span><span class="sxs-lookup"><span data-stu-id="74bb6-108">[in] A bitmask of flags that controls the setting of the default message store.</span></span> <span data-ttu-id="74bb6-109">这些标志为相互排斥;可以设置以下标志的唯一之一：</span><span class="sxs-lookup"><span data-stu-id="74bb6-109">These flags are mutually exclusive; only one of the following flags can be set:</span></span>
    
<span data-ttu-id="74bb6-110">MAPI_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="74bb6-110">MAPI_DEFAULT_STORE</span></span>
  
> <span data-ttu-id="74bb6-111">为会话默认建立的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="74bb6-111">Establishes the message store as the session default.</span></span> <span data-ttu-id="74bb6-112">通过设置 STATUS_DEFAULT_STORE 标志**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 列中更新的消息存储状态表格行。</span><span class="sxs-lookup"><span data-stu-id="74bb6-112">Updates the message store's status table row by setting the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) column.</span></span>
    
<span data-ttu-id="74bb6-113">MAPI_PRIMARY_STORE</span><span class="sxs-lookup"><span data-stu-id="74bb6-113">MAPI_PRIMARY_STORE</span></span>
  
> <span data-ttu-id="74bb6-114">作为存储用于登录建立的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="74bb6-114">Establishes the message store as the store to be used at logon.</span></span> <span data-ttu-id="74bb6-115">如果消息存储不是默认存储，客户端应使其默认值。</span><span class="sxs-lookup"><span data-stu-id="74bb6-115">If the message store is not the default store, clients should make it the default.</span></span> <span data-ttu-id="74bb6-116">通过设置 STATUS_PRIMARY_STORE 标志**PR_RESOURCE_FLAGS**列中更新的消息存储状态表格行。</span><span class="sxs-lookup"><span data-stu-id="74bb6-116">Updates the message store's status table row by setting the STATUS_PRIMARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="74bb6-117">MAPI_SECONDARY_STORE</span><span class="sxs-lookup"><span data-stu-id="74bb6-117">MAPI_SECONDARY_STORE</span></span>
  
> <span data-ttu-id="74bb6-118">建立的邮件存储组作为存储用于登录时如果主消息存储不可用。</span><span class="sxs-lookup"><span data-stu-id="74bb6-118">Establishes the message store as the store to be used at logon if the primary message store is not available.</span></span> <span data-ttu-id="74bb6-119">如果客户端无法打开主存储区，它应打开辅助存储，并将其设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="74bb6-119">If a client cannot open the primary store, it should open the secondary store and set it as the default.</span></span> <span data-ttu-id="74bb6-120">通过设置 STATUS_SECONDARY_STORE 标志**PR_RESOURCE_FLAGS**列中更新的消息存储状态表格行。</span><span class="sxs-lookup"><span data-stu-id="74bb6-120">Updates the message store's status table row by setting the STATUS_SECONDARY_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> 
    
<span data-ttu-id="74bb6-121">MAPI_SIMPLE_STORE_PERMANENT</span><span class="sxs-lookup"><span data-stu-id="74bb6-121">MAPI_SIMPLE_STORE_PERMANENT</span></span>
  
> <span data-ttu-id="74bb6-122">消息存储表格行，其状态表格行和会话配置文件中的消息存储**PR_RESOURCE_FLAGS**属性中设置 STATUS_SIMPLE_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="74bb6-122">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row, message store table row, and in the session profile.</span></span> 
    
<span data-ttu-id="74bb6-123">MAPI_SIMPLE_STORE_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="74bb6-123">MAPI_SIMPLE_STORE_TEMPORARY</span></span>
  
> <span data-ttu-id="74bb6-124">其状态表行和消息存储表行中的消息存储**PR_RESOURCE_FLAGS**属性中设置 STATUS_SIMPLE_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="74bb6-124">Sets the STATUS_SIMPLE_STORE flag in the message store's **PR_RESOURCE_FLAGS** property in its status table row and message store table row.</span></span> <span data-ttu-id="74bb6-125">未修改配置文件。</span><span class="sxs-lookup"><span data-stu-id="74bb6-125">The profile is not modified.</span></span> 
    
 <span data-ttu-id="74bb6-126">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="74bb6-126">_cbEntryID_</span></span>
  
> <span data-ttu-id="74bb6-127">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="74bb6-127">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="74bb6-128">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="74bb6-128">_lpEntryID_</span></span>
  
> <span data-ttu-id="74bb6-129">[in]指向专为默认的消息存储的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="74bb6-129">[in] A pointer to the entry identifier of the message store that is intended as the default.</span></span> <span data-ttu-id="74bb6-130">如果客户端传入_lpEntryID_NULL，没有消息存储在为默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="74bb6-130">If a client passes NULL in  _lpEntryID_, no message store is selected as the default.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="74bb6-131">返回值</span><span class="sxs-lookup"><span data-stu-id="74bb6-131">Return value</span></span>

<span data-ttu-id="74bb6-132">S_OK</span><span class="sxs-lookup"><span data-stu-id="74bb6-132">S_OK</span></span> 
  
> <span data-ttu-id="74bb6-133">呼叫成功，并返回预期的值。</span><span class="sxs-lookup"><span data-stu-id="74bb6-133">The call succeeded and returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="74bb6-134">备注</span><span class="sxs-lookup"><span data-stu-id="74bb6-134">Remarks</span></span>

<span data-ttu-id="74bb6-135">**IMAPISession::SetDefaultStore**方法建立的消息存储为下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="74bb6-135">The **IMAPISession::SetDefaultStore** method establishes a message store as one of the following:</span></span> 
  
- <span data-ttu-id="74bb6-136">默认的邮件存储会话。</span><span class="sxs-lookup"><span data-stu-id="74bb6-136">The default message store for the session.</span></span>
    
- <span data-ttu-id="74bb6-137">用于会话的主邮件存储。</span><span class="sxs-lookup"><span data-stu-id="74bb6-137">The primary message store for the session.</span></span>
    
- <span data-ttu-id="74bb6-138">会话辅助消息存储。</span><span class="sxs-lookup"><span data-stu-id="74bb6-138">The secondary message store for the session.</span></span>
    
<span data-ttu-id="74bb6-139">要建立为默认的消息存储，消息存储库必须具有以下标志在其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中设置：</span><span class="sxs-lookup"><span data-stu-id="74bb6-139">To establish a message store as the default, the message store must have the following flags set in its **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property:</span></span>
  
- <span data-ttu-id="74bb6-140">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="74bb6-140">STORE_SUBMIT_OK</span></span>
    
- <span data-ttu-id="74bb6-141">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="74bb6-141">STORE_CREATE_OK</span></span>
    
- <span data-ttu-id="74bb6-142">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="74bb6-142">STORE_MODIFY_OK</span></span>
    
## <a name="notes-to-callers"></a><span data-ttu-id="74bb6-143">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="74bb6-143">Notes to callers</span></span>

<span data-ttu-id="74bb6-144">您可以通过检索状态表和搜索**PR_RESOURCE_FLAGS**列中的 STATUS_DEFAULT_STORE 标志设置为会话确定默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="74bb6-144">You can determine the default message store for the session by retrieving the status table and searching for the setting of the STATUS_DEFAULT_STORE flag in the **PR_RESOURCE_FLAGS** column.</span></span> <span data-ttu-id="74bb6-145">此设置的行代表被指定为会话默认的消息存储。</span><span class="sxs-lookup"><span data-stu-id="74bb6-145">The row that has this setting represents the message store that is designated as the session default.</span></span> 
  
<span data-ttu-id="74bb6-146">当设置 MAPI_DEFAULT_STORE 或 MAPI_SIMPLE_STORE_PERMANENT 标志时，MAPI 更新配置文件、 消息存储表和状态表。</span><span class="sxs-lookup"><span data-stu-id="74bb6-146">When either the MAPI_DEFAULT_STORE or the MAPI_SIMPLE_STORE_PERMANENT flag is set, MAPI updates the profile, message store table, and status table.</span></span> 
  
<span data-ttu-id="74bb6-147">消息存储默认设置进行更改时，只要将生成以下通知：</span><span class="sxs-lookup"><span data-stu-id="74bb6-147">Whenever a change is made to the message store default setting, the following notifications are generated:</span></span>
  
- <span data-ttu-id="74bb6-148">**FnevTableModified**事件通知发出的消息存储和状态表中的每个受影响的行。</span><span class="sxs-lookup"><span data-stu-id="74bb6-148">An **fnevTableModified** event notification is issued for each affected row in both the message store and status table.</span></span> 
    
- <span data-ttu-id="74bb6-149">内部通知颁发给 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="74bb6-149">An internal notification is issued to the MAPI spooler.</span></span> <span data-ttu-id="74bb6-150">正在进行的操作完成后，无更改;新的默认存储处理涉及默认的邮件存储，如消息下载的新操作。</span><span class="sxs-lookup"><span data-stu-id="74bb6-150">Operations already in progress are completed without change; new operations that involve the default message store, such as message downloading, are processed for the new default store.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="74bb6-151">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="74bb6-151">MFCMAPI reference</span></span>

<span data-ttu-id="74bb6-152">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="74bb6-152">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="74bb6-153">**文件**</span><span class="sxs-lookup"><span data-stu-id="74bb6-153">**File**</span></span>|<span data-ttu-id="74bb6-154">**函数**</span><span class="sxs-lookup"><span data-stu-id="74bb6-154">**Function**</span></span>|<span data-ttu-id="74bb6-155">**Comment**</span><span class="sxs-lookup"><span data-stu-id="74bb6-155">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="74bb6-156">MainDlg.cpp</span><span class="sxs-lookup"><span data-stu-id="74bb6-156">MainDlg.cpp</span></span>  <br/> |<span data-ttu-id="74bb6-157">CMainDlg::OnSetDefaultStore</span><span class="sxs-lookup"><span data-stu-id="74bb6-157">CMainDlg::OnSetDefaultStore</span></span>  <br/> |<span data-ttu-id="74bb6-158">MFCMAPI 使用**IMAPISession::SetDefaultStore**方法将所选的商店设置为默认存储。</span><span class="sxs-lookup"><span data-stu-id="74bb6-158">MFCMAPI uses the **IMAPISession::SetDefaultStore** method to set the selected store as the default store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="74bb6-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74bb6-159">See also</span></span>



[<span data-ttu-id="74bb6-160">PidTagResourceFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="74bb6-160">PidTagResourceFlags Canonical Property</span></span>](pidtagresourceflags-canonical-property.md)
  
[<span data-ttu-id="74bb6-161">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="74bb6-161">PidTagStoreSupportMask Canonical Property</span></span>](pidtagstoresupportmask-canonical-property.md)
  
[<span data-ttu-id="74bb6-162">TABLE_NOTIFICATION</span><span class="sxs-lookup"><span data-stu-id="74bb6-162">TABLE_NOTIFICATION</span></span>](table_notification.md)
  
[<span data-ttu-id="74bb6-163">IMAPISession: IUnknown</span><span class="sxs-lookup"><span data-stu-id="74bb6-163">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)


[<span data-ttu-id="74bb6-164">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="74bb6-164">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

