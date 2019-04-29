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
# <a name="imapisessionopenmsgstore"></a><span data-ttu-id="10849-103">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="10849-103">IMAPISession::OpenMsgStore</span></span>

<span data-ttu-id="10849-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10849-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10849-105">打开邮件存储, 并返回一个[IMsgStore](imsgstoreimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="10849-105">Opens a message store and returns an [IMsgStore](imsgstoreimapiprop.md) pointer for further access.</span></span> 
  
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

## <a name="parameters"></a><span data-ttu-id="10849-106">参数</span><span class="sxs-lookup"><span data-stu-id="10849-106">Parameters</span></span>

<span data-ttu-id="10849-107">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="10849-107">_ulUIParam_</span></span>
  
> <span data-ttu-id="10849-108">实时公用地址对话框和其他相关显示的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="10849-108">[in] A handle to the parent window of the common address dialog box and other related displays.</span></span>
    
<span data-ttu-id="10849-109">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="10849-109">_cbEntryID_</span></span>
  
> <span data-ttu-id="10849-110">实时条目标识符中由_lpEntryID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="10849-110">[in] The byte count in the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
<span data-ttu-id="10849-111">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="10849-111">_lpEntryID_</span></span>
  
> <span data-ttu-id="10849-112">实时指向要打开的邮件存储区的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="10849-112">[in] A pointer to the entry identifier of the message store to be opened.</span></span> <span data-ttu-id="10849-113">_lpEntryID_参数不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="10849-113">The  _lpEntryID_ parameter must not be NULL.</span></span> 
    
<span data-ttu-id="10849-114">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="10849-114">_lpInterface_</span></span>
  
> <span data-ttu-id="10849-115">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问邮件存储区的接口。</span><span class="sxs-lookup"><span data-stu-id="10849-115">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the message store.</span></span> <span data-ttu-id="10849-116">传递 NULL 会导致_lppMDB_参数返回指向邮件存储 (**IMsgStore**) 的标准接口的指针。</span><span class="sxs-lookup"><span data-stu-id="10849-116">Passing NULL causes the  _lppMDB_ parameter to return a pointer to the standard interface for a message store (**IMsgStore**).</span></span>
    
<span data-ttu-id="10849-117">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="10849-117">_ulFlags_</span></span>
  
> <span data-ttu-id="10849-118">实时用于控制对象打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="10849-118">[in] A bitmask of flags that controls how the object is opened.</span></span> <span data-ttu-id="10849-119">可以使用以下标志:</span><span class="sxs-lookup"><span data-stu-id="10849-119">The following flags can be used:</span></span>
    
  - <span data-ttu-id="10849-120">MAPI_BEST_ACCESS: 请求使用用户允许的最大网络权限和最大客户端应用程序权限打开邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="10849-120">MAPI_BEST_ACCESS: Requests that the message store be opened with the maximum network permissions allowed for the user and the maximum client application permissions.</span></span> <span data-ttu-id="10849-121">例如, 如果客户端具有读/写权限, 则应使用读/写权限打开邮件存储区;如果客户端具有只读权限, 则应使用只读权限打开邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="10849-121">For example, if the client has read/write permission, the message store should be opened with read/write permission; if the client has read-only permission, the message store should be opened with read-only permission.</span></span> 
      
  - <span data-ttu-id="10849-122">MAPI_DEFERRED_ERRORS: 允许**OpenMsgStore**成功返回, 这可能在邮件存储库完全提供给呼叫客户端之前。</span><span class="sxs-lookup"><span data-stu-id="10849-122">MAPI_DEFERRED_ERRORS: Allows **OpenMsgStore** to return successfully, possibly before the message store is fully available to the calling client.</span></span> <span data-ttu-id="10849-123">如果邮件存储不可用, 则进行后续的对象调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="10849-123">If the message store is not available, making a subsequent object call can raise an error.</span></span> 
      
  - <span data-ttu-id="10849-124">MDB\_NO_DIALOG: 禁止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="10849-124">MDB\_NO_DIALOG: Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="10849-125">如果设置了此标志, 并且**OpenMsgStore**没有足够的配置信息, 无法在用户帮助下打开邮件存储区, 则将返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="10849-125">If this flag is set, and **OpenMsgStore** has insufficient configuration information to open the message store without the user's help, it returns MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="10849-126">如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码, 或者执行建立与邮件存储的连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="10849-126">If this flag is not set, the message store provider can prompt the user to correct a name or password or to perform other actions that are needed to establish a connection to the message store.</span></span> 
      
  - <span data-ttu-id="10849-127">MDB\_NO_MAIL: 不应使用邮件存储来发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="10849-127">MDB\_NO_MAIL: The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="10849-128">设置此标志后, mapi 将不会通知 mapi 后台处理程序正在打开此邮件存储。</span><span class="sxs-lookup"><span data-stu-id="10849-128">When this flag is set, MAPI does not notify the MAPI spooler that this message store is being opened.</span></span>
      
  - <span data-ttu-id="10849-129">MDB\_ONLINE: 在缓存 Exchange 模式中, 客户端或服务提供程序可以使用 MDB_ONLINE 调用此方法, 以覆盖与本地邮件存储区的连接并在远程服务器上打开存储。</span><span class="sxs-lookup"><span data-stu-id="10849-129">MDB\_ONLINE: In Cached Exchange Mode, a client or service provider can call this method with MDB_ONLINE to override the connection to the local message store and open the store on the remote server.</span></span> <span data-ttu-id="10849-130">无法同时在缓存模式和非缓存模式下打开同一 MAPI 会话中的 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="10849-130">You cannot open an Exchange store in cached mode and in non-cached mode at the same time in the same MAPI session.</span></span> <span data-ttu-id="10849-131">如果已经打开缓存的邮件存储区，或者必须使用此标记关闭存储，或打开新的 MAPI 会话，可以使用此标记在远程服务器上打开 Exchange 存储。</span><span class="sxs-lookup"><span data-stu-id="10849-131">If you have already opened the cached message store, you must either close the store before you open it with this flag, or open a new MAPI session where you can open the Exchange store on the remote server by using this flag.</span></span>
      
  - <span data-ttu-id="10849-132">MDB_TEMPORARY: 指示 MAPI 邮件存储区不是永久的, 不应将其添加到邮件存储库表中。</span><span class="sxs-lookup"><span data-stu-id="10849-132">MDB_TEMPORARY: Instructs MAPI that the message store is not permanent and should not be added to the message store table.</span></span> <span data-ttu-id="10849-133">此标志用于登录到邮件存储区, 以便可以从 "配置文件" 部分以编程方式检索信息。</span><span class="sxs-lookup"><span data-stu-id="10849-133">This flag is used to log on to the message store so information can be retrieved programmatically from the profile section.</span></span> 
      
  - <span data-ttu-id="10849-134">MDB_WRITE: 请求对邮件存储区的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="10849-134">MDB_WRITE: Requests read/write permission to the message store.</span></span>
    
<span data-ttu-id="10849-135">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="10849-135">_lppMDB_</span></span>
  
> <span data-ttu-id="10849-136">排除指向邮件存储区的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="10849-136">[out] Pointer to a pointer of the message store.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="10849-137">返回值</span><span class="sxs-lookup"><span data-stu-id="10849-137">Return value</span></span>

<span data-ttu-id="10849-138">S_OK</span><span class="sxs-lookup"><span data-stu-id="10849-138">S_OK</span></span> 
  
> <span data-ttu-id="10849-139">邮件存储已成功打开。</span><span class="sxs-lookup"><span data-stu-id="10849-139">The message store was successfully opened.</span></span>
    
<span data-ttu-id="10849-140">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="10849-140">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="10849-141">试图访问用户具有的权限不足的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="10849-141">An attempt was made to access a message store for which the user has insufficient permissions.</span></span>
    
<span data-ttu-id="10849-142">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="10849-142">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="10849-143">_lpEntryID_指示的邮件存储不存在。</span><span class="sxs-lookup"><span data-stu-id="10849-143">The message store indicated by  _lpEntryID_ does not exist.</span></span> 
    
<span data-ttu-id="10849-144">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="10849-144">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="10849-145">未将服务器配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="10849-145">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="10849-146">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="10849-146">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="10849-147">未将服务器配置为支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="10849-147">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="10849-148">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="10849-148">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="10849-149">调用成功, 但邮件存储区提供程序有可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="10849-149">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="10849-150">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="10849-150">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="10849-151">若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="10849-151">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> <span data-ttu-id="10849-152">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="10849-152">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="10849-153">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="10849-153">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span>
    
## <a name="remarks"></a><span data-ttu-id="10849-154">说明</span><span class="sxs-lookup"><span data-stu-id="10849-154">Remarks</span></span>

<span data-ttu-id="10849-155">**IMAPISession:: OpenMsgStore**方法打开特定的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="10849-155">The **IMAPISession::OpenMsgStore** method opens a particular message store.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="10849-156">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="10849-156">Notes to callers</span></span>

<span data-ttu-id="10849-157">邮件存储区的默认权限级别为只读。</span><span class="sxs-lookup"><span data-stu-id="10849-157">The default permission level for message stores is read-only.</span></span> <span data-ttu-id="10849-158">如果设置了 MDB_WRITE 标志, 则仍可能无法授予您读/写权限。</span><span class="sxs-lookup"><span data-stu-id="10849-158">If you set the MDB_WRITE flag, you still might not be granted read/write permission.</span></span> <span data-ttu-id="10849-159">MAPI 为邮件存储分配的最终访问级别取决于您的权限级别、邮件存储区本身和邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="10849-159">The final level of access that MAPI assigns to the message store depends on your permission level, the message store itself, and the message store provider.</span></span> 
  
<span data-ttu-id="10849-160">如果调用**OpenMsgStore**以打开具有只读权限的邮件存储区, 将发生以下情况:</span><span class="sxs-lookup"><span data-stu-id="10849-160">If you call **OpenMsgStore** to open a message store with read-only permission, the following will occur:</span></span> 
  
- <span data-ttu-id="10849-161">store 的**PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性不会设置其 store\_MODIFY_OK 和 store\_CREATE_OK bits。</span><span class="sxs-lookup"><span data-stu-id="10849-161">The store's **PR\_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property will not have its STORE\_MODIFY_OK and STORE\_CREATE_OK bits set.</span></span> 
    
- <span data-ttu-id="10849-162">通过使用[IMAPISession:: OpenEntry](imapisession-openentry.md)和 MAPI_MODIFY 标志设置来打开邮件存储区中的邮件或文件夹的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="10849-162">Calls to open one of the message store's messages or folders by using [IMAPISession::OpenEntry](imapisession-openentry.md) with the MAPI_MODIFY flag set will fail.</span></span> 
    
- <span data-ttu-id="10849-163">通过使用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)和 MAPI_MODIFY 标志打开邮件存储的邮件或文件夹的属性之一的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="10849-163">Calls to open one of the properties of the message store's messages or folders by using [IMAPIProp::OpenProperty](imapiprop-openproperty.md) with the MAPI_MODIFY flag will fail.</span></span> 
    
- <span data-ttu-id="10849-164">对以下任一方法的调用将失败:</span><span class="sxs-lookup"><span data-stu-id="10849-164">Calls to any of the following methods will fail:</span></span> 
    
  - [<span data-ttu-id="10849-165">IMAPIFolder::CreateMessage</span><span class="sxs-lookup"><span data-stu-id="10849-165">IMAPIFolder::CreateMessage</span></span>](imapifolder-createmessage.md)
    
  - [<span data-ttu-id="10849-166">IMAPIFolder::DeleteMessages</span><span class="sxs-lookup"><span data-stu-id="10849-166">IMAPIFolder::DeleteMessages</span></span>](imapifolder-deletemessages.md)
    
  - [<span data-ttu-id="10849-167">IMAPIFolder::CreateFolder</span><span class="sxs-lookup"><span data-stu-id="10849-167">IMAPIFolder::CreateFolder</span></span>](imapifolder-createfolder.md)
    
  - [<span data-ttu-id="10849-168">IMAPIFolder::DeleteFolder</span><span class="sxs-lookup"><span data-stu-id="10849-168">IMAPIFolder::DeleteFolder</span></span>](imapifolder-deletefolder.md)
    
  - [<span data-ttu-id="10849-169">IMAPIFolder::SetMessageStatus</span><span class="sxs-lookup"><span data-stu-id="10849-169">IMAPIFolder::SetMessageStatus</span></span>](imapifolder-setmessagestatus.md)
    
  - [<span data-ttu-id="10849-170">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="10849-170">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
  - [<span data-ttu-id="10849-171">IMAPIProp::DeleteProps</span><span class="sxs-lookup"><span data-stu-id="10849-171">IMAPIProp::DeleteProps</span></span>](imapiprop-deleteprops.md)
  
- <span data-ttu-id="10849-172">如果复制的邮件的目标是只读的, 无论目标是与源邮件存储一样还是另一个只读存储, 则对以下方法的调用将失败。</span><span class="sxs-lookup"><span data-stu-id="10849-172">Calls to the following methods will fail if the destination for the copied message is read-only, whether the destination is the same as the source message store or is another read-only store.</span></span>
    
  - [<span data-ttu-id="10849-173">IMAPIFolder::CopyMessages</span><span class="sxs-lookup"><span data-stu-id="10849-173">IMAPIFolder::CopyMessages</span></span>](imapifolder-copymessages.md)
    
  - [<span data-ttu-id="10849-174">IMAPIFolder::CopyFolder</span><span class="sxs-lookup"><span data-stu-id="10849-174">IMAPIFolder::CopyFolder</span></span>](imapifolder-copyfolder.md)
    
  - [<span data-ttu-id="10849-175">IMAPIProp::CopyTo</span><span class="sxs-lookup"><span data-stu-id="10849-175">IMAPIProp::CopyTo</span></span>](imapiprop-copyto.md)
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="10849-176">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="10849-176">MFCMAPI reference</span></span>

<span data-ttu-id="10849-177">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="10849-177">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="10849-178">**文件**</span><span class="sxs-lookup"><span data-stu-id="10849-178">**File**</span></span>|<span data-ttu-id="10849-179">**函数**</span><span class="sxs-lookup"><span data-stu-id="10849-179">**Function**</span></span>|<span data-ttu-id="10849-180">**备注**</span><span class="sxs-lookup"><span data-stu-id="10849-180">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10849-181">MAPIStoreFunctions</span><span class="sxs-lookup"><span data-stu-id="10849-181">MAPIStoreFunctions.cpp</span></span>  <br/> |<span data-ttu-id="10849-182">CallOpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="10849-182">CallOpenMsgStore</span></span>  <br/> |<span data-ttu-id="10849-183">MFCMAPI 使用**IMAPISession:: OpenMsgStore**方法打开邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="10849-183">MFCMAPI uses the **IMAPISession::OpenMsgStore** method to open a message store.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="10849-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10849-184">See also</span></span>

- [<span data-ttu-id="10849-185">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="10849-185">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
- [<span data-ttu-id="10849-186">IMAPISession::GetLastError</span><span class="sxs-lookup"><span data-stu-id="10849-186">IMAPISession::GetLastError</span></span>](imapisession-getlasterror.md)
- [<span data-ttu-id="10849-187">IMAPISession::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="10849-187">IMAPISession::OpenEntry</span></span>](imapisession-openentry.md)
- [<span data-ttu-id="10849-188">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="10849-188">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
- [<span data-ttu-id="10849-189">IMAPISession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="10849-189">IMAPISession : IUnknown</span></span>](imapisessioniunknown.md)
- [<span data-ttu-id="10849-190">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="10849-190">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)
- [<span data-ttu-id="10849-191">使用宏进行错误处理</span><span class="sxs-lookup"><span data-stu-id="10849-191">Using Macros for Error Handling</span></span>](using-macros-for-error-handling.md)

