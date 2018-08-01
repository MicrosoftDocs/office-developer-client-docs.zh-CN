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
ms.openlocfilehash: 983c22772acfea7837e85d409b7928a35aed91ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775568"
---
# <a name="imapisessionopenmsgstore"></a><span data-ttu-id="f2cf6-103">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="f2cf6-103">IMAPISession::OpenMsgStore</span></span>

<span data-ttu-id="f2cf6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f2cf6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f2cf6-105">打开的消息存储并返回进一步访问[IMsgStore](imsgstoreimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-105">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="f2cf6-106">参数</span><span class="sxs-lookup"><span data-stu-id="f2cf6-106">Parameters</span></span>

<span data-ttu-id="f2cf6-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="f2cf6-108">[in]通用的地址对话框和其他的父窗口的句柄相关显示。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-108">[in] A handle to the parent window of the common address dialog box and other related displays.</span></span>
    
<span data-ttu-id="f2cf6-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="f2cf6-110">[in]在_lpEntryID_参数指向的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="f2cf6-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="f2cf6-112">[in]指向要打开的消息存储的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-112">[in] A pointer to the entry identifier of the message store to be opened.</span></span> <span data-ttu-id="f2cf6-113">_LpEntryID_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-113">The  _lpEntryID_ parameter must not be NULL.</span></span> 
    
<span data-ttu-id="f2cf6-114">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-114">_lpInterface_</span></span>
  
> <span data-ttu-id="f2cf6-115">[in]指向接口标识 (IID) 值，该值代表要用于访问邮件存储区的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-115">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message store.</span></span> <span data-ttu-id="f2cf6-116">传递 NULL 会导致_lppMDB_参数来返回指向的消息存储 (**IMsgStore**) 的标准接口的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-116">Passing NULL causes the  _lppMDB_ parameter to return a pointer to the standard interface for a message store (**IMsgStore**).</span></span>
    
<span data-ttu-id="f2cf6-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-117">_ulFlags_</span></span>
  
> <span data-ttu-id="f2cf6-118">[in]位掩码的标志，控制如何打开对象。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-118">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="f2cf6-119">可以使用以下标志：</span><span class="sxs-lookup"><span data-stu-id="f2cf6-119">The following flags can be used:</span></span>
    
  - <span data-ttu-id="f2cf6-120">MAPI_BEST_ACCESS： 请求的最大网络权限打开的消息存储和允许的用户的最大客户端应用程序权限。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-120">MAPI_BEST_ACCESS: Requests that the message store be opened with the maximum network permissions allowed for the user and the maximum client application permissions.</span></span> <span data-ttu-id="f2cf6-121">例如，如果客户端具有读/写权限，消息存储应打开具有读/写权限;如果客户端具有只读权限，应具有只读权限打开的消息存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-121">For example, if the client has read/write permission, the message store should be opened with read/write permission; if the client has read-only permission, the message store should be opened with read-only permission.</span></span> 
      
  - <span data-ttu-id="f2cf6-122">MAPI_DEFERRED_ERRORS： 允许**OpenMsgStore**成功返回可能的消息之前存储是完全可调用客户端。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-122">MAPI_DEFERRED_ERRORS: Allows **OpenMsgStore** to return successfully, possibly before the message store is fully available to the calling client.</span></span> <span data-ttu-id="f2cf6-123">如果消息存储不可用，则进行后续对象呼叫会引发错误。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-123">If the message store is not available, making a subsequent object call can raise an error.</span></span> 
      
  - <span data-ttu-id="f2cf6-124">MDB\_NO_DIALOG： 阻止的登录对话框显示。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-124">MDB\_NO_DIALOG: Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="f2cf6-125">如果设置此标志，并且**OpenMsgStore**有不足，无法配置的信息来打开消息存储，无需用户的帮助，则将返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-125">If this flag is set, and **OpenMsgStore** has insufficient configuration information to open the message store without the user's help, it returns MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="f2cf6-126">如果未设置此标志，消息存储提供程序可以提示用户更正名或密码或执行其他操作所需的消息存储与建立连接。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-126">If this flag is not set, the message store provider can prompt the user to correct a name or password or to perform other actions that are needed to establish a connection to the message store.</span></span> 
      
  - <span data-ttu-id="f2cf6-127">MDB\_NO_MAIL： 消息存储不应发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-127">MDB\_NO_MAIL: The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="f2cf6-128">当设置此标志时，MAPI 不通知 MAPI 后台处理程序打开的时此消息存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-128">When this flag is set, MAPI does not notify the MAPI spooler that this message store is being opened.</span></span>
      
  - <span data-ttu-id="f2cf6-129">MDB\_ONLINE： 在缓存 Exchange 模式，客户端或服务提供程序可以调用此方法与 MDB_ONLINE 覆盖本地消息存储库的连接并打开远程服务器上的存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-129">MDB\_ONLINE: In Cached Exchange Mode, a client or service provider can call this method with MDB_ONLINE to override the connection to the local message store and open the store on the remote server.</span></span> <span data-ttu-id="f2cf6-130">在缓存模式和非缓存模式下在同一 MAPI 会话中的同一时间，您无法打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-130">You cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="f2cf6-131">如果您已经打开的缓存的消息存储之前，必须也关闭存储打开与此标志，或打开新其中可以使用此标志打开 Exchange 存储的远程服务器上的 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-131">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>
      
  - <span data-ttu-id="f2cf6-132">MDB_TEMPORARY： 指示 MAPI 消息存储不是永久性操作和不应添加到消息存储表。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-132">MDB_TEMPORARY: Instructs MAPI that the message store is not permanent and should not be added to the message store table.</span></span> <span data-ttu-id="f2cf6-133">此标志用于登录到的消息存储，因此可以从配置文件部分以编程方式检索信息。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-133">This flag is used to log on to the message store so information can be retrieved programmatically from the profile section.</span></span> 
      
  - <span data-ttu-id="f2cf6-134">MDB_WRITE： 请求读/写权限的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-134">MDB_WRITE: Requests read/write permission to the message store.</span></span>
    
<span data-ttu-id="f2cf6-135">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="f2cf6-135">_lppMDB_</span></span>
  
> <span data-ttu-id="f2cf6-136">[输出]为邮件存储的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-136">[out] Pointer to a pointer of the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f2cf6-137">返回值</span><span class="sxs-lookup"><span data-stu-id="f2cf6-137">Return value</span></span>

<span data-ttu-id="f2cf6-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2cf6-138">S_OK</span></span> 
  
> <span data-ttu-id="f2cf6-139">消息存储已成功打开。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-139">The message store was successfully opened.</span></span>
    
<span data-ttu-id="f2cf6-140">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="f2cf6-140">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="f2cf6-141">尝试访问其用户没有足够的权限的消息存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-141">An attempt was made to access a message store for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="f2cf6-142">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="f2cf6-142">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="f2cf6-143">由_lpEntryID_的消息存储不存在。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-143">The message store indicated by  _lpEntryID_ does not exist.</span></span> 
    
<span data-ttu-id="f2cf6-144">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="f2cf6-144">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="f2cf6-145">将服务器不配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-145">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="f2cf6-146">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="f2cf6-146">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="f2cf6-147">将服务器不配置为支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-147">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="f2cf6-148">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="f2cf6-148">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="f2cf6-149">调用成功，但消息存储提供程序已经可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-149">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="f2cf6-150">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-150">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="f2cf6-151">要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-151">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> <span data-ttu-id="f2cf6-152">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-152">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="f2cf6-153">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-153">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f2cf6-154">说明</span><span class="sxs-lookup"><span data-stu-id="f2cf6-154">Remarks</span></span>

<span data-ttu-id="f2cf6-155">**IMAPISession::OpenMsgStore**方法打开特定邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-155">The **IMAPISession::OpenMsgStore** method opens a particular message store.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="f2cf6-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="f2cf6-156">Notes to callers</span></span>

<span data-ttu-id="f2cf6-157">消息存储库的默认权限级别是只读的。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-157">The default permission level for message stores is read-only.</span></span> <span data-ttu-id="f2cf6-158">如果设置 MDB_WRITE 标志，您仍可能不被授予读/写权限。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-158">If you set the MDB_WRITE flag, you still might not be granted read/write permission.</span></span> <span data-ttu-id="f2cf6-159">最终的 MAPI 分配到的消息存储取决于您的权限级别的访问级别，邮件存储本身，和消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-159">The final level of access that MAPI assigns to the message store depends on your permission level, the message store itself, and the message store provider.</span></span> 
  
<span data-ttu-id="f2cf6-160">如果调用**OpenMsgStore**具有只读权限打开邮件存储区时，将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f2cf6-160">If you call **OpenMsgStore** to open a message store with read-only permission, the following will occur:</span></span> 
  
- <span data-ttu-id="f2cf6-161">存储的**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会其存储\_MODIFY_OK 和存储\_CREATE_OK 位设置。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-161">The store's **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property will not have its STORE\_MODIFY_OK and STORE\_CREATE_OK bits set.</span></span> 
    
- <span data-ttu-id="f2cf6-162">设置了 MAPI_MODIFY 标志使用[IMAPISession::OpenEntry](imapisession-openentry.md)打开之一的消息存储的邮件或文件夹的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-162">Calls to open one of the message store's messages or folders by using [IMAPISession::OpenEntry](imapisession-openentry.md) with the MAPI_MODIFY flag set will fail.</span></span> 
    
- <span data-ttu-id="f2cf6-163">若要打开的消息存储库的邮件或文件夹的属性之一的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)使用 MAPI_MODIFY 标志的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-163">Calls to open one of the properties of the message store's messages or folders by using [IMAPIProp::OpenProperty](imapiprop-openproperty.md) with the MAPI_MODIFY flag will fail.</span></span> 
    
- <span data-ttu-id="f2cf6-164">对任何以下方法的调用将失败：</span><span class="sxs-lookup"><span data-stu-id="f2cf6-164">Calls to any of the following methods will fail:</span></span> 
    
  - [<span data-ttu-id="f2cf6-165">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="f2cf6-165">IMAPIFolder::CreateMessage</span></span>](imapifolder-createmessage.md)
    
  - [<span data-ttu-id="f2cf6-166">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="f2cf6-166">IMAPIFolder::DeleteMessages</span></span>](imapifolder-deletemessages.md)
    
  - [<span data-ttu-id="f2cf6-167">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="f2cf6-167">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
    
  - [<span data-ttu-id="f2cf6-168">IMAPIFolder::DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="f2cf6-168">IMAPIFolder::DeleteFolder</span></span>](imapifolder-deletefolder.md)
    
  - [<span data-ttu-id="f2cf6-169">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="f2cf6-169">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
    
  - [<span data-ttu-id="f2cf6-170">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="f2cf6-170">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
  - [<span data-ttu-id="f2cf6-171">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="f2cf6-171">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md)
  
- <span data-ttu-id="f2cf6-172">如果复制邮件的目标是只读的目标是源消息存储相同还是是另一个只读的存储，对下列方法的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-172">Calls to the following methods will fail if the destination for the copied message is read-only, whether the destination is the same as the source message store or is another read-only store.</span></span>
    
  - [<span data-ttu-id="f2cf6-173">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="f2cf6-173">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
  - [<span data-ttu-id="f2cf6-174">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="f2cf6-174">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
  - [<span data-ttu-id="f2cf6-175">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="f2cf6-175">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f2cf6-176">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="f2cf6-176">MFCMAPI reference</span></span>

<span data-ttu-id="f2cf6-177">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-177">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f2cf6-178">**文件**</span><span class="sxs-lookup"><span data-stu-id="f2cf6-178">**File**</span></span>|<span data-ttu-id="f2cf6-179">**函数**</span><span class="sxs-lookup"><span data-stu-id="f2cf6-179">**Function**</span></span>|<span data-ttu-id="f2cf6-180">**Comment**</span><span class="sxs-lookup"><span data-stu-id="f2cf6-180">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2cf6-181">MAPIStoreFunctions.cpp</span><span class="sxs-lookup"><span data-stu-id="f2cf6-181">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="f2cf6-182">CallOpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="f2cf6-182">CallOpenMsgStore</span></span>  <br/> |<span data-ttu-id="f2cf6-183">MFCMAPI 使用**IMAPISession::OpenMsgStore**方法打开的消息存储。</span><span class="sxs-lookup"><span data-stu-id="f2cf6-183">MFCMAPI uses the **IMAPISession::OpenMsgStore** method to open a message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f2cf6-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2cf6-184">See also</span></span>

- [<span data-ttu-id="f2cf6-185">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="f2cf6-185">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
- [<span data-ttu-id="f2cf6-186">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="f2cf6-186">IMAPISession::GetLastError</span></span>](imapisession-getlasterror.md)
- [<span data-ttu-id="f2cf6-187">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="f2cf6-187">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
- [<span data-ttu-id="f2cf6-188">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="f2cf6-188">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
- [<span data-ttu-id="f2cf6-189">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f2cf6-189">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)
- [<span data-ttu-id="f2cf6-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="f2cf6-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
- [<span data-ttu-id="f2cf6-191">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="f2cf6-191">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

