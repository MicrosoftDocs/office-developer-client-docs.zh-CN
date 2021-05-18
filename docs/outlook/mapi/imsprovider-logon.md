---
title: IMSProviderLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.Logon
api_type:
- COM
ms.assetid: 890d9cbe-3570-4cf0-aeae-667c0e5ba181
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9c7f62c69c7a06f7ca0e4bfddcf789cddc536ea6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309665"
---
# <a name="imsproviderlogon"></a><span data-ttu-id="e47b7-103">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="e47b7-103">IMSProvider::Logon</span></span>

  
  
<span data-ttu-id="e47b7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e47b7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e47b7-105">将 MAPI 记录到邮件存储提供程序的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e47b7-105">Logs MAPI on to one instance of a message store provider.</span></span>
  
```cpp
HRESULT Logon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  LPCIID lpInterface,
  ULONG FAR * lpcbSpoolSecurity,
  LPBYTE FAR * lppbSpoolSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPMSLOGON FAR * lppMSLogon,
  LPMDB FAR * lppMDB
);
```

## <a name="parameters"></a><span data-ttu-id="e47b7-106">参数</span><span class="sxs-lookup"><span data-stu-id="e47b7-106">Parameters</span></span>

 <span data-ttu-id="e47b7-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="e47b7-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="e47b7-108">[in]指向邮件存储的当前 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-108">[in] A pointer to the current MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="e47b7-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="e47b7-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="e47b7-110">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e47b7-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="e47b7-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="e47b7-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="e47b7-112">[in]指向包含用于存储提供程序登录的配置文件的名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-112">[in] A pointer to a string that contains the name of the profile being used for store provider logon.</span></span> <span data-ttu-id="e47b7-113">此字符串可以在对话框中显示、写入或日志文件或忽略。</span><span class="sxs-lookup"><span data-stu-id="e47b7-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="e47b7-114">如果在  _ulFlags_ 参数中设置了 MAPI_UNICODE 标志，则它必须采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e47b7-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="e47b7-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="e47b7-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="e47b7-116">[in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e47b7-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="e47b7-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="e47b7-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="e47b7-118">[in]指向邮件存储的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="e47b7-119">在 _lpEntryID_ 中传递 **null** 表示尚未选择邮件存储，并且会显示允许用户选择邮件存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-119">Passing **null** in  _lpEntryID_ indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="e47b7-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e47b7-120">_ulFlags_</span></span>
  
> <span data-ttu-id="e47b7-121">[in]控制如何执行登录的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e47b7-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="e47b7-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="e47b7-122">The following flags can be set:</span></span>
    
<span data-ttu-id="e47b7-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="e47b7-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="e47b7-124">即使基础对象对调用实现不可用，也允许调用成功。</span><span class="sxs-lookup"><span data-stu-id="e47b7-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="e47b7-125">如果该对象不可用，则对该对象的后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="e47b7-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="e47b7-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e47b7-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="e47b7-127">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e47b7-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="e47b7-128">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e47b7-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="e47b7-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="e47b7-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="e47b7-130">禁止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="e47b7-131">如果设置此标志，则返回错误MAPI_E_LOGON_FAILED登录不成功时返回。</span><span class="sxs-lookup"><span data-stu-id="e47b7-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="e47b7-132">如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="e47b7-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions that are necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="e47b7-133">MDB_NO_MAIL</span><span class="sxs-lookup"><span data-stu-id="e47b7-133">MDB_NO_MAIL</span></span> 
  
> <span data-ttu-id="e47b7-134">邮件存储不应用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="e47b7-134">The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="e47b7-135">该标志指示 MAPI 不通知 MAPI 后台处理程序此邮件存储正在打开。</span><span class="sxs-lookup"><span data-stu-id="e47b7-135">The flag signals MAPI not to notify the MAPI spooler that this message store is being opened.</span></span> <span data-ttu-id="e47b7-136">如果设置了此标志，并且邮件存储与传输提供程序紧密结合，则提供程序不需要调用 [IMAPISupport：：SpoolerNotify](imapisupport-spoolernotify.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-136">If this flag is set and the message store is tightly coupled with a transport provider, the provider does not need to call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> 
    
<span data-ttu-id="e47b7-137">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="e47b7-137">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="e47b7-138">记录存储，以便可以通过编程方式从配置文件部分检索信息，而无需使用对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-138">Logs on the store so that information can be retrieved programmatically from the profile section, without use of dialog boxes.</span></span> <span data-ttu-id="e47b7-139">此标志指示 MAPI 不会将存储添加到邮件存储表，并且存储不能永久化。</span><span class="sxs-lookup"><span data-stu-id="e47b7-139">This flag instructs MAPI that the store is not to be added to the message store table and that the store cannot be made permanent.</span></span> <span data-ttu-id="e47b7-140">如果设置了此标志，则消息存储提供程序无需调用 [IMAPISupport：：ModifyProfile](imapisupport-modifyprofile.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-140">If this flag is set, message store providers do not need to call the [IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md) method.</span></span> 
    
<span data-ttu-id="e47b7-141">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="e47b7-141">MDB_WRITE</span></span> 
  
> <span data-ttu-id="e47b7-142">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="e47b7-142">Requests read/write permission.</span></span>
    
 <span data-ttu-id="e47b7-143">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="e47b7-143">_lpInterface_</span></span>
  
> <span data-ttu-id="e47b7-144">[in]指向接口标识符的 (IID) 供邮件存储登录。</span><span class="sxs-lookup"><span data-stu-id="e47b7-144">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="e47b7-145">传递 **null** 指示返回 [IMsgStore](imsgstoreimapiprop.md) (邮件存储) MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="e47b7-145">Passing **null** indicates the MAPI interface for the message store ( [IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="e47b7-146">_还可以将 lpInterface_ 参数设置为邮件存储的适当接口的标识符 (例如，IID_IUnknown 或 IID_IMAPIProp) 。</span><span class="sxs-lookup"><span data-stu-id="e47b7-146">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example, IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="e47b7-147">_lpcbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="e47b7-147">_lpcbSpoolSecurity_</span></span>
  
> <span data-ttu-id="e47b7-148">[out]指向存储提供程序在  _lppbSpoolSecurity_ 参数中返回验证数据的大小（以字节为单位）的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-148">[out] A pointer to the variable in which the store provider returns the size, in bytes, of the validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="e47b7-149">_lppbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="e47b7-149">_lppbSpoolSecurity_</span></span>
  
> <span data-ttu-id="e47b7-150">[out]指向返回的验证数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-150">[out] A pointer to the pointer to the returned validation data.</span></span> <span data-ttu-id="e47b7-151">提供此验证数据，以便 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md) 方法可以将 MAPI 后台处理程序记录到与消息存储提供程序相同的存储。</span><span class="sxs-lookup"><span data-stu-id="e47b7-151">This validation data is provided so the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method can log the MAPI spooler on to the same store as the message store provider.</span></span> 
    
 <span data-ttu-id="e47b7-152">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="e47b7-152">_lppMAPIError_</span></span>
  
> <span data-ttu-id="e47b7-153">[out]指向返回的 [MAPIERROR](mapierror.md) 结构的指针（如果有）的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-153">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="e47b7-154">如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 null。</span><span class="sxs-lookup"><span data-stu-id="e47b7-154">The  _lppMAPIError_ parameter can be set to **null** if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="e47b7-155">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="e47b7-155">_lppMSLogon_</span></span>
  
> <span data-ttu-id="e47b7-156">[out]指向指向 MAPI 要登录的消息存储登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-156">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="e47b7-157">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="e47b7-157">_lppMDB_</span></span>
  
> <span data-ttu-id="e47b7-158">[out]指向 MAPI 后台处理程序和客户端应用程序要登录的消息存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-158">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e47b7-159">返回值</span><span class="sxs-lookup"><span data-stu-id="e47b7-159">Return value</span></span>

<span data-ttu-id="e47b7-160">S_OK</span><span class="sxs-lookup"><span data-stu-id="e47b7-160">S_OK</span></span> 
  
> <span data-ttu-id="e47b7-161">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="e47b7-161">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="e47b7-162">MAPI_E_FAILONEPROVIDER</span><span class="sxs-lookup"><span data-stu-id="e47b7-162">MAPI_E_FAILONEPROVIDER</span></span> 
  
> <span data-ttu-id="e47b7-163">此提供程序无法登录，但此错误不应禁用该服务。</span><span class="sxs-lookup"><span data-stu-id="e47b7-163">This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="e47b7-164">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="e47b7-164">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="e47b7-165">无法建立登录会话。</span><span class="sxs-lookup"><span data-stu-id="e47b7-165">A logon session could not be established.</span></span>
    
<span data-ttu-id="e47b7-166">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="e47b7-166">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="e47b7-167">配置文件包含的信息不足，无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="e47b7-167">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="e47b7-168">返回此值时，MAPI 将调用邮件存储提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="e47b7-168">When this value is returned, MAPI calls the message store provider's message-service entry point function.</span></span>
    
<span data-ttu-id="e47b7-169">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="e47b7-169">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="e47b7-170">用户通常通过单击对话框中的"取消" **按钮来取消** 操作。</span><span class="sxs-lookup"><span data-stu-id="e47b7-170">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="e47b7-171">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="e47b7-171">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="e47b7-172">服务器未配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="e47b7-172">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="e47b7-173">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="e47b7-173">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="e47b7-174">服务器未配置为支持客户端区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-174">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="e47b7-175">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="e47b7-175">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="e47b7-176">调用成功，但邮件存储提供程序提供错误信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-176">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="e47b7-177">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="e47b7-177">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="e47b7-178">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="e47b7-178">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="e47b7-179">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="e47b7-179">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="e47b7-180">若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-180">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="e47b7-181">备注</span><span class="sxs-lookup"><span data-stu-id="e47b7-181">Remarks</span></span>

<span data-ttu-id="e47b7-182">MAPI 调用 **IMSProvider：：Logon** 方法，以执行获取对消息存储的访问权限所需的大部分处理。</span><span class="sxs-lookup"><span data-stu-id="e47b7-182">MAPI calls the **IMSProvider::Logon** method to do the majority of processing necessary to obtain access to a message store.</span></span> <span data-ttu-id="e47b7-183">邮件存储提供程序验证访问特定存储所需的任何用户凭据，并返回 MAPI 后台处理程序和客户端应用程序可登录到  _的 lppMDB_ 参数中的邮件存储对象。</span><span class="sxs-lookup"><span data-stu-id="e47b7-183">Message store providers validate any user credentials necessary to access a particular store and return a message store object in the  _lppMDB_ parameter that the MAPI spooler and client applications can log on to.</span></span> 
  
<span data-ttu-id="e47b7-184">除了返回的邮件存储对象用于客户端和 MAPI 后台处理程序之外，提供程序还返回 MAPI 用于控制打开的存储区的邮件存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="e47b7-184">In addition to the returned message store object for client and MAPI spooler use, the provider also returns a message store logon object for MAPI to use in controlling the opened store.</span></span> <span data-ttu-id="e47b7-185">邮件存储登录对象和邮件存储对象应紧密链接在邮件存储提供程序内，以便每个对象可以相互影响。</span><span class="sxs-lookup"><span data-stu-id="e47b7-185">The message store logon object and the message store object should be tightly linked inside the message store provider so each can affect the other.</span></span> <span data-ttu-id="e47b7-186">存储对象的使用和登录对象的使用应该相同;登录对象和存储对象之间应该存在一对一的对应关系，这样对象的行为就就像它们是一个公开两个接口的对象一样。</span><span class="sxs-lookup"><span data-stu-id="e47b7-186">The use of the store object and the logon object should be identical; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="e47b7-187">这两个对象也应该一起创建并释放在一起。</span><span class="sxs-lookup"><span data-stu-id="e47b7-187">The two objects should also be created together and freed together.</span></span> 
  
<span data-ttu-id="e47b7-188">MAPI 支持对象（由 MAPI 创建，在  _lpMAPISup_ 参数中传递给提供程序）提供对提供程序所需的 MAPI 中函数的访问。</span><span class="sxs-lookup"><span data-stu-id="e47b7-188">The MAPI support object, created by MAPI and passed to the provider in the  _lpMAPISup_ parameter, provides access to functions in MAPI that the provider requires.</span></span> <span data-ttu-id="e47b7-189">这些功能包括保存和检索配置文件信息、访问通讯簿等功能。</span><span class="sxs-lookup"><span data-stu-id="e47b7-189">These include functions that save and retrieve profile information, access address books, and so on.</span></span> <span data-ttu-id="e47b7-190">对于  _打开的每个存储区，lpMAPISup_ 指针可能不同。</span><span class="sxs-lookup"><span data-stu-id="e47b7-190">The  _lpMAPISup_ pointer can be different for each store that is opened.</span></span> <span data-ttu-id="e47b7-191">在登录后处理邮件存储的调用时，存储提供程序应该使用特定于该存储的  _lpMAPISup_ 变量。</span><span class="sxs-lookup"><span data-stu-id="e47b7-191">While processing calls for a message store after logon, the store provider should use the  _lpMAPISup_ variable that is specific to that store.</span></span> <span data-ttu-id="e47b7-192">对于打开邮件存储并成功创建邮件存储登录对象的任何登录调用，提供程序必须将指向 MAPI 支持对象的指针保存在存储登录对象中，并且必须调用[IUnknown：：AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法来添加对支持对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e47b7-192">For any **Logon** call that opens a message store and succeeds in creating a message store logon object, the provider must save a pointer to the MAPI support object in the store logon object and must call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method to add a reference for the support object.</span></span> 
  
<span data-ttu-id="e47b7-193">如果提供程序在登录调用期间显示对话框，则应该使用 _ulUIParam_ **参数。**</span><span class="sxs-lookup"><span data-stu-id="e47b7-193">The  _ulUIParam_ parameter should be used if the provider presents dialog boxes during the **Logon** call.</span></span> <span data-ttu-id="e47b7-194">但是，如果  _ulFlags_ 包含 MDB_NO_DIALOG 标志，则不应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-194">However, dialog boxes should not be presented if  _ulFlags_ contains the MDB_NO_DIALOG flag.</span></span> <span data-ttu-id="e47b7-195">如果需要调用用户界面但  _ulFlags_ 不允许它，或者由于其他原因无法显示用户界面，则提供程序应返回MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="e47b7-195">If a user interface needs to be called but  _ulFlags_ does not allow it, or if for some other reason a user interface cannot be displayed, the provider should return MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="e47b7-196">如果 **登录** 显示一个对话框，并且用户通常通过单击对话框的"取消"按钮来取消登录，则提供程序应返回MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="e47b7-196">If **Logon** displays a dialog box and the user cancels the logon, typically by clicking the dialog box's **Cancel** button, the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="e47b7-197">_lpEntryID_ 参数可以是 **null，** 也可以指向此邮件存储之前创建的未包装存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e47b7-197">The  _lpEntryID_ parameter can either be **null** or point to an unwrapped store entry identifier that this message store previously created.</span></span> <span data-ttu-id="e47b7-198">如果  _lpEntryID_ 指向未包的条目标识符，该条目标识符可能来自多个位置之一：</span><span class="sxs-lookup"><span data-stu-id="e47b7-198">If  _lpEntryID_ points to an unwrapped entry identifier, that entry identifier can come from one of several places:</span></span> 
  
- <span data-ttu-id="e47b7-199">它可以是存储提供程序之前作为[PidTagEntryId](pidtagentryid-canonical-property.md) PR_ENTRYID (并写到配置文件) 标识符。</span><span class="sxs-lookup"><span data-stu-id="e47b7-199">It can be an entry identifier that the store provider previously wrapped and wrote to the profile section as a **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="e47b7-200">它可以是提供程序之前包装并作为[PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md) PR_STORE_ENTRYID (返回给调用) 标识符。</span><span class="sxs-lookup"><span data-stu-id="e47b7-200">It can be an entry identifier that the provider previously wrapped and returned to a calling client as a **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> 
    
- <span data-ttu-id="e47b7-201">它可以是提供程序之前封装并作为邮件存储对象的 PR_ENTRYID 返回给调用客户端的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e47b7-201">It can be an entry identifier that the provider previously wrapped and returned to a calling client as the **PR_ENTRYID** property of a message store object.</span></span> 
    
<span data-ttu-id="e47b7-202">在任一情况下，条目标识符可能是在不同于当前使用的计算机中创建的。</span><span class="sxs-lookup"><span data-stu-id="e47b7-202">In any of these cases, it is possible that the entry identifier was created on a different computer than the one currently being used.</span></span>
  
<span data-ttu-id="e47b7-203">当  _lpEntryID_ 不 **为 null** 时，它应包含标识和查找邮件存储所需的全部信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-203">When  _lpEntryID_ is not **null**, it should contain all of the information needed to identify and locate the message store.</span></span> <span data-ttu-id="e47b7-204">此信息可能包括网络卷名称、电话号码、用户帐户名等。</span><span class="sxs-lookup"><span data-stu-id="e47b7-204">This information can include network volume names, phone numbers, user account names, and so on.</span></span> <span data-ttu-id="e47b7-205">如果无法使用条目标识符中的数据建立到存储的连接，则存储提供程序应显示一个对话框，允许用户选择要打开的存储区。</span><span class="sxs-lookup"><span data-stu-id="e47b7-205">If the connection to the store cannot be made by using the data in the entry identifier, the store provider should display a dialog box that enables the user to select the store to be opened.</span></span> <span data-ttu-id="e47b7-206">可能需要对话框，例如，如果服务器已重命名、帐户名称已更改或网络部分不可用。</span><span class="sxs-lookup"><span data-stu-id="e47b7-206">A dialog box might be required, for example, if a server has been renamed, an account name has changed, or portions of the network are not available.</span></span>
  
<span data-ttu-id="e47b7-207">当  _lpEntryID_ **为 null** 时，尚未选择使用的邮件存储。</span><span class="sxs-lookup"><span data-stu-id="e47b7-207">When  _lpEntryID_ is **null**, the message store to use has not yet been selected.</span></span> <span data-ttu-id="e47b7-208">如果提供程序支持指定存储的进一步方法，则它仍然可以在不显示对话框的情况下访问存储区。</span><span class="sxs-lookup"><span data-stu-id="e47b7-208">The provider can still access a store without displaying a dialog box if it supports further methods to specify the store.</span></span> <span data-ttu-id="e47b7-209">例如，提供程序可以检查其初始化文件，也可以查找在配置时放置在其邮件服务配置文件部分的其他属性。</span><span class="sxs-lookup"><span data-stu-id="e47b7-209">For example, the provider can check its initialization file, or it can look for additional properties that were placed in its or its message service's profile section at configuration.</span></span>
  
<span data-ttu-id="e47b7-210">如果提供程序发现配置文件中未包含所有必需的信息，则它应返回MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="e47b7-210">If a provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="e47b7-211">然后，MAPI 将调用提供程序的邮件服务入口点函数，以使用户能够选择存储，甚至创建一个存储，并根据需要输入帐户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e47b7-211">MAPI will then call the provider's message service entry point function to enable the user to select a store, or even to create one, and to enter an account name and password, as needed.</span></span> <span data-ttu-id="e47b7-212">MAPI 自动创建新存储的配置文件部分;此新配置文件部分可以是临时的或永久的，具体取决于其添加方式。</span><span class="sxs-lookup"><span data-stu-id="e47b7-212">MAPI automatically creates a new profile section for a new store; this new profile section can be temporary or permanent, depending on how it has been added.</span></span> <span data-ttu-id="e47b7-213">如果存储提供程序调用 **IMAPISupport：：ModifyProfile** 方法，则新的配置文件部分将变为永久性，并且存储将添加到 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法返回的消息存储列表中。</span><span class="sxs-lookup"><span data-stu-id="e47b7-213">If the store provider calls the **IMAPISupport::ModifyProfile** method, the new profile section becomes permanent and the store is added to the list of message stores returned by the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method.</span></span> 
  
<span data-ttu-id="e47b7-214">_lpInterface_ 参数指定新打开的存储区对象所需的接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="e47b7-214">The  _lpInterface_ parameter specifies the IID of the interface required for the newly opened store object.</span></span> <span data-ttu-id="e47b7-215">在 _lpInterface_ 中传递 **null** 指定 MAPI 邮件存储接口 **IMsgStore** 是必需的。</span><span class="sxs-lookup"><span data-stu-id="e47b7-215">Passing **null** in  _lpInterface_ specifies that the MAPI message store interface, **IMsgStore**, is required.</span></span> <span data-ttu-id="e47b7-216">传递邮件存储对象 IID_IMsgStore，还指定 **需要 IMsgStore。**</span><span class="sxs-lookup"><span data-stu-id="e47b7-216">Passing the message store object, IID_IMsgStore, also specifies that **IMsgStore** is required.</span></span> <span data-ttu-id="e47b7-217">如果IID_IUnknown  _lpInterface_ 中传递，则提供程序应该使用从 [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) 派生的任何接口打开存储，这同样 (，这通常是 **IMsgStore**) 。</span><span class="sxs-lookup"><span data-stu-id="e47b7-217">If IID_IUnknown is passed in  _lpInterface_, the provider should open the store by using whatever interface derived from [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) is best for the provider (again, this is typically **IMsgStore**).</span></span> <span data-ttu-id="e47b7-218">传递IID_IUnknown时，调用实现使用 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法在存储打开操作成功后选择接口。</span><span class="sxs-lookup"><span data-stu-id="e47b7-218">When IID_IUnknown is passed, the calling implementation uses the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method to select an interface after the store open operation succeeds.</span></span> 
  
<span data-ttu-id="e47b7-219">**IMSProvider：：Logon** 调用应返回足够的信息，例如存储的路径和用于访问存储的凭据，以允许 MAPI 后台处理程序登录到存储提供程序所登录的同一存储，而不显示对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-219">The **IMSProvider::Logon** call should return sufficient information, such as a path to the store and credentials for accessing the store, to allow the MAPI spooler to log on to the same store that the store provider does without presenting a dialog box.</span></span> <span data-ttu-id="e47b7-220">_lpcbSpoolSecurity_ 和 _lppbSpoolSecurity_ 参数用于返回此信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-220">The  _lpcbSpoolSecurity_ and  _lppbSpoolSecurity_ parameters are used to return this information.</span></span> <span data-ttu-id="e47b7-221">提供程序通过向 [MSProviderInit](msproviderinit.md) 函数的  _lpfAllocateBuffer_ 参数中的缓冲区传递指针来为此数据分配内存;提供程序将此缓冲区的大小设置在  _lpcbSpoolSecurity 中_。</span><span class="sxs-lookup"><span data-stu-id="e47b7-221">The provider allocates the memory for this data by passing a pointer to a buffer in the [MSProviderInit](msproviderinit.md) function's  _lpfAllocateBuffer_ parameter; the provider places the size of this buffer in  _lpcbSpoolSecurity_.</span></span> 
  
<span data-ttu-id="e47b7-222">MAPI 在适当时释放此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e47b7-222">MAPI frees this buffer when appropriate.</span></span> <span data-ttu-id="e47b7-223">如果 MAPI 后台处理程序对存储的登录可以单独通过配置文件部分的信息完成，则提供程序可以在  _lppbSpoolSecurity_ 中返回 null，在  _lpcbSpoolSecurity_ 中为信息大小返回 0。</span><span class="sxs-lookup"><span data-stu-id="e47b7-223">If the MAPI spooler's logon to the store can be accomplished from the information in the profile section alone, the provider can return null in  _lppbSpoolSecurity_ and 0 for the information's size in  _lpcbSpoolSecurity_.</span></span> <span data-ttu-id="e47b7-224">MAPI 后台处理程序登录作为与存储登录不同的过程的一部分进行;由于包含传递信息的缓冲区在进程之间复制，因此它可能不在与存储提供程序进程相同的 MAPI 后台处理程序进程的相同位置的内存中。</span><span class="sxs-lookup"><span data-stu-id="e47b7-224">The MAPI spooler logon occurs as part of a different process than the store logon; because the buffer that contains the passed information gets copied between processes, it might not be in memory at the same location for the MAPI spooler process as for the store provider process.</span></span> <span data-ttu-id="e47b7-225">因此，提供程序不应将地址放入此缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="e47b7-225">Therefore, a provider shouldn't put addresses into this buffer.</span></span> <span data-ttu-id="e47b7-226">有关 MAPI 后台处理程序登录信息，请参阅 [IMSProvider：：SpoolerLogon](imsprovider-spoolerlogon.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-226">For more information about MAPI spooler logon, see the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method.</span></span> 
  
<span data-ttu-id="e47b7-227">大多数存储提供程序使用在 _lpMAPISup_ 参数中传递的支持对象的 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md)方法保存和检索用户凭据和选项。</span><span class="sxs-lookup"><span data-stu-id="e47b7-227">Most store providers use the [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) method of the support object passed in the  _lpMAPISup_ parameter for saving and retrieving user credentials and options.</span></span> <span data-ttu-id="e47b7-228">**OpenProfileSection** 允许存储提供程序在配置文件部分保存其他任意信息，并将其与特定资源关联。</span><span class="sxs-lookup"><span data-stu-id="e47b7-228">**OpenProfileSection** enables a store provider to save additional arbitrary information in a profile section and associate it with a particular resource.</span></span> <span data-ttu-id="e47b7-229">例如，存储提供程序可以保存与资源关联的用户帐户名称和密码以及访问该资源所需的任何路径或其他信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-229">For example, a store provider can save the user account name and password associated with a resource and any paths or other information needed to access that resource.</span></span> 
  
<span data-ttu-id="e47b7-230">属性标识符0x6600属性0x67FF提供程序可以使用的安全属性，供提供程序自行使用以在配置文件节中存储私有数据。</span><span class="sxs-lookup"><span data-stu-id="e47b7-230">Properties with property identifiers 0x6600 through 0x67FF are secure properties available to the provider for its own use to store private data in profile sections.</span></span> <span data-ttu-id="e47b7-231">有关配置文件节对象中属性用法的信息，请参阅 [IProfSect ： IMAPIProp](iprofsectimapiprop.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-231">For more information about the uses of properties in profile section objects, see the [IProfSect : IMAPIProp](iprofsectimapiprop.md) method.</span></span> 
  
<span data-ttu-id="e47b7-232">除了标识符为 0x6600 到 0x67FF 的属性中的任何私有数据外，存储提供程序还应在其配置文件部分提供 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-232">In addition to any private data in properties with identifiers 0x6600 through 0x67FF, the store provider should provide information for the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in its profile section.</span></span> <span data-ttu-id="e47b7-233">它应放在PR_DISPLAY_NAME的 显示名称 中— 向用户显示的标识字符串 (例如，"Microsoft 个人信息存储") ，以便用户可以区分此消息存储与可能有权访问的其他人。</span><span class="sxs-lookup"><span data-stu-id="e47b7-233">It should put in **PR_DISPLAY_NAME** the display name of the provider itself — an identifying string (for example, "Microsoft Personal Information Store") that is displayed to users so they can distinguish this message store from others they might have access to.</span></span> <span data-ttu-id="e47b7-234">**PR_DISPLAY_NAME** 通常包含服务器名称、用户帐户名或路径。</span><span class="sxs-lookup"><span data-stu-id="e47b7-234">**PR_DISPLAY_NAME** commonly contains a server name, user account name, or path.</span></span> 
  
<span data-ttu-id="e47b7-235">某些配置文件节属性在邮件存储表中可见;其他在 MAPI 子系统的安装、安装和配置过程中可见。</span><span class="sxs-lookup"><span data-stu-id="e47b7-235">Some profile section properties are visible in the message store table; others are visible during setup, installation, and configuration of the MAPI subsystem.</span></span> <span data-ttu-id="e47b7-236">通常，提供程序会为新的配置文件节提供这些可见属性的信息，这不包括保存的凭据或私人信息，以及发现属性信息已更改时。</span><span class="sxs-lookup"><span data-stu-id="e47b7-236">The provider typically provides information for these visible properties both for a new profile section, which does not yet include saved credentials or private information, and when it finds that property information has changed.</span></span> <span data-ttu-id="e47b7-237">有关配置文件部分详细信息，请参阅 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md)。</span><span class="sxs-lookup"><span data-stu-id="e47b7-237">For more information about profile sections, see [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md).</span></span>
  
<span data-ttu-id="e47b7-238">成功登录用户后，在返回到 MAPI 之前，存储提供程序应为资源的状态行创建属性数组并调用 [IMAPISupport：：ModifyStatusRow](imapisupport-modifystatusrow.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="e47b7-238">After successfully logging on a user, and before returning to MAPI, the store provider should create the array of properties for the status row for the resource and call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> 
  
 <span data-ttu-id="e47b7-239">**打开** 为当前 MAPI 会话打开的邮件存储的登录调用将跳过之前描述的很多处理。</span><span class="sxs-lookup"><span data-stu-id="e47b7-239">**Logon** calls that open message stores that are already open for the current MAPI session skip much of the processing previously described.</span></span> <span data-ttu-id="e47b7-240">这些调用不会创建状态行、返回邮件存储登录对象、调用 MAPI 支持对象的 **AddRef** 或返回 MAPI 后台处理程序登录的数据。</span><span class="sxs-lookup"><span data-stu-id="e47b7-240">These calls do not create status rows, return message store logon objects, call **AddRef** for the MAPI support object, or return data for MAPI spooler logon.</span></span> <span data-ttu-id="e47b7-241">这些调用会返回S_OK请求的接口返回消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="e47b7-241">These calls do return S_OK and return a message store object with the requested interface.</span></span> 
  
<span data-ttu-id="e47b7-242">若要检测此类调用，提供程序应维护已为此提供程序对象打开的存储区的邮件存储提供程序对象中的列表。</span><span class="sxs-lookup"><span data-stu-id="e47b7-242">To detect such calls, the provider should maintain a list in the message store provider object of stores already open for this provider object.</span></span> <span data-ttu-id="e47b7-243">处理 **登录调用** 时，提供程序应扫描此打开的存储区列表，并确定要登录到的存储区是否已打开。</span><span class="sxs-lookup"><span data-stu-id="e47b7-243">When processing a **Logon** call, the provider should scan this list of open stores and determine whether the store to be logged on to is already open.</span></span> <span data-ttu-id="e47b7-244">如果是，则不需要检查用户凭据，如果可能，应避免显示对话框。</span><span class="sxs-lookup"><span data-stu-id="e47b7-244">If it is, user credentials do not need to be checked and the display of a dialog box should be avoided, if possible.</span></span> <span data-ttu-id="e47b7-245">如果必须显示对话框，提供程序应检查返回的信息，以查看是否已再次打开存储区。</span><span class="sxs-lookup"><span data-stu-id="e47b7-245">If dialog boxes must be displayed, the provider should check returned information to see whether a store has been opened a second time.</span></span> <span data-ttu-id="e47b7-246">此外，提供程序应在登录呼叫处理开始时使用  _lpEntryID_ 检查 **重复** 的打开。</span><span class="sxs-lookup"><span data-stu-id="e47b7-246">In addition, the provider should check for duplicate openings by using  _lpEntryID_ at the beginning of **Logon** call processing.</span></span> 
  
<span data-ttu-id="e47b7-247">访问打开的 **存储区** 的登录调用的标准处理如下：</span><span class="sxs-lookup"><span data-stu-id="e47b7-247">Standard processing for a **Logon** call that accesses an open store is as follows:</span></span> 
  
1. <span data-ttu-id="e47b7-248">如果请求的新接口与现有存储的接口相同，则存储提供程序将调用现有存储对象的 **AddRef。**</span><span class="sxs-lookup"><span data-stu-id="e47b7-248">The store provider calls **AddRef** for the existing store object if the new interface being requested is the same as the interface for the existing store.</span></span> <span data-ttu-id="e47b7-249">否则，它将调用 **QueryInterface** 获取新接口。</span><span class="sxs-lookup"><span data-stu-id="e47b7-249">Otherwise, it calls **QueryInterface** to get the new interface.</span></span> <span data-ttu-id="e47b7-250">如果存储不支持新接口，提供程序应返回错误值MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="e47b7-250">If the store does not support the new interface, the provider should return the error value MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="e47b7-251">提供程序返回一个指针，指向  _lppMDB_ 中现有存储对象的必需接口。</span><span class="sxs-lookup"><span data-stu-id="e47b7-251">The provider returns a pointer to the required interface of the existing store object in  _lppMDB_.</span></span>
    
3. <span data-ttu-id="e47b7-252">提供程序在 _lppMSLogon 中返回 null。_</span><span class="sxs-lookup"><span data-stu-id="e47b7-252">The provider returns **null** in  _lppMSLogon_.</span></span>
    
4. <span data-ttu-id="e47b7-253">提供程序不应打开调用中传递的支持对象的配置文件。</span><span class="sxs-lookup"><span data-stu-id="e47b7-253">The provider should not open the profile for the support object passed in the call.</span></span> <span data-ttu-id="e47b7-254">此外，它不应注册提供程序唯一标识符、注册状态行或返回 MAPI 后台处理程序登录数据。</span><span class="sxs-lookup"><span data-stu-id="e47b7-254">In addition, it should not register a provider unique identifier, register a status row, or return MAPI spooler logon data.</span></span>
    
5. <span data-ttu-id="e47b7-255">提供程序不应为 **支持对象调用 AddRef，** 因为它不需要指向该对象的指针。</span><span class="sxs-lookup"><span data-stu-id="e47b7-255">The provider should not call **AddRef** for the support object, because it does not require a pointer to the object.</span></span> 
    
<span data-ttu-id="e47b7-256">只要有可能，提供程序应为 **登录** 调用返回相应的错误和警告字符串，因为这样做可大大减轻用户在确定某些内容不起作用的原因时的负担。</span><span class="sxs-lookup"><span data-stu-id="e47b7-256">Whenever possible, providers should return appropriate error and warning strings for **Logon** calls, because doing so greatly eases the burden of users in determining why something did not work.</span></span> <span data-ttu-id="e47b7-257">若要返回这些字符串，提供程序将设置 **MAPIERROR** 结构中的成员。</span><span class="sxs-lookup"><span data-stu-id="e47b7-257">To return these strings, a provider sets the members in the **MAPIERROR** structure.</span></span> <span data-ttu-id="e47b7-258">如果 MAPI 由提供程序返回，则查找、使用并释放 **MAPIERROR** 结构。</span><span class="sxs-lookup"><span data-stu-id="e47b7-258">MAPI looks for, uses, and releases the **MAPIERROR** structure if it is returned by a provider.</span></span> 
  
<span data-ttu-id="e47b7-259">此 **MAPIERROR** 结构的内存应通过使用 **在 MSProviderInit** 调用上 _传入 lpfAllocateBuffer_ 的缓冲区进行分配。</span><span class="sxs-lookup"><span data-stu-id="e47b7-259">Memory for this **MAPIERROR** structure should be allocated by using the buffer passed in  _lpfAllocateBuffer_ on the **MSProviderInit** call.</span></span> <span data-ttu-id="e47b7-260">如果在 **Logon** _ulFlags_ 中设置了 MAPI_UNICODE，则返回的结构中包含的任何错误字符串都应采用 Unicode 格式;否则，它们应位于 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="e47b7-260">Any error strings contained in the returned structure should be in Unicode format if MAPI_UNICODE is set in the **Logon** _ulFlags;_ otherwise, they should be in the ANSI character set.</span></span> 
  
<span data-ttu-id="e47b7-261">对于从 **Logon** 返回的多数错误值，MAPI 将禁用失败提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="e47b7-261">For most error values returned from **Logon**, MAPI disables the message services to which the failing provider belongs.</span></span> <span data-ttu-id="e47b7-262">MAPI 在 MAPI 会话的生命周期内不会调用属于这些服务的任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="e47b7-262">MAPI will not call any providers that belong to those services for the life of the MAPI session.</span></span> <span data-ttu-id="e47b7-263">相反，当 **登录** 从MAPI_E_FAILONEPROVIDER返回错误值时，MAPI 不会禁用提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="e47b7-263">In contrast, when **Logon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="e47b7-264">**如果** 登录MAPI_E_FAILONEPROVIDER如果遇到一个错误，而该错误不保证在会话的整个生命周期内禁用整个服务，则应该返回此状态。</span><span class="sxs-lookup"><span data-stu-id="e47b7-264">**Logon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the entire service for the life of the session.</span></span> <span data-ttu-id="e47b7-265">例如，如果提供程序不允许显示用户界面并且所需的密码不可用，则提供程序可能会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="e47b7-265">For example, a provider might return this error when it does not allow the display of a user interface and a required password is unavailable.</span></span> 
  
<span data-ttu-id="e47b7-266">如果提供程序从MAPI_E_UNCONFIGURED返回消息，MAPI 将调用提供程序的邮件服务条目函数，然后重试登录。</span><span class="sxs-lookup"><span data-stu-id="e47b7-266">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="e47b7-267">MAPI 将MSG_SERVICE_CONFIGURE作为上下文传递，为服务提供自行配置的机会。</span><span class="sxs-lookup"><span data-stu-id="e47b7-267">MAPI passes MSG_SERVICE_CONFIGURE as the context to give the service a chance to configure itself.</span></span> <span data-ttu-id="e47b7-268">如果客户端已选择允许在登录时使用用户界面，该服务可以显示其配置属性表以便用户输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="e47b7-268">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so the user can enter configuration information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e47b7-269">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e47b7-269">See also</span></span>



[<span data-ttu-id="e47b7-270">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="e47b7-270">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="e47b7-271">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="e47b7-271">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="e47b7-272">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="e47b7-272">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="e47b7-273">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="e47b7-273">IMAPISupport::ModifyProfile</span></span>](imapisupport-modifyprofile.md)
  
[<span data-ttu-id="e47b7-274">IMAPISupport::ModifyStatusRow</span><span class="sxs-lookup"><span data-stu-id="e47b7-274">IMAPISupport::ModifyStatusRow</span></span>](imapisupport-modifystatusrow.md)
  
[<span data-ttu-id="e47b7-275">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e47b7-275">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
  
[<span data-ttu-id="e47b7-276">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="e47b7-276">IMSProvider::SpoolerLogon</span></span>](imsprovider-spoolerlogon.md)
  
[<span data-ttu-id="e47b7-277">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="e47b7-277">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="e47b7-278">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="e47b7-278">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="e47b7-279">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="e47b7-279">MSProviderInit</span></span>](msproviderinit.md)
  
[<span data-ttu-id="e47b7-280">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e47b7-280">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

