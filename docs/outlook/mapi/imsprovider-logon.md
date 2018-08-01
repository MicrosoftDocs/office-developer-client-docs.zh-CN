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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b89c8129f68852bdd243a7f984497ab312aa2551
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775948"
---
# <a name="imsproviderlogon"></a><span data-ttu-id="b56f9-103">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="b56f9-103">IMSProvider::Logon</span></span>

  
  
<span data-ttu-id="b56f9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b56f9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b56f9-105">日志 MAPI 到消息存储提供程序的一个实例。</span><span class="sxs-lookup"><span data-stu-id="b56f9-105">Logs MAPI on to one instance of a message store provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="b56f9-106">参数</span><span class="sxs-lookup"><span data-stu-id="b56f9-106">Parameters</span></span>

 <span data-ttu-id="b56f9-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="b56f9-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="b56f9-108">[in]一个指向当前的 MAPI 支持的消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-108">[in] A pointer to the current MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="b56f9-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b56f9-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="b56f9-110">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="b56f9-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="b56f9-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="b56f9-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="b56f9-112">[in]一个指向一个字符串，包含要用于存储提供程序登录的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b56f9-112">[in] A pointer to a string that contains the name of the profile being used for store provider logon.</span></span> <span data-ttu-id="b56f9-113">可以显示在对话框中，写入日志文件，或只忽略此字符串。</span><span class="sxs-lookup"><span data-stu-id="b56f9-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="b56f9-114">如果_ulFlags_参数中设置 MAPI_UNICODE 标志，它必须是以 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b56f9-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b56f9-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b56f9-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="b56f9-116">[in]以字节为单位_lpEntryID_参数指向的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="b56f9-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b56f9-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b56f9-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="b56f9-118">[in]指向消息存储库的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="b56f9-119">_LpEntryID_中传递**null**指示尚未选择的消息存储，并且可以提供让用户能够选择的消息存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="b56f9-119">Passing **null** in  _lpEntryID_ indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="b56f9-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b56f9-120">_ulFlags_</span></span>
  
> <span data-ttu-id="b56f9-121">[in]位掩码的标志，控制如何执行登录。</span><span class="sxs-lookup"><span data-stu-id="b56f9-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="b56f9-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b56f9-122">The following flags can be set:</span></span>
    
<span data-ttu-id="b56f9-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="b56f9-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="b56f9-124">若要成功执行，即使基础对象不可用的呼叫的实现，即允许该呼叫。</span><span class="sxs-lookup"><span data-stu-id="b56f9-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="b56f9-125">如果对象不可用，对对象的后续调用可能会引发一个错误。</span><span class="sxs-lookup"><span data-stu-id="b56f9-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="b56f9-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b56f9-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b56f9-127">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b56f9-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="b56f9-128">如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b56f9-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="b56f9-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="b56f9-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="b56f9-130">阻止登录对话框的显示。</span><span class="sxs-lookup"><span data-stu-id="b56f9-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="b56f9-131">如果设置此标志，如果登录失败，则返回错误值 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="b56f9-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="b56f9-132">如果未设置此标志，消息存储提供程序可以提示用户正确的名称或密码，插入磁盘，或执行其他操作所需建立连接到存储区。</span><span class="sxs-lookup"><span data-stu-id="b56f9-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions that are necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="b56f9-133">MDB_NO_MAIL</span><span class="sxs-lookup"><span data-stu-id="b56f9-133">MDB_NO_MAIL</span></span> 
  
> <span data-ttu-id="b56f9-134">消息存储不应用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="b56f9-134">The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="b56f9-135">标志信号 MAPI 不以通知 MAPI 后台处理程序打开的时此消息存储。</span><span class="sxs-lookup"><span data-stu-id="b56f9-135">The flag signals MAPI not to notify the MAPI spooler that this message store is being opened.</span></span> <span data-ttu-id="b56f9-136">如果设置此标志，与传输提供程序紧密耦合的消息存储，则不需要调用[IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md)方法提供程序。</span><span class="sxs-lookup"><span data-stu-id="b56f9-136">If this flag is set and the message store is tightly coupled with a transport provider, the provider does not need to call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> 
    
<span data-ttu-id="b56f9-137">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="b56f9-137">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="b56f9-138">对存储日志，以便从配置文件部分中，以编程方式检索信息不使用的对话框。</span><span class="sxs-lookup"><span data-stu-id="b56f9-138">Logs on the store so that information can be retrieved programmatically from the profile section, without use of dialog boxes.</span></span> <span data-ttu-id="b56f9-139">此标志指示 MAPI 存储是不是要添加到消息存储表和存储无法进行永久。</span><span class="sxs-lookup"><span data-stu-id="b56f9-139">This flag instructs MAPI that the store is not to be added to the message store table and that the store cannot be made permanent.</span></span> <span data-ttu-id="b56f9-140">如果设置此标志，消息存储提供程序不需要调用[IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b56f9-140">If this flag is set, message store providers do not need to call the [IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md) method.</span></span> 
    
<span data-ttu-id="b56f9-141">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="b56f9-141">MDB_WRITE</span></span> 
  
> <span data-ttu-id="b56f9-142">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="b56f9-142">Requests read/write permission.</span></span>
    
 <span data-ttu-id="b56f9-143">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="b56f9-143">_lpInterface_</span></span>
  
> <span data-ttu-id="b56f9-144">[in]指向要登录到的邮件存储区的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-144">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="b56f9-145">传递**null**指示返回的消息存储 ( [IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 界面。</span><span class="sxs-lookup"><span data-stu-id="b56f9-145">Passing **null** indicates the MAPI interface for the message store ( [IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="b56f9-146">_LpInterface_参数还可以设置为消息存储 （例如，IID_IUnknown 或 IID_IMAPIProp） 的适当的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="b56f9-146">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example, IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="b56f9-147">_lpcbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="b56f9-147">_lpcbSpoolSecurity_</span></span>
  
> <span data-ttu-id="b56f9-148">[输出]指向在其中存储提供程序返回的大小，以字节为单位的_lppbSpoolSecurity_参数中的验证数据变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-148">[out] A pointer to the variable in which the store provider returns the size, in bytes, of the validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="b56f9-149">_lppbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="b56f9-149">_lppbSpoolSecurity_</span></span>
  
> <span data-ttu-id="b56f9-150">[输出]指向该指针指向返回的验证数据的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-150">[out] A pointer to the pointer to the returned validation data.</span></span> <span data-ttu-id="b56f9-151">以便[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法可以登录到同一个存储 MAPI 后台处理程序的消息存储提供程序提供此验证数据。</span><span class="sxs-lookup"><span data-stu-id="b56f9-151">This validation data is provided so the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method can log the MAPI spooler on to the same store as the message store provider.</span></span> 
    
 <span data-ttu-id="b56f9-152">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="b56f9-152">_lppMAPIError_</span></span>
  
> <span data-ttu-id="b56f9-153">[输出]指向返回[MAPIERROR](mapierror.md)结构，如果有，其中包含的错误的版本、 组件及上下文信息的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-153">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="b56f9-154">如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为**null** 。</span><span class="sxs-lookup"><span data-stu-id="b56f9-154">The  _lppMAPIError_ parameter can be set to **null** if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="b56f9-155">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="b56f9-155">_lppMSLogon_</span></span>
  
> <span data-ttu-id="b56f9-156">[输出]指向该指针指向邮件存储 MAPI 登录到的登录对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-156">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="b56f9-157">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="b56f9-157">_lppMDB_</span></span>
  
> <span data-ttu-id="b56f9-158">[输出]指向该指针指向邮件存储 MAPI 后台处理程序和客户端应用程序登录到的对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-158">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="b56f9-159">返回值</span><span class="sxs-lookup"><span data-stu-id="b56f9-159">Return value</span></span>

<span data-ttu-id="b56f9-160">S_OK</span><span class="sxs-lookup"><span data-stu-id="b56f9-160">S_OK</span></span> 
  
> <span data-ttu-id="b56f9-161">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="b56f9-161">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="b56f9-162">MAPI_E_FAILONEPROVIDER</span><span class="sxs-lookup"><span data-stu-id="b56f9-162">MAPI_E_FAILONEPROVIDER</span></span> 
  
> <span data-ttu-id="b56f9-163">此提供程序不能登录，但不是服务应禁用此错误。</span><span class="sxs-lookup"><span data-stu-id="b56f9-163">This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="b56f9-164">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="b56f9-164">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="b56f9-165">无法建立登录会话。</span><span class="sxs-lookup"><span data-stu-id="b56f9-165">A logon session could not be established.</span></span>
    
<span data-ttu-id="b56f9-166">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="b56f9-166">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="b56f9-167">配置文件不包含登录后，若要完成的足够信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-167">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="b56f9-168">返回此值时，MAPI 调用的消息存储提供程序的消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="b56f9-168">When this value is returned, MAPI calls the message store provider's message-service entry point function.</span></span>
    
<span data-ttu-id="b56f9-169">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="b56f9-169">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="b56f9-170">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="b56f9-170">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="b56f9-171">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="b56f9-171">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="b56f9-172">将服务器不配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="b56f9-172">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="b56f9-173">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="b56f9-173">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="b56f9-174">将服务器不配置为支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-174">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="b56f9-175">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="b56f9-175">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="b56f9-176">调用成功，但消息存储提供程序已经可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-176">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="b56f9-177">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="b56f9-177">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="b56f9-178">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="b56f9-178">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="b56f9-179">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="b56f9-179">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="b56f9-180">要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b56f9-180">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b56f9-181">说明</span><span class="sxs-lookup"><span data-stu-id="b56f9-181">Remarks</span></span>

<span data-ttu-id="b56f9-182">MAPI 调用**IMSProvider::Logon**方法执行大部分获取的消息存储访问所需的处理。</span><span class="sxs-lookup"><span data-stu-id="b56f9-182">MAPI calls the **IMSProvider::Logon** method to do the majority of processing necessary to obtain access to a message store.</span></span> <span data-ttu-id="b56f9-183">消息存储提供程序验证任何需要访问特定存储和 MAPI 后台处理程序和客户端应用程序可以登录到_lppMDB_参数中返回的消息存储对象的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="b56f9-183">Message store providers validate any user credentials necessary to access a particular store and return a message store object in the  _lppMDB_ parameter that the MAPI spooler and client applications can log on to.</span></span> 
  
<span data-ttu-id="b56f9-184">除了为客户端和 MAPI 后台处理程序使用返回的消息存储对象，提供程序也会返回 MAPI 用于控制在打开的存储的消息存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-184">In addition to the returned message store object for client and MAPI spooler use, the provider also returns a message store logon object for MAPI to use in controlling the opened store.</span></span> <span data-ttu-id="b56f9-185">消息存储登录对象和消息存储对象应紧密链接内的消息存储提供程序以便如何影响其他。</span><span class="sxs-lookup"><span data-stu-id="b56f9-185">The message store logon object and the message store object should be tightly linked inside the message store provider so each can affect the other.</span></span> <span data-ttu-id="b56f9-186">使用的存储对象和登录对象应相同;应一一对应登录对象之间的存储对象，以便对象就像它们是公开两个接口的一个对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-186">The use of the store object and the logon object should be identical; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="b56f9-187">两个对象应还创建组合在一起和释放在一起。</span><span class="sxs-lookup"><span data-stu-id="b56f9-187">The two objects should also be created together and freed together.</span></span> 
  
<span data-ttu-id="b56f9-188">MAPI 支持对象，由 MAPI 和传递给_lpMAPISup_参数中的提供程序提供访问的提供程序需要的 MAPI 中的功能。</span><span class="sxs-lookup"><span data-stu-id="b56f9-188">The MAPI support object, created by MAPI and passed to the provider in the  _lpMAPISup_ parameter, provides access to functions in MAPI that the provider requires.</span></span> <span data-ttu-id="b56f9-189">包括函数的保存和检索配置文件信息、 访问通讯簿，等等。</span><span class="sxs-lookup"><span data-stu-id="b56f9-189">These include functions that save and retrieve profile information, access address books, and so on.</span></span> <span data-ttu-id="b56f9-190">_LpMAPISup_指针可以打开每个存储的不同。</span><span class="sxs-lookup"><span data-stu-id="b56f9-190">The  _lpMAPISup_ pointer can be different for each store that is opened.</span></span> <span data-ttu-id="b56f9-191">时处理呼叫消息存储登录后，存储提供程序应使用的特定于存储_lpMAPISup_变量。</span><span class="sxs-lookup"><span data-stu-id="b56f9-191">While processing calls for a message store after logon, the store provider should use the  _lpMAPISup_ variable that is specific to that store.</span></span> <span data-ttu-id="b56f9-192">提供程序的任何**登录**调用，以打开的消息存储并成功创建消息存储登录对象，必须将指针保存到存储登录对象中的 MAPI 支持对象和必须调用[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)方法添加的引用支持的对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-192">For any **Logon** call that opens a message store and succeeds in creating a message store logon object, the provider must save a pointer to the MAPI support object in the store logon object and must call the [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx) method to add a reference for the support object.</span></span> 
  
<span data-ttu-id="b56f9-193">如果提供程序**登录**呼叫期间显示对话框，则应使用_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="b56f9-193">The  _ulUIParam_ parameter should be used if the provider presents dialog boxes during the **Logon** call.</span></span> <span data-ttu-id="b56f9-194">但是，如果_ulFlags_包含 MDB_NO_DIALOG 标志应不显示对话框。</span><span class="sxs-lookup"><span data-stu-id="b56f9-194">However, dialog boxes should not be presented if  _ulFlags_ contains the MDB_NO_DIALOG flag.</span></span> <span data-ttu-id="b56f9-195">如果用户界面需要调用但_ulFlags_不允许使用它，或者如果其他原因无法显示用户界面，提供程序应返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="b56f9-195">If a user interface needs to be called but  _ulFlags_ does not allow it, or if for some other reason a user interface cannot be displayed, the provider should return MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="b56f9-196">如果**登录**显示一个对话框，并且用户取消了登录，通常通过单击对话框的**取消**按钮，提供程序应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="b56f9-196">If **Logon** displays a dialog box and the user cancels the logon, typically by clicking the dialog box's **Cancel** button, the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="b56f9-197">_LpEntryID_参数可以为**null**或指向解包的存储项的标识符此消息存储以前创建的。</span><span class="sxs-lookup"><span data-stu-id="b56f9-197">The  _lpEntryID_ parameter can either be **null** or point to an unwrapped store entry identifier that this message store previously created.</span></span> <span data-ttu-id="b56f9-198">如果_lpEntryID_指向解包的条目标识符，该条目标识符可来自多个位置之一：</span><span class="sxs-lookup"><span data-stu-id="b56f9-198">If  _lpEntryID_ points to an unwrapped entry identifier, that entry identifier can come from one of several places:</span></span> 
  
- <span data-ttu-id="b56f9-199">它可以是存储提供程序以前自动换行，并记作为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性配置文件一节的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b56f9-199">It can be an entry identifier that the store provider previously wrapped and wrote to the profile section as a **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="b56f9-200">它可以是提供程序以前自动换行，并返回到**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性以调用客户端的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b56f9-200">It can be an entry identifier that the provider previously wrapped and returned to a calling client as a **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> 
    
- <span data-ttu-id="b56f9-201">它可以是提供程序以前自动换行，并作为消息存储对象的**PR_ENTRYID**属性返回到调用客户端的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b56f9-201">It can be an entry identifier that the provider previously wrapped and returned to a calling client as the **PR_ENTRYID** property of a message store object.</span></span> 
    
<span data-ttu-id="b56f9-202">在上述任一情况下，很可能比当前正在使用不同的计算机上创建的项标识符的。</span><span class="sxs-lookup"><span data-stu-id="b56f9-202">In any of these cases, it is possible that the entry identifier was created on a different computer than the one currently being used.</span></span>
  
<span data-ttu-id="b56f9-203">当_lpEntryID_不**为 null**时，它应包含所有所需确定并找到消息存储库的信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-203">When  _lpEntryID_ is not **null**, it should contain all of the information needed to identify and locate the message store.</span></span> <span data-ttu-id="b56f9-204">此信息可以包括网络卷名称、 电话号码、 用户帐户名和等等。</span><span class="sxs-lookup"><span data-stu-id="b56f9-204">This information can include network volume names, phone numbers, user account names, and so on.</span></span> <span data-ttu-id="b56f9-205">如果无法建立到商店连接，通过使用中的项标识符的数据，存储提供程序应显示一个对话框，使用户能够选择要打开的存储。</span><span class="sxs-lookup"><span data-stu-id="b56f9-205">If the connection to the store cannot be made by using the data in the entry identifier, the store provider should display a dialog box that enables the user to select the store to be opened.</span></span> <span data-ttu-id="b56f9-206">一个对话框，可能需要，例如，如果已重命名服务器、 已更改的帐户名称，或网络的部分不可用。</span><span class="sxs-lookup"><span data-stu-id="b56f9-206">A dialog box might be required, for example, if a server has been renamed, an account name has changed, or portions of the network are not available.</span></span>
  
<span data-ttu-id="b56f9-207">**Null** _lpEntryID_后，要使用的消息存储具有尚未选择。</span><span class="sxs-lookup"><span data-stu-id="b56f9-207">When  _lpEntryID_ is **null**, the message store to use has not yet been selected.</span></span> <span data-ttu-id="b56f9-208">提供程序仍可以访问存储区，而不显示一个对话框，如果它支持进一步的方法，以指定的存储。</span><span class="sxs-lookup"><span data-stu-id="b56f9-208">The provider can still access a store without displaying a dialog box if it supports further methods to specify the store.</span></span> <span data-ttu-id="b56f9-209">例如，提供程序可以检查其初始化文件，或者它可以查找放置在其或其消息服务的配置文件配置处的一节中的其他属性。</span><span class="sxs-lookup"><span data-stu-id="b56f9-209">For example, the provider can check its initialization file, or it can look for additional properties that were placed in its or its message service's profile section at configuration.</span></span>
  
<span data-ttu-id="b56f9-210">如果提供程序查找所有所需的信息不在配置文件中，则应返回 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="b56f9-210">If a provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="b56f9-211">MAPI 将呼叫提供商的消息服务入口点函数以允许用户选择一个存储区，或甚至创建一个，并以输入帐户名和密码，需要。</span><span class="sxs-lookup"><span data-stu-id="b56f9-211">MAPI will then call the provider's message service entry point function to enable the user to select a store, or even to create one, and to enter an account name and password, as needed.</span></span> <span data-ttu-id="b56f9-212">MAPI 将自动创建新的存储; 新配置文件节本节新配置文件可以是临时或永久，具体取决于添加的方式。</span><span class="sxs-lookup"><span data-stu-id="b56f9-212">MAPI automatically creates a new profile section for a new store; this new profile section can be temporary or permanent, depending on how it has been added.</span></span> <span data-ttu-id="b56f9-213">如果存储提供程序调用**IMAPISupport::ModifyProfile**方法时，新的配置文件部分会成为永久性并存储添加到[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法返回的消息存储的列表。</span><span class="sxs-lookup"><span data-stu-id="b56f9-213">If the store provider calls the **IMAPISupport::ModifyProfile** method, the new profile section becomes permanent and the store is added to the list of message stores returned by the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method.</span></span> 
  
<span data-ttu-id="b56f9-214">_LpInterface_参数指定新打开的存储对象所需的接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="b56f9-214">The  _lpInterface_ parameter specifies the IID of the interface required for the newly opened store object.</span></span> <span data-ttu-id="b56f9-215">在_lpInterface_传递**null**指定 MAPI 消息存储接口， **IMsgStore**，都要求。</span><span class="sxs-lookup"><span data-stu-id="b56f9-215">Passing **null** in  _lpInterface_ specifies that the MAPI message store interface, **IMsgStore**, is required.</span></span> <span data-ttu-id="b56f9-216">传递消息存储对象，IID_IMsgStore，还指定**IMsgStore**都要求。</span><span class="sxs-lookup"><span data-stu-id="b56f9-216">Passing the message store object, IID_IMsgStore, also specifies that **IMsgStore** is required.</span></span> <span data-ttu-id="b56f9-217">如果在_lpInterface_传递 IID_IUnknown，则提供程序应使用的任何接口派生打开存储[IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)是最适用于提供程序 （同样，这通常是**IMsgStore**）。</span><span class="sxs-lookup"><span data-stu-id="b56f9-217">If IID_IUnknown is passed in  _lpInterface_, the provider should open the store by using whatever interface derived from [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx) is best for the provider (again, this is typically **IMsgStore**).</span></span> <span data-ttu-id="b56f9-218">当 IID_IUnknown 传递时，调用实现使用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)方法存储打开操作成功后，选择一个接口。</span><span class="sxs-lookup"><span data-stu-id="b56f9-218">When IID_IUnknown is passed, the calling implementation uses the [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx) method to select an interface after the store open operation succeeds.</span></span> 
  
<span data-ttu-id="b56f9-219">**IMSProvider::Logon**呼叫应返回足够的信息，如存储和访问的存储，以允许 MAPI 后台处理程序登录到的存储提供程序实现，而无演示对话框中的同一存储的凭据的路径。</span><span class="sxs-lookup"><span data-stu-id="b56f9-219">The **IMSProvider::Logon** call should return sufficient information, such as a path to the store and credentials for accessing the store, to allow the MAPI spooler to log on to the same store that the store provider does without presenting a dialog box.</span></span> <span data-ttu-id="b56f9-220">在_lpcbSpoolSecurity_和_lppbSpoolSecurity_参数用于返回此信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-220">The  _lpcbSpoolSecurity_ and  _lppbSpoolSecurity_ parameters are used to return this information.</span></span> <span data-ttu-id="b56f9-221">提供程序通过将指针传递到的缓冲区中的[MSProviderInit](msproviderinit.md)函数_lpfAllocateBuffer_参数，则此数据分配的内存提供程序置于_lpcbSpoolSecurity_此缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="b56f9-221">The provider allocates the memory for this data by passing a pointer to a buffer in the [MSProviderInit](msproviderinit.md) function's  _lpfAllocateBuffer_ parameter; the provider places the size of this buffer in  _lpcbSpoolSecurity_.</span></span> 
  
<span data-ttu-id="b56f9-222">MAPI 释放时相应此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b56f9-222">MAPI frees this buffer when appropriate.</span></span> <span data-ttu-id="b56f9-223">如果表达配置文件部分中的信息，可以通过 MAPI 后台处理程序的登录到存储区，提供程序可以返回 null _lppbSpoolSecurity_和信息的大小以_lpcbSpoolSecurity_0 中。</span><span class="sxs-lookup"><span data-stu-id="b56f9-223">If the MAPI spooler's logon to the store can be accomplished from the information in the profile section alone, the provider can return null in  _lppbSpoolSecurity_ and 0 for the information's size in  _lpcbSpoolSecurity_.</span></span> <span data-ttu-id="b56f9-224">MAPI 后台处理程序登录发生不同于存储登录; 进程的一部分包含传递的信息的缓冲区获取进程之间复制的因为它可能不是内存存储提供程序进程相同的 MAPI 后台处理程序过程的相同位置中。</span><span class="sxs-lookup"><span data-stu-id="b56f9-224">The MAPI spooler logon occurs as part of a different process than the store logon; because the buffer that contains the passed information gets copied between processes, it might not be in memory at the same location for the MAPI spooler process as for the store provider process.</span></span> <span data-ttu-id="b56f9-225">因此，提供程序不应将地址放入此缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="b56f9-225">Therefore, a provider shouldn't put addresses into this buffer.</span></span> <span data-ttu-id="b56f9-226">有关 MAPI 后台处理程序登录的详细信息，请参阅[IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b56f9-226">For more information about MAPI spooler logon, see the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method.</span></span> 
  
<span data-ttu-id="b56f9-227">大多数存储提供程序使用[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)方法保存和检索用户凭据和选项的_lpMAPISup_参数中传递的支持对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-227">Most store providers use the [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) method of the support object passed in the  _lpMAPISup_ parameter for saving and retrieving user credentials and options.</span></span> <span data-ttu-id="b56f9-228">**OpenProfileSection**使存储提供程序配置文件节中保存任意的其他信息，并将其与特定的资源关联。</span><span class="sxs-lookup"><span data-stu-id="b56f9-228">**OpenProfileSection** enables a store provider to save additional arbitrary information in a profile section and associate it with a particular resource.</span></span> <span data-ttu-id="b56f9-229">例如，存储提供程序可以保存的用户帐户名和密码与资源和任何路径或访问该资源所需的其他信息关联。</span><span class="sxs-lookup"><span data-stu-id="b56f9-229">For example, a store provider can save the user account name and password associated with a resource and any paths or other information needed to access that resource.</span></span> 
  
<span data-ttu-id="b56f9-230">使用属性标识符通过 0x67FF 0x6600 属性是供自己使用配置文件各节中存储私有数据提供程序的安全属性。</span><span class="sxs-lookup"><span data-stu-id="b56f9-230">Properties with property identifiers 0x6600 through 0x67FF are secure properties available to the provider for its own use to store private data in profile sections.</span></span> <span data-ttu-id="b56f9-231">有关使用配置文件部分对象中的属性的详细信息，请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b56f9-231">For more information about the uses of properties in profile section objects, see the [IProfSect : IMAPIProp](iprofsectimapiprop.md) method.</span></span> 
  
<span data-ttu-id="b56f9-232">除了使用标识符通过 0x67FF 0x6600 属性中的任何私有数据，存储提供程序应提供其配置文件一节中**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-232">In addition to any private data in properties with identifiers 0x6600 through 0x67FF, the store provider should provide information for the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in its profile section.</span></span> <span data-ttu-id="b56f9-233">它应置于**PR_DISPLAY_NAME**本身的提供程序的显示名称 — 标识字符串 （例如，"Microsoft 个人信息存储"），它们可以将此消息存储与其他人区分开来以便向用户显示他们可能具有访问权限自。</span><span class="sxs-lookup"><span data-stu-id="b56f9-233">It should put in **PR_DISPLAY_NAME** the display name of the provider itself — an identifying string (for example, "Microsoft Personal Information Store") that is displayed to users so they can distinguish this message store from others they might have access to.</span></span> <span data-ttu-id="b56f9-234">**PR_DISPLAY_NAME**通常包含服务器名称、 用户帐户名称或路径。</span><span class="sxs-lookup"><span data-stu-id="b56f9-234">**PR_DISPLAY_NAME** commonly contains a server name, user account name, or path.</span></span> 
  
<span data-ttu-id="b56f9-235">可以看到消息存储表; 中一些配置文件的部分属性其他人都能看到期间安装程序、 安装和配置的 MAPI 子系统。</span><span class="sxs-lookup"><span data-stu-id="b56f9-235">Some profile section properties are visible in the message store table; others are visible during setup, installation, and configuration of the MAPI subsystem.</span></span> <span data-ttu-id="b56f9-236">提供程序通常提供新的配置文件节，其尚未包含保存的凭据或私人信息和时它查找属性信息已更改这些可见属性这两个的信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-236">The provider typically provides information for these visible properties both for a new profile section, which does not yet include saved credentials or private information, and when it finds that property information has changed.</span></span> <span data-ttu-id="b56f9-237">有关配置文件节的详细信息，请参阅[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)。</span><span class="sxs-lookup"><span data-stu-id="b56f9-237">For more information about profile sections, see [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md).</span></span>
  
<span data-ttu-id="b56f9-238">成功登录用户和 MAPI 向返回之前之后, 的存储提供程序应创建的资源的状态行属性数组，并调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b56f9-238">After successfully logging on a user, and before returning to MAPI, the store provider should create the array of properties for the status row for the resource and call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> 
  
 <span data-ttu-id="b56f9-239">打开当前的 MAPI 会话已打开的消息存储的**登录**呼叫跳过何种前面所述的处理。</span><span class="sxs-lookup"><span data-stu-id="b56f9-239">**Logon** calls that open message stores that are already open for the current MAPI session skip much of the processing previously described.</span></span> <span data-ttu-id="b56f9-240">这些呼叫不要创建状态行、 返回消息存储登录对象，对于 MAPI 支持对象，调用**AddRef**或 MAPI 后台处理程序登录为返回数据。</span><span class="sxs-lookup"><span data-stu-id="b56f9-240">These calls do not create status rows, return message store logon objects, call **AddRef** for the MAPI support object, or return data for MAPI spooler logon.</span></span> <span data-ttu-id="b56f9-241">这些呼叫执行返回 S_OK 和返回与请求的接口的消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="b56f9-241">These calls do return S_OK and return a message store object with the requested interface.</span></span> 
  
<span data-ttu-id="b56f9-242">若要检测此类呼叫，提供程序应该中存储的消息存储提供程序对象的列表为此提供程序对象已打开。</span><span class="sxs-lookup"><span data-stu-id="b56f9-242">To detect such calls, the provider should maintain a list in the message store provider object of stores already open for this provider object.</span></span> <span data-ttu-id="b56f9-243">处理时**登录**呼叫，提供程序应扫描打开存储此列表，并确定要登录到的存储是否已打开。</span><span class="sxs-lookup"><span data-stu-id="b56f9-243">When processing a **Logon** call, the provider should scan this list of open stores and determine whether the store to be logged on to is already open.</span></span> <span data-ttu-id="b56f9-244">如果是，用户凭据不需要检查并显示一个对话框，应避免，如果可能。</span><span class="sxs-lookup"><span data-stu-id="b56f9-244">If it is, user credentials do not need to be checked and the display of a dialog box should be avoided, if possible.</span></span> <span data-ttu-id="b56f9-245">如果必须显示对话框，提供程序应检查返回的信息，以查看是否已打开存储第二次。</span><span class="sxs-lookup"><span data-stu-id="b56f9-245">If dialog boxes must be displayed, the provider should check returned information to see whether a store has been opened a second time.</span></span> <span data-ttu-id="b56f9-246">此外，提供程序应检查重复开口**登录**呼叫的开头使用_lpEntryID_处理。</span><span class="sxs-lookup"><span data-stu-id="b56f9-246">In addition, the provider should check for duplicate openings by using  _lpEntryID_ at the beginning of **Logon** call processing.</span></span> 
  
<span data-ttu-id="b56f9-247">标准**登录**呼叫访问打开存储处理如下所示：</span><span class="sxs-lookup"><span data-stu-id="b56f9-247">Standard processing for a **Logon** call that accesses an open store is as follows:</span></span> 
  
1. <span data-ttu-id="b56f9-248">存储提供程序为现有的存储对象调用**AddRef** ，如果正在请求的新接口是与现有的存储的界面相同。</span><span class="sxs-lookup"><span data-stu-id="b56f9-248">The store provider calls **AddRef** for the existing store object if the new interface being requested is the same as the interface for the existing store.</span></span> <span data-ttu-id="b56f9-249">否则，它将调用**QueryInterface**获取新接口。</span><span class="sxs-lookup"><span data-stu-id="b56f9-249">Otherwise, it calls **QueryInterface** to get the new interface.</span></span> <span data-ttu-id="b56f9-250">如果存储区不支持新的界面，提供程序应返回错误值 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="b56f9-250">If the store does not support the new interface, the provider should return the error value MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="b56f9-251">提供程序返回到_lppMDB_中的现有存储对象的所需的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-251">The provider returns a pointer to the required interface of the existing store object in  _lppMDB_.</span></span>
    
3. <span data-ttu-id="b56f9-252">提供程序在_lppMSLogon_返回**null** 。</span><span class="sxs-lookup"><span data-stu-id="b56f9-252">The provider returns **null** in  _lppMSLogon_.</span></span>
    
4. <span data-ttu-id="b56f9-253">提供程序不应打开传入呼叫的支持对象的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b56f9-253">The provider should not open the profile for the support object passed in the call.</span></span> <span data-ttu-id="b56f9-254">此外，它不应注册提供程序的唯一标识符，注册一个状态行中，或返回登录数据的 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="b56f9-254">In addition, it should not register a provider unique identifier, register a status row, or return MAPI spooler logon data.</span></span>
    
5. <span data-ttu-id="b56f9-255">提供程序不应支持对象中，调用**AddRef** ，因为它不需要对对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b56f9-255">The provider should not call **AddRef** for the support object, because it does not require a pointer to the object.</span></span> 
    
<span data-ttu-id="b56f9-256">只要有可能，提供程序应返回相应的错误和警告字符串**登录**呼叫，因为这样做会显著可减轻负担中确定为什么内容无法正常工作的用户。</span><span class="sxs-lookup"><span data-stu-id="b56f9-256">Whenever possible, providers should return appropriate error and warning strings for **Logon** calls, because doing so greatly eases the burden of users in determining why something did not work.</span></span> <span data-ttu-id="b56f9-257">若要返回这些字符串，提供程序设置**MAPIERROR**结构中的成员。</span><span class="sxs-lookup"><span data-stu-id="b56f9-257">To return these strings, a provider sets the members in the **MAPIERROR** structure.</span></span> <span data-ttu-id="b56f9-258">MAPI 查找和使用，如果提供程序返回释放**MAPIERROR**结构。</span><span class="sxs-lookup"><span data-stu-id="b56f9-258">MAPI looks for, uses, and releases the **MAPIERROR** structure if it is returned by a provider.</span></span> 
  
<span data-ttu-id="b56f9-259">应使用**MSProviderInit**呼叫_lpfAllocateBuffer_中传递的缓冲区分配此**MAPIERROR**结构的内存。</span><span class="sxs-lookup"><span data-stu-id="b56f9-259">Memory for this **MAPIERROR** structure should be allocated by using the buffer passed in  _lpfAllocateBuffer_ on the **MSProviderInit** call.</span></span> <span data-ttu-id="b56f9-260">如果 MAPI_UNICODE 设置中**登录** _ulFlags;_ 否则，返回的结构中包含字符串应为 Unicode 格式任何错误，他们应的 ANSI 字符集字符中设置。</span><span class="sxs-lookup"><span data-stu-id="b56f9-260">Any error strings contained in the returned structure should be in Unicode format if MAPI_UNICODE is set in the **Logon** _ulFlags;_ otherwise, they should be in the ANSI character set.</span></span> 
  
<span data-ttu-id="b56f9-261">对于大多数**登录**从返回的错误值，MAPI 禁用的失败提供程序所属的消息服务。</span><span class="sxs-lookup"><span data-stu-id="b56f9-261">For most error values returned from **Logon**, MAPI disables the message services to which the failing provider belongs.</span></span> <span data-ttu-id="b56f9-262">MAPI 将不会调用属于生命周期的 MAPI 会话这些服务的任何提供程序。</span><span class="sxs-lookup"><span data-stu-id="b56f9-262">MAPI will not call any providers that belong to those services for the life of the MAPI session.</span></span> <span data-ttu-id="b56f9-263">相比之下时**登录**其登录过程中返回 MAPI_E_FAILONEPROVIDER 错误值，, MAPI 不禁用邮件服务提供程序所属。</span><span class="sxs-lookup"><span data-stu-id="b56f9-263">In contrast, when **Logon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="b56f9-264">如果遇到错误，不保证禁用整个会话的生命周期服务，则**登录**应返回 MAPI_E_FAILONEPROVIDER。</span><span class="sxs-lookup"><span data-stu-id="b56f9-264">**Logon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the entire service for the life of the session.</span></span> <span data-ttu-id="b56f9-265">例如，提供程序可能不允许的用户界面的显示和所需的密码将不可用时返回该错误。</span><span class="sxs-lookup"><span data-stu-id="b56f9-265">For example, a provider might return this error when it does not allow the display of a user interface and a required password is unavailable.</span></span> 
  
<span data-ttu-id="b56f9-266">如果提供程序返回 MAPI_E_UNCONFIGURED 从其登录，MAPI 将调用提供程序的消息服务条目函数，然后重试登录。</span><span class="sxs-lookup"><span data-stu-id="b56f9-266">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="b56f9-267">MAPI 将 MSG_SERVICE_CONFIGURE 以使配置本身有机会的服务上下文。</span><span class="sxs-lookup"><span data-stu-id="b56f9-267">MAPI passes MSG_SERVICE_CONFIGURE as the context to give the service a chance to configure itself.</span></span> <span data-ttu-id="b56f9-268">如果客户端已经选择允许在登录的用户界面，该服务可以将其配置属性表，以便用户可以输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="b56f9-268">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so the user can enter configuration information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b56f9-269">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b56f9-269">See also</span></span>



[<span data-ttu-id="b56f9-270">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="b56f9-270">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="b56f9-271">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="b56f9-271">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="b56f9-272">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="b56f9-272">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="b56f9-273">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="b56f9-273">IMAPISupport::ModifyProfile</span></span>](imapisupport-modifyprofile.md)
  
[<span data-ttu-id="b56f9-274">IMAPISupport::ModifyStatusRow</span><span class="sxs-lookup"><span data-stu-id="b56f9-274">IMAPISupport::ModifyStatusRow</span></span>](imapisupport-modifystatusrow.md)
  
[<span data-ttu-id="b56f9-275">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b56f9-275">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
  
[<span data-ttu-id="b56f9-276">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="b56f9-276">IMSProvider::SpoolerLogon</span></span>](imsprovider-spoolerlogon.md)
  
[<span data-ttu-id="b56f9-277">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b56f9-277">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="b56f9-278">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="b56f9-278">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="b56f9-279">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="b56f9-279">MSProviderInit</span></span>](msproviderinit.md)
  
[<span data-ttu-id="b56f9-280">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b56f9-280">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

