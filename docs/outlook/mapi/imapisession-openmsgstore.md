---
title: IMAPISessionOpenMsgStore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.OpenMsgStore
api_type:
- COM
ms.assetid: 7f73b5cf-7093-42e9-8acc-63d73df77cf5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 19d3df004676a71e2bf6243d9288efd824d99c33
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418020"
---
# <a name="imapisessionopenmsgstore"></a><span data-ttu-id="89af4-103">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="89af4-103">IMAPISession::OpenMsgStore</span></span>

<span data-ttu-id="89af4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="89af4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="89af4-105">打开邮件存储并返回 [IMsgStore](imsgstoreimapiprop.md) 指针以进一步访问。</span><span class="sxs-lookup"><span data-stu-id="89af4-105">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span> 
  
```cpp
HRESULT OpenMsgStore(
  ULONG_PTR ulUIParam,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPCIID lpInterface,
  ULONG ulFlags,
  LPMDB FAR * lppMDB
);
```

## <a name="parameters"></a><span data-ttu-id="89af4-106">参数</span><span class="sxs-lookup"><span data-stu-id="89af4-106">Parameters</span></span>

<span data-ttu-id="89af4-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="89af4-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="89af4-108">[in]常见地址对话框和其他相关显示器的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="89af4-108">[in] A handle to the parent window of the common address dialog box and other related displays.</span></span>
    
<span data-ttu-id="89af4-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="89af4-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="89af4-110">[in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="89af4-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="89af4-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="89af4-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="89af4-112">[in]指向要打开的邮件存储的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="89af4-112">[in] A pointer to the entry identifier of the message store to be opened.</span></span> <span data-ttu-id="89af4-113">_lpEntryID_ 参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="89af4-113">The  _lpEntryID_ parameter must not be NULL.</span></span> 
    
<span data-ttu-id="89af4-114">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="89af4-114">_lpInterface_</span></span>
  
> <span data-ttu-id="89af4-115">[in]指向接口标识符的指针 (IID) 表示用于访问邮件存储的接口的 IID 标识符。</span><span class="sxs-lookup"><span data-stu-id="89af4-115">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message store.</span></span> <span data-ttu-id="89af4-116">传递 NULL 会导致  _lppMDB_ 参数返回指向 **IMsgStore** (标准接口) 。</span><span class="sxs-lookup"><span data-stu-id="89af4-116">Passing NULL causes the  _lppMDB_ parameter to return a pointer to the standard interface for a message store (**IMsgStore**).</span></span>
    
<span data-ttu-id="89af4-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="89af4-117">_ulFlags_</span></span>
  
> <span data-ttu-id="89af4-118">[in]控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="89af4-118">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="89af4-119">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="89af4-119">The following flags can be used:</span></span>
    
  - <span data-ttu-id="89af4-120">MAPI_BEST_ACCESS：请求使用用户允许的最大网络权限和最大客户端应用程序权限打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-120">MAPI_BEST_ACCESS: Requests that the message store be opened with the maximum network permissions allowed for the user and the maximum client application permissions.</span></span> <span data-ttu-id="89af4-121">例如，如果客户端具有读/写权限，则应该使用读/写权限打开邮件存储;如果客户端具有只读权限，则应该使用只读权限打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-121">For example, if the client has read/write permission, the message store should be opened with read/write permission; if the client has read-only permission, the message store should be opened with read-only permission.</span></span> 
      
  - <span data-ttu-id="89af4-122">MAPI_DEFERRED_ERRORS：允许在邮件存储完全可供调用客户端使用之前，成功返回 **OpenMsgStore。**</span><span class="sxs-lookup"><span data-stu-id="89af4-122">MAPI_DEFERRED_ERRORS: Allows **OpenMsgStore** to return successfully, possibly before the message store is fully available to the calling client.</span></span> <span data-ttu-id="89af4-123">如果邮件存储不可用，则进行后续对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="89af4-123">If the message store is not available, making a subsequent object call can raise an error.</span></span> 
      
  - <span data-ttu-id="89af4-124">MDB \_ NO_DIALOG：禁止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="89af4-124">MDB\_NO_DIALOG: Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="89af4-125">如果设置了此标志，并且 **OpenMsgStore** 的配置信息不足，在没有用户帮助的情况下打开邮件存储，它将返回MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="89af4-125">If this flag is set, and **OpenMsgStore** has insufficient configuration information to open the message store without the user's help, it returns MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="89af4-126">如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码或执行建立与邮件存储的连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="89af4-126">If this flag is not set, the message store provider can prompt the user to correct a name or password or to perform other actions that are needed to establish a connection to the message store.</span></span> 
      
  - <span data-ttu-id="89af4-127">MDB NO_MAIL：邮件存储不应 \_ 用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="89af4-127">MDB\_NO_MAIL: The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="89af4-128">设置此标志后，MAPI 不会通知 MAPI 后台处理程序此邮件存储正在打开。</span><span class="sxs-lookup"><span data-stu-id="89af4-128">When this flag is set, MAPI does not notify the MAPI spooler that this message store is being opened.</span></span>
      
  - <span data-ttu-id="89af4-129">MDB ONLINE：在缓存Exchange模式下，客户端或服务提供商可以使用 MDB_ONLINE 调用此方法以覆盖与本地邮件存储的连接，并打开远程 \_ 服务器上存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-129">MDB\_ONLINE: In Cached Exchange Mode, a client or service provider can call this method with MDB_ONLINE to override the connection to the local message store and open the store on the remote server.</span></span> <span data-ttu-id="89af4-130">不能在同一 MAPI 会话中Exchange缓存模式和非缓存模式下同时打开缓存存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-130">You cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="89af4-131">如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-131">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>
      
  - <span data-ttu-id="89af4-132">MDB_TEMPORARY：指示 MAPI 邮件存储不是永久性的，不应添加到邮件存储表中。</span><span class="sxs-lookup"><span data-stu-id="89af4-132">MDB_TEMPORARY: Instructs MAPI that the message store is not permanent and should not be added to the message store table.</span></span> <span data-ttu-id="89af4-133">此标志用于登录到邮件存储，以便可以通过编程方式从配置文件部分检索信息。</span><span class="sxs-lookup"><span data-stu-id="89af4-133">This flag is used to log on to the message store so information can be retrieved programmatically from the profile section.</span></span> 
      
  - <span data-ttu-id="89af4-134">MDB_WRITE：请求对邮件存储的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="89af4-134">MDB_WRITE: Requests read/write permission to the message store.</span></span>
    
<span data-ttu-id="89af4-135">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="89af4-135">_lppMDB_</span></span>
  
> <span data-ttu-id="89af4-136">[out]指向消息存储的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="89af4-136">[out] Pointer to a pointer of the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="89af4-137">返回值</span><span class="sxs-lookup"><span data-stu-id="89af4-137">Return value</span></span>

<span data-ttu-id="89af4-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="89af4-138">S_OK</span></span> 
  
> <span data-ttu-id="89af4-139">已成功打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-139">The message store was successfully opened.</span></span>
    
<span data-ttu-id="89af4-140">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="89af4-140">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="89af4-141">尝试访问用户权限不足的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-141">An attempt was made to access a message store for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="89af4-142">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="89af4-142">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="89af4-143">_lpEntryID_ 指示的邮件存储不存在。</span><span class="sxs-lookup"><span data-stu-id="89af4-143">The message store indicated by  _lpEntryID_ does not exist.</span></span> 
    
<span data-ttu-id="89af4-144">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="89af4-144">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="89af4-145">服务器未配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="89af4-145">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="89af4-146">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="89af4-146">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="89af4-147">服务器未配置为支持客户端区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="89af4-147">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="89af4-148">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="89af4-148">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="89af4-149">调用成功，但邮件存储提供程序提供错误信息。</span><span class="sxs-lookup"><span data-stu-id="89af4-149">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="89af4-150">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="89af4-150">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="89af4-151">若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="89af4-151">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> <span data-ttu-id="89af4-152">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="89af4-152">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="89af4-153">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="89af4-153">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="89af4-154">备注</span><span class="sxs-lookup"><span data-stu-id="89af4-154">Remarks</span></span>

<span data-ttu-id="89af4-155">**IMAPISession：：OpenMsgStore** 方法打开特定邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-155">The **IMAPISession::OpenMsgStore** method opens a particular message store.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="89af4-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="89af4-156">Notes to callers</span></span>

<span data-ttu-id="89af4-157">邮件存储的默认权限级别为只读。</span><span class="sxs-lookup"><span data-stu-id="89af4-157">The default permission level for message stores is read-only.</span></span> <span data-ttu-id="89af4-158">如果您设置MDB_WRITE，您仍可能不会被授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="89af4-158">If you set the MDB_WRITE flag, you still might not be granted read/write permission.</span></span> <span data-ttu-id="89af4-159">MAPI 分配给邮件存储的最终访问级别取决于您的权限级别、邮件存储本身以及邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="89af4-159">The final level of access that MAPI assigns to the message store depends on your permission level, the message store itself, and the message store provider.</span></span> 
  
<span data-ttu-id="89af4-160">如果调用 **OpenMsgStore** 以使用只读权限打开邮件存储，将发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="89af4-160">If you call **OpenMsgStore** to open a message store with read-only permission, the following will occur:</span></span> 
  
- <span data-ttu-id="89af4-161">存储的 **PR \_** STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会设置其 STORE MODIFY_OK STORE CREATE_OK \_ \_ 位。</span><span class="sxs-lookup"><span data-stu-id="89af4-161">The store's **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property will not have its STORE\_MODIFY_OK and STORE\_CREATE_OK bits set.</span></span> 
    
- <span data-ttu-id="89af4-162">调用使用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 打开邮件存储的邮件或文件夹之一，MAPI_MODIFY设置失败。</span><span class="sxs-lookup"><span data-stu-id="89af4-162">Calls to open one of the message store's messages or folders by using [IMAPISession::OpenEntry](imapisession-openentry.md) with the MAPI_MODIFY flag set will fail.</span></span> 
    
- <span data-ttu-id="89af4-163">调用使用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 和 MAPI_MODIFY 标志打开邮件存储的邮件或文件夹的属性之一将失败。</span><span class="sxs-lookup"><span data-stu-id="89af4-163">Calls to open one of the properties of the message store's messages or folders by using [IMAPIProp::OpenProperty](imapiprop-openproperty.md) with the MAPI_MODIFY flag will fail.</span></span> 
    
- <span data-ttu-id="89af4-164">调用以下任一方法将失败：</span><span class="sxs-lookup"><span data-stu-id="89af4-164">Calls to any of the following methods will fail:</span></span> 
    
  - [<span data-ttu-id="89af4-165">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="89af4-165">IMAPIFolder::CreateMessage</span></span>](imapifolder-createmessage.md)
    
  - [<span data-ttu-id="89af4-166">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="89af4-166">IMAPIFolder::DeleteMessages</span></span>](imapifolder-deletemessages.md)
    
  - [<span data-ttu-id="89af4-167">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="89af4-167">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
    
  - [<span data-ttu-id="89af4-168">IMAPIFolder::DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="89af4-168">IMAPIFolder::DeleteFolder</span></span>](imapifolder-deletefolder.md)
    
  - [<span data-ttu-id="89af4-169">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="89af4-169">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
    
  - [<span data-ttu-id="89af4-170">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="89af4-170">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
  - [<span data-ttu-id="89af4-171">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="89af4-171">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md)
  
- <span data-ttu-id="89af4-172">如果复制的邮件的目标为只读，则对以下方法的调用将失败，无论目标与源邮件存储相同还是另一个只读存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-172">Calls to the following methods will fail if the destination for the copied message is read-only, whether the destination is the same as the source message store or is another read-only store.</span></span>
    
  - [<span data-ttu-id="89af4-173">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="89af4-173">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
  - [<span data-ttu-id="89af4-174">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="89af4-174">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
  - [<span data-ttu-id="89af4-175">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="89af4-175">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="89af4-176">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="89af4-176">MFCMAPI reference</span></span>

<span data-ttu-id="89af4-177">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="89af4-177">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="89af4-178">**文件**</span><span class="sxs-lookup"><span data-stu-id="89af4-178">**File**</span></span>|<span data-ttu-id="89af4-179">**函数**</span><span class="sxs-lookup"><span data-stu-id="89af4-179">**Function**</span></span>|<span data-ttu-id="89af4-180">**备注**</span><span class="sxs-lookup"><span data-stu-id="89af4-180">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89af4-181">MAPIStoreFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="89af4-181">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="89af4-182">CallOpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="89af4-182">CallOpenMsgStore</span></span>  <br/> |<span data-ttu-id="89af4-183">MFCMAPI 使用 **IMAPISession：：OpenMsgStore** 方法打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="89af4-183">MFCMAPI uses the **IMAPISession::OpenMsgStore** method to open a message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="89af4-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89af4-184">See also</span></span>

- [<span data-ttu-id="89af4-185">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="89af4-185">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
- [<span data-ttu-id="89af4-186">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="89af4-186">IMAPISession::GetLastError</span></span>](imapisession-getlasterror.md)
- [<span data-ttu-id="89af4-187">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="89af4-187">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
- [<span data-ttu-id="89af4-188">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="89af4-188">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
- [<span data-ttu-id="89af4-189">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="89af4-189">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)
- [<span data-ttu-id="89af4-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="89af4-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
- [<span data-ttu-id="89af4-191">使用宏处理错误</span><span class="sxs-lookup"><span data-stu-id="89af4-191">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

