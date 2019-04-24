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
# <a name="imsproviderlogon"></a><span data-ttu-id="53f0d-103">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="53f0d-103">IMSProvider::Logon</span></span>

  
  
<span data-ttu-id="53f0d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53f0d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53f0d-105">将 MAPI 记录到邮件存储提供程序的一个实例上。</span><span class="sxs-lookup"><span data-stu-id="53f0d-105">Logs MAPI on to one instance of a message store provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="53f0d-106">参数</span><span class="sxs-lookup"><span data-stu-id="53f0d-106">Parameters</span></span>

 <span data-ttu-id="53f0d-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="53f0d-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="53f0d-108">实时指向邮件存储区的当前 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-108">[in] A pointer to the current MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="53f0d-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="53f0d-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="53f0d-110">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="53f0d-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="53f0d-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="53f0d-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="53f0d-112">实时指向包含要用于存储提供程序登录的配置文件的名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-112">[in] A pointer to a string that contains the name of the profile being used for store provider logon.</span></span> <span data-ttu-id="53f0d-113">此字符串可以显示在对话框中, 将其写出到日志文件中, 或简单地忽略。</span><span class="sxs-lookup"><span data-stu-id="53f0d-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="53f0d-114">如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则它必须采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="53f0d-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="53f0d-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="53f0d-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="53f0d-116">实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="53f0d-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="53f0d-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="53f0d-118">实时指向邮件存储区的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="53f0d-119">在_lpEntryID_中传递**null**指示尚未选择邮件存储, 并且可以显示使用户能够选择邮件存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-119">Passing **null** in  _lpEntryID_ indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="53f0d-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="53f0d-120">_ulFlags_</span></span>
  
> <span data-ttu-id="53f0d-121">实时用于控制登录执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="53f0d-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="53f0d-122">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="53f0d-122">The following flags can be set:</span></span>
    
<span data-ttu-id="53f0d-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="53f0d-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="53f0d-124">即使基础对象对调用实现不可用, 也允许该调用成功。</span><span class="sxs-lookup"><span data-stu-id="53f0d-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="53f0d-125">如果该对象不可用, 则对该对象的后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="53f0d-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="53f0d-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="53f0d-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="53f0d-127">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="53f0d-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="53f0d-128">如果未设置 MAPI_UNICODE, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="53f0d-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="53f0d-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="53f0d-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="53f0d-130">阻止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="53f0d-131">如果设置了此标志, 如果登录不成功, 则返回错误值 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="53f0d-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="53f0d-132">如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="53f0d-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions that are necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="53f0d-133">MDB_NO_MAIL</span><span class="sxs-lookup"><span data-stu-id="53f0d-133">MDB_NO_MAIL</span></span> 
  
> <span data-ttu-id="53f0d-134">邮件存储不应用于发送或接收邮件。</span><span class="sxs-lookup"><span data-stu-id="53f0d-134">The message store should not be used for sending or receiving mail.</span></span> <span data-ttu-id="53f0d-135">此标志通知 mapi 不通知 mapi 后台处理程序正在打开此邮件存储。</span><span class="sxs-lookup"><span data-stu-id="53f0d-135">The flag signals MAPI not to notify the MAPI spooler that this message store is being opened.</span></span> <span data-ttu-id="53f0d-136">如果设置了此标志, 且邮件存储与传输提供程序紧密结合, 则提供程序不需要调用[IMAPISupport:: SpoolerNotify](imapisupport-spoolernotify.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-136">If this flag is set and the message store is tightly coupled with a transport provider, the provider does not need to call the [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) method.</span></span> 
    
<span data-ttu-id="53f0d-137">MDB_TEMPORARY</span><span class="sxs-lookup"><span data-stu-id="53f0d-137">MDB_TEMPORARY</span></span> 
  
> <span data-ttu-id="53f0d-138">在存储区上记录, 以便可以从 "配置文件" 部分以编程方式检索信息, 而无需使用对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-138">Logs on the store so that information can be retrieved programmatically from the profile section, without use of dialog boxes.</span></span> <span data-ttu-id="53f0d-139">此标志指示 MAPI 存储不会添加到邮件存储库表中, 并且无法永久成为存储。</span><span class="sxs-lookup"><span data-stu-id="53f0d-139">This flag instructs MAPI that the store is not to be added to the message store table and that the store cannot be made permanent.</span></span> <span data-ttu-id="53f0d-140">如果设置了此标志, 则邮件存储提供程序无需调用[IMAPISupport:: ModifyProfile](imapisupport-modifyprofile.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-140">If this flag is set, message store providers do not need to call the [IMAPISupport::ModifyProfile](imapisupport-modifyprofile.md) method.</span></span> 
    
<span data-ttu-id="53f0d-141">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="53f0d-141">MDB_WRITE</span></span> 
  
> <span data-ttu-id="53f0d-142">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="53f0d-142">Requests read/write permission.</span></span>
    
 <span data-ttu-id="53f0d-143">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="53f0d-143">_lpInterface_</span></span>
  
> <span data-ttu-id="53f0d-144">实时指向要登录到的邮件存储区的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-144">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="53f0d-145">传递**null**表示将返回邮件存储 ( [IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="53f0d-145">Passing **null** indicates the MAPI interface for the message store ( [IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="53f0d-146">也可以将_lpInterface_参数设置为邮件存储区的相应接口的标识符 (例如, IID_IUnknown 或 IID_IMAPIProp)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-146">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example, IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="53f0d-147">_lpcbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="53f0d-147">_lpcbSpoolSecurity_</span></span>
  
> <span data-ttu-id="53f0d-148">排除指向存储提供程序在其中返回_lppbSpoolSecurity_参数中的验证数据的大小 (以字节为单位) 的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-148">[out] A pointer to the variable in which the store provider returns the size, in bytes, of the validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="53f0d-149">_lppbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="53f0d-149">_lppbSpoolSecurity_</span></span>
  
> <span data-ttu-id="53f0d-150">排除指向指向返回的验证数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-150">[out] A pointer to the pointer to the returned validation data.</span></span> <span data-ttu-id="53f0d-151">提供此验证数据是为了使[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)方法可以将 MAPI 后台处理程序记录到与邮件存储提供程序相同的存储中。</span><span class="sxs-lookup"><span data-stu-id="53f0d-151">This validation data is provided so the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method can log the MAPI spooler on to the same store as the message store provider.</span></span> 
    
 <span data-ttu-id="53f0d-152">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="53f0d-152">_lppMAPIError_</span></span>
  
> <span data-ttu-id="53f0d-153">排除指向包含错误的版本、组件和上下文信息的返回的[MAPIERROR](mapierror.md)结构的指针 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-153">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="53f0d-154">如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为**null** 。</span><span class="sxs-lookup"><span data-stu-id="53f0d-154">The  _lppMAPIError_ parameter can be set to **null** if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="53f0d-155">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="53f0d-155">_lppMSLogon_</span></span>
  
> <span data-ttu-id="53f0d-156">排除指向邮件存储区登录对象的指针, MAPI 将登录到该对象。</span><span class="sxs-lookup"><span data-stu-id="53f0d-156">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="53f0d-157">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="53f0d-157">_lppMDB_</span></span>
  
> <span data-ttu-id="53f0d-158">排除指向指向要登录到的 MAPI 后台处理程序和客户端应用程序的邮件存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-158">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="53f0d-159">返回值</span><span class="sxs-lookup"><span data-stu-id="53f0d-159">Return value</span></span>

<span data-ttu-id="53f0d-160">S_OK</span><span class="sxs-lookup"><span data-stu-id="53f0d-160">S_OK</span></span> 
  
> <span data-ttu-id="53f0d-161">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="53f0d-161">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="53f0d-162">MAPI_E_FAILONEPROVIDER</span><span class="sxs-lookup"><span data-stu-id="53f0d-162">MAPI_E_FAILONEPROVIDER</span></span> 
  
> <span data-ttu-id="53f0d-163">此提供程序无法登录, 但此错误不应禁用该服务。</span><span class="sxs-lookup"><span data-stu-id="53f0d-163">This provider cannot log on, but this error should not disable the service.</span></span> 
    
<span data-ttu-id="53f0d-164">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="53f0d-164">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="53f0d-165">无法建立登录会话。</span><span class="sxs-lookup"><span data-stu-id="53f0d-165">A logon session could not be established.</span></span>
    
<span data-ttu-id="53f0d-166">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="53f0d-166">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="53f0d-167">配置文件中包含的信息不足, 无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="53f0d-167">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="53f0d-168">返回此值时, MAPI 会调用邮件存储提供程序的消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="53f0d-168">When this value is returned, MAPI calls the message store provider's message-service entry point function.</span></span>
    
<span data-ttu-id="53f0d-169">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="53f0d-169">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="53f0d-170">用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="53f0d-170">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
<span data-ttu-id="53f0d-171">MAPI_E_UNKNOWN_CPID</span><span class="sxs-lookup"><span data-stu-id="53f0d-171">MAPI_E_UNKNOWN_CPID</span></span> 
  
> <span data-ttu-id="53f0d-172">未将服务器配置为支持客户端的代码页。</span><span class="sxs-lookup"><span data-stu-id="53f0d-172">The server is not configured to support the client's code page.</span></span>
    
<span data-ttu-id="53f0d-173">MAPI_E_UNKNOWN_LCID</span><span class="sxs-lookup"><span data-stu-id="53f0d-173">MAPI_E_UNKNOWN_LCID</span></span> 
  
> <span data-ttu-id="53f0d-174">未将服务器配置为支持客户端的区域设置信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-174">The server is not configured to support the client's locale information.</span></span>
    
<span data-ttu-id="53f0d-175">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="53f0d-175">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="53f0d-176">调用成功, 但邮件存储区提供程序有可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-176">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="53f0d-177">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="53f0d-177">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="53f0d-178">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="53f0d-178">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="53f0d-179">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-179">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="53f0d-180">若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-180">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="53f0d-181">注解</span><span class="sxs-lookup"><span data-stu-id="53f0d-181">Remarks</span></span>

<span data-ttu-id="53f0d-182">MAPI 调用**IMSProvider:: Logon**方法, 以执行获取对邮件存储区的访问所必需的大部分处理过程。</span><span class="sxs-lookup"><span data-stu-id="53f0d-182">MAPI calls the **IMSProvider::Logon** method to do the majority of processing necessary to obtain access to a message store.</span></span> <span data-ttu-id="53f0d-183">邮件存储提供程序验证访问特定存储区所需的任何用户凭据, 并返回 MAPI 后台处理程序和客户端应用程序可以登录到的_lppMDB_参数中的邮件存储对象。</span><span class="sxs-lookup"><span data-stu-id="53f0d-183">Message store providers validate any user credentials necessary to access a particular store and return a message store object in the  _lppMDB_ parameter that the MAPI spooler and client applications can log on to.</span></span> 
  
<span data-ttu-id="53f0d-184">除了返回的用于客户端和 MAPI 后台处理程序的邮件存储对象之外, 该提供程序还返回邮件存储登录对象, 以便 MAPI 在控制打开的存储区时使用。</span><span class="sxs-lookup"><span data-stu-id="53f0d-184">In addition to the returned message store object for client and MAPI spooler use, the provider also returns a message store logon object for MAPI to use in controlling the opened store.</span></span> <span data-ttu-id="53f0d-185">邮件存储登录对象和邮件存储对象应紧密链接到邮件存储提供程序中, 以便每个对象都能影响另一个对象。</span><span class="sxs-lookup"><span data-stu-id="53f0d-185">The message store logon object and the message store object should be tightly linked inside the message store provider so each can affect the other.</span></span> <span data-ttu-id="53f0d-186">store 对象和 logon 对象的使用应相同;登录对象和 store 对象之间应存在一对一的对应关系, 这样, 这些对象就像是一个公开两个接口的对象一样。</span><span class="sxs-lookup"><span data-stu-id="53f0d-186">The use of the store object and the logon object should be identical; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="53f0d-187">这两个对象也应一起创建并一起释放。</span><span class="sxs-lookup"><span data-stu-id="53f0d-187">The two objects should also be created together and freed together.</span></span> 
  
<span data-ttu-id="53f0d-188">mapi 支持对象 (由 mapi 创建并在_lpMAPISup_参数中传递给提供程序) 提供了对 MAPI 中提供程序所需的函数的访问。</span><span class="sxs-lookup"><span data-stu-id="53f0d-188">The MAPI support object, created by MAPI and passed to the provider in the  _lpMAPISup_ parameter, provides access to functions in MAPI that the provider requires.</span></span> <span data-ttu-id="53f0d-189">这些函数包括保存和检索配置文件信息、访问通讯簿等的函数。</span><span class="sxs-lookup"><span data-stu-id="53f0d-189">These include functions that save and retrieve profile information, access address books, and so on.</span></span> <span data-ttu-id="53f0d-190">对于打开的每个存储, _lpMAPISup_指针可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="53f0d-190">The  _lpMAPISup_ pointer can be different for each store that is opened.</span></span> <span data-ttu-id="53f0d-191">在登录后处理邮件存储区的呼叫时, 存储提供程序应使用特定于该存储的_lpMAPISup_变量。</span><span class="sxs-lookup"><span data-stu-id="53f0d-191">While processing calls for a message store after logon, the store provider should use the  _lpMAPISup_ variable that is specific to that store.</span></span> <span data-ttu-id="53f0d-192">对于打开邮件存储区并在创建邮件存储登录对象时成功的任何**登录**呼叫, 提供程序必须保存指向 store Logon 对象中的 MAPI 支持对象的指针, 并且必须调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)方法以添加对的引用支持对象。</span><span class="sxs-lookup"><span data-stu-id="53f0d-192">For any **Logon** call that opens a message store and succeeds in creating a message store logon object, the provider must save a pointer to the MAPI support object in the store logon object and must call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx) method to add a reference for the support object.</span></span> 
  
<span data-ttu-id="53f0d-193">如果提供程序在**登录**呼叫过程中显示对话框, 则应使用_ulUIParam_参数。</span><span class="sxs-lookup"><span data-stu-id="53f0d-193">The  _ulUIParam_ parameter should be used if the provider presents dialog boxes during the **Logon** call.</span></span> <span data-ttu-id="53f0d-194">但是, 如果_ulFlags_包含 MDB_NO_DIALOG 标志, 则不应显示对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-194">However, dialog boxes should not be presented if  _ulFlags_ contains the MDB_NO_DIALOG flag.</span></span> <span data-ttu-id="53f0d-195">如果需要调用用户界面, 但_ulFlags_不允许, 或者如果由于其他原因而无法显示用户界面, 则提供程序应返回 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="53f0d-195">If a user interface needs to be called but  _ulFlags_ does not allow it, or if for some other reason a user interface cannot be displayed, the provider should return MAPI_E_LOGON_FAILED.</span></span> <span data-ttu-id="53f0d-196">如果**登录**显示一个对话框, 并且用户取消了登录, 则通常通过单击对话框的 "**取消**" 按钮, 提供程序应返回 MAPI_E_USER_CANCEL。</span><span class="sxs-lookup"><span data-stu-id="53f0d-196">If **Logon** displays a dialog box and the user cancels the logon, typically by clicking the dialog box's **Cancel** button, the provider should return MAPI_E_USER_CANCEL.</span></span> 
  
<span data-ttu-id="53f0d-197">_lpEntryID_参数可以是**null** , 也可以指向此邮件存储之前创建的已解包的存储条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53f0d-197">The  _lpEntryID_ parameter can either be **null** or point to an unwrapped store entry identifier that this message store previously created.</span></span> <span data-ttu-id="53f0d-198">如果_lpEntryID_指向一个已断开的条目标识符, 则该条目标识符可以来自多个位置之一:</span><span class="sxs-lookup"><span data-stu-id="53f0d-198">If  _lpEntryID_ points to an unwrapped entry identifier, that entry identifier can come from one of several places:</span></span> 
  
- <span data-ttu-id="53f0d-199">它可以是存储提供程序之前作为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性打包并写入到配置文件节中的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53f0d-199">It can be an entry identifier that the store provider previously wrapped and wrote to the profile section as a **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="53f0d-200">它可以是提供程序之前作为**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性进行包装并返回给呼叫客户端的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53f0d-200">It can be an entry identifier that the provider previously wrapped and returned to a calling client as a **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property.</span></span> 
    
- <span data-ttu-id="53f0d-201">它可以是提供程序之前作为邮件存储对象的**PR_ENTRYID**属性进行包装并返回给呼叫客户端的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53f0d-201">It can be an entry identifier that the provider previously wrapped and returned to a calling client as the **PR_ENTRYID** property of a message store object.</span></span> 
    
<span data-ttu-id="53f0d-202">在上述任一情况下, 可能会在与当前使用的计算机不同的计算机上创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="53f0d-202">In any of these cases, it is possible that the entry identifier was created on a different computer than the one currently being used.</span></span>
  
<span data-ttu-id="53f0d-203">如果_lpEntryID_不**为 null**, 则它应包含标识和定位邮件存储区所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-203">When  _lpEntryID_ is not **null**, it should contain all of the information needed to identify and locate the message store.</span></span> <span data-ttu-id="53f0d-204">此信息可以包括网络卷名、电话号码、用户帐户名等等。</span><span class="sxs-lookup"><span data-stu-id="53f0d-204">This information can include network volume names, phone numbers, user account names, and so on.</span></span> <span data-ttu-id="53f0d-205">如果使用条目标识符中的数据无法建立与存储区的连接, 则存储提供程序应显示一个对话框, 使用户能够选择要打开的存储。</span><span class="sxs-lookup"><span data-stu-id="53f0d-205">If the connection to the store cannot be made by using the data in the entry identifier, the store provider should display a dialog box that enables the user to select the store to be opened.</span></span> <span data-ttu-id="53f0d-206">对话框可能是必需的, 例如, 如果服务器已重命名、帐户名称已更改或部分网络不可用。</span><span class="sxs-lookup"><span data-stu-id="53f0d-206">A dialog box might be required, for example, if a server has been renamed, an account name has changed, or portions of the network are not available.</span></span>
  
<span data-ttu-id="53f0d-207">如果_lpEntryID_为**null**, 则尚未选择要使用的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="53f0d-207">When  _lpEntryID_ is **null**, the message store to use has not yet been selected.</span></span> <span data-ttu-id="53f0d-208">如果提供程序支持用于指定存储的其他方法, 则该提供程序仍可以访问存储, 而不显示对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-208">The provider can still access a store without displaying a dialog box if it supports further methods to specify the store.</span></span> <span data-ttu-id="53f0d-209">例如, 提供程序可以检查其初始化文件, 也可以查找配置中放置在其或其消息服务的配置文件部分中的其他属性。</span><span class="sxs-lookup"><span data-stu-id="53f0d-209">For example, the provider can check its initialization file, or it can look for additional properties that were placed in its or its message service's profile section at configuration.</span></span>
  
<span data-ttu-id="53f0d-210">如果提供程序发现所有必需的信息都不在配置文件中, 则应返回 MAPI_E_UNCONFIGURED。</span><span class="sxs-lookup"><span data-stu-id="53f0d-210">If a provider finds that all the required information is not in the profile, it should return MAPI_E_UNCONFIGURED.</span></span> <span data-ttu-id="53f0d-211">然后, MAPI 将调用提供程序的邮件服务入口点函数, 以使用户能够选择存储, 甚至可以创建一个存储, 并根据需要输入帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="53f0d-211">MAPI will then call the provider's message service entry point function to enable the user to select a store, or even to create one, and to enter an account name and password, as needed.</span></span> <span data-ttu-id="53f0d-212">MAPI 为新存储自动创建一个新的配置文件部分;此新的配置文件节可以是临时的, 也可以是永久的, 具体取决于它的添加方式。</span><span class="sxs-lookup"><span data-stu-id="53f0d-212">MAPI automatically creates a new profile section for a new store; this new profile section can be temporary or permanent, depending on how it has been added.</span></span> <span data-ttu-id="53f0d-213">如果存储提供程序调用**IMAPISupport:: ModifyProfile**方法, 则新的配置文件节将成为永久的, 并将该存储区添加到[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)方法返回的邮件存储列表中。</span><span class="sxs-lookup"><span data-stu-id="53f0d-213">If the store provider calls the **IMAPISupport::ModifyProfile** method, the new profile section becomes permanent and the store is added to the list of message stores returned by the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method.</span></span> 
  
<span data-ttu-id="53f0d-214">_lpInterface_参数指定新打开的存储对象所需的接口的 IID。</span><span class="sxs-lookup"><span data-stu-id="53f0d-214">The  _lpInterface_ parameter specifies the IID of the interface required for the newly opened store object.</span></span> <span data-ttu-id="53f0d-215">在_lpInterface_中传递**null**指定 MAPI 邮件存储区接口 ( **IMsgStore**) 是必需的。</span><span class="sxs-lookup"><span data-stu-id="53f0d-215">Passing **null** in  _lpInterface_ specifies that the MAPI message store interface, **IMsgStore**, is required.</span></span> <span data-ttu-id="53f0d-216">传递邮件存储区对象 IID_IMsgStore 还指定**IMsgStore**是必需的。</span><span class="sxs-lookup"><span data-stu-id="53f0d-216">Passing the message store object, IID_IMsgStore, also specifies that **IMsgStore** is required.</span></span> <span data-ttu-id="53f0d-217">如果在_lpInterface_中传递 IID_IUnknown, 则提供程序应使用从[IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx)派生的任何接口打开存储, 以最适合提供程序的接口 (同样, 这通常是**IMsgStore**)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-217">If IID_IUnknown is passed in  _lpInterface_, the provider should open the store by using whatever interface derived from [IUnknown](https://msdn.microsoft.com/library/ms680509%28v=VS.85%29.aspx) is best for the provider (again, this is typically **IMsgStore**).</span></span> <span data-ttu-id="53f0d-218">当传递 IID_IUnknown 时, 调用实现使用[IUnknown:: QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法在存储打开操作成功后选择接口。</span><span class="sxs-lookup"><span data-stu-id="53f0d-218">When IID_IUnknown is passed, the calling implementation uses the [IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) method to select an interface after the store open operation succeeds.</span></span> 
  
<span data-ttu-id="53f0d-219">**IMSProvider:: Logon**调用应返回足够的信息, 如访问存储区的存储和凭据的路径, 以允许 MAPI 后台处理程序登录到存储提供程序的同一存储, 而不显示对话框。</span><span class="sxs-lookup"><span data-stu-id="53f0d-219">The **IMSProvider::Logon** call should return sufficient information, such as a path to the store and credentials for accessing the store, to allow the MAPI spooler to log on to the same store that the store provider does without presenting a dialog box.</span></span> <span data-ttu-id="53f0d-220">_lpcbSpoolSecurity_和_lppbSpoolSecurity_参数用于返回此信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-220">The  _lpcbSpoolSecurity_ and  _lppbSpoolSecurity_ parameters are used to return this information.</span></span> <span data-ttu-id="53f0d-221">提供程序通过在[MSProviderInit](msproviderinit.md)函数的_lpfAllocateBuffer_参数中传递指向缓冲区的指针来为此数据分配内存;提供程序在_lpcbSpoolSecurity_中放置此缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="53f0d-221">The provider allocates the memory for this data by passing a pointer to a buffer in the [MSProviderInit](msproviderinit.md) function's  _lpfAllocateBuffer_ parameter; the provider places the size of this buffer in  _lpcbSpoolSecurity_.</span></span> 
  
<span data-ttu-id="53f0d-222">MAPI 在适当的时候释放此缓冲区。</span><span class="sxs-lookup"><span data-stu-id="53f0d-222">MAPI frees this buffer when appropriate.</span></span> <span data-ttu-id="53f0d-223">如果 MAPI 后台处理程序登录到存储可以从 "配置文件" 部分的信息单独完成, 则提供程序可以在_lppbSpoolSecurity_中返回 null, 而在_lpcbSpoolSecurity_中返回的信息大小为0。</span><span class="sxs-lookup"><span data-stu-id="53f0d-223">If the MAPI spooler's logon to the store can be accomplished from the information in the profile section alone, the provider can return null in  _lppbSpoolSecurity_ and 0 for the information's size in  _lpcbSpoolSecurity_.</span></span> <span data-ttu-id="53f0d-224">MAPI 后台处理程序登录与存储登录过程中的过程不同, 它是由于包含传递的信息的缓冲区在进程之间进行复制, 因此与存储提供程序进程相比, MAPI 后台处理程序进程的内存可能不在同一位置。</span><span class="sxs-lookup"><span data-stu-id="53f0d-224">The MAPI spooler logon occurs as part of a different process than the store logon; because the buffer that contains the passed information gets copied between processes, it might not be in memory at the same location for the MAPI spooler process as for the store provider process.</span></span> <span data-ttu-id="53f0d-225">因此, 提供程序不应将地址放入此缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="53f0d-225">Therefore, a provider shouldn't put addresses into this buffer.</span></span> <span data-ttu-id="53f0d-226">有关 MAPI 后台处理程序登录的详细信息, 请参阅[IMSProvider:: SpoolerLogon](imsprovider-spoolerlogon.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-226">For more information about MAPI spooler logon, see the [IMSProvider::SpoolerLogon](imsprovider-spoolerlogon.md) method.</span></span> 
  
<span data-ttu-id="53f0d-227">大多数存储提供程序使用在_lpMAPISup_参数中传递的支持对象的[IMAPISession:: OpenProfileSection](imapisession-openprofilesection.md)方法来保存和检索用户凭据和选项。</span><span class="sxs-lookup"><span data-stu-id="53f0d-227">Most store providers use the [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md) method of the support object passed in the  _lpMAPISup_ parameter for saving and retrieving user credentials and options.</span></span> <span data-ttu-id="53f0d-228">**OpenProfileSection**使存储提供程序能够在 profile 节中保存其他任意信息, 并将其与特定资源相关联。</span><span class="sxs-lookup"><span data-stu-id="53f0d-228">**OpenProfileSection** enables a store provider to save additional arbitrary information in a profile section and associate it with a particular resource.</span></span> <span data-ttu-id="53f0d-229">例如, 存储提供程序可以保存与资源相关联的用户帐户名和密码, 以及访问该资源所需的任何路径或其他信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-229">For example, a store provider can save the user account name and password associated with a resource and any paths or other information needed to access that resource.</span></span> 
  
<span data-ttu-id="53f0d-230">属性标识符0x6600 到0x67FF 的属性是可供提供程序用来在 profile 节中存储私有数据的安全属性。</span><span class="sxs-lookup"><span data-stu-id="53f0d-230">Properties with property identifiers 0x6600 through 0x67FF are secure properties available to the provider for its own use to store private data in profile sections.</span></span> <span data-ttu-id="53f0d-231">有关 profile 部分对象中的属性使用的详细信息, 请参阅[IProfSect: IMAPIProp](iprofsectimapiprop.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-231">For more information about the uses of properties in profile section objects, see the [IProfSect : IMAPIProp](iprofsectimapiprop.md) method.</span></span> 
  
<span data-ttu-id="53f0d-232">除了标识符0x6600 到0x67FF 的属性中的任何专用数据之外, 存储提供程序还应在其 profile 节中提供**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-232">In addition to any private data in properties with identifiers 0x6600 through 0x67FF, the store provider should provide information for the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in its profile section.</span></span> <span data-ttu-id="53f0d-233">它应放在**PR_DISPLAY_NAME**中, 提供程序本身的显示名称 (一个标识字符串 (例如 "Microsoft 个人信息存储"), 以便用户可以将此邮件存储区与他们可能有权访问的其他人区分开来自。</span><span class="sxs-lookup"><span data-stu-id="53f0d-233">It should put in **PR_DISPLAY_NAME** the display name of the provider itself — an identifying string (for example, "Microsoft Personal Information Store") that is displayed to users so they can distinguish this message store from others they might have access to.</span></span> <span data-ttu-id="53f0d-234">**PR_DISPLAY_NAME**通常包含服务器名称、用户帐户名称或路径。</span><span class="sxs-lookup"><span data-stu-id="53f0d-234">**PR_DISPLAY_NAME** commonly contains a server name, user account name, or path.</span></span> 
  
<span data-ttu-id="53f0d-235">某些配置文件节属性在邮件存储表中可见;其他人在安装、安装和配置 MAPI 子系统期间可见。</span><span class="sxs-lookup"><span data-stu-id="53f0d-235">Some profile section properties are visible in the message store table; others are visible during setup, installation, and configuration of the MAPI subsystem.</span></span> <span data-ttu-id="53f0d-236">提供程序通常会为一个新的配置文件部分提供这些可见属性的信息, 该部分还不包括保存的凭据或私有信息, 并且在发现属性信息已更改时。</span><span class="sxs-lookup"><span data-stu-id="53f0d-236">The provider typically provides information for these visible properties both for a new profile section, which does not yet include saved credentials or private information, and when it finds that property information has changed.</span></span> <span data-ttu-id="53f0d-237">有关配置文件节的详细信息, 请参阅[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-237">For more information about profile sections, see [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md).</span></span>
  
<span data-ttu-id="53f0d-238">在用户成功登录并返回 MAPI 之前, 存储提供程序应为资源的状态行创建属性的数组并调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="53f0d-238">After successfully logging on a user, and before returning to MAPI, the store provider should create the array of properties for the status row for the resource and call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method.</span></span> 
  
 <span data-ttu-id="53f0d-239">打开已为当前 MAPI 会话打开的邮件存储的**登录**调用将跳过上述大部分处理过程。</span><span class="sxs-lookup"><span data-stu-id="53f0d-239">**Logon** calls that open message stores that are already open for the current MAPI session skip much of the processing previously described.</span></span> <span data-ttu-id="53f0d-240">这些呼叫不会创建状态行、返回邮件存储区登录对象、调用**AddRef**的 mapi 支持对象或返回 mapi 后台处理程序登录的数据。</span><span class="sxs-lookup"><span data-stu-id="53f0d-240">These calls do not create status rows, return message store logon objects, call **AddRef** for the MAPI support object, or return data for MAPI spooler logon.</span></span> <span data-ttu-id="53f0d-241">这些调用确实返回 S_OK, 并返回包含所请求的接口的邮件存储对象。</span><span class="sxs-lookup"><span data-stu-id="53f0d-241">These calls do return S_OK and return a message store object with the requested interface.</span></span> 
  
<span data-ttu-id="53f0d-242">若要检测此类调用, 提供程序应在已为此提供程序对象打开的存储的邮件存储区提供程序对象中维护一个列表。</span><span class="sxs-lookup"><span data-stu-id="53f0d-242">To detect such calls, the provider should maintain a list in the message store provider object of stores already open for this provider object.</span></span> <span data-ttu-id="53f0d-243">在处理**登录**呼叫时, 提供程序应扫描此打开存储的列表, 并确定要登录到的存储是否已打开。</span><span class="sxs-lookup"><span data-stu-id="53f0d-243">When processing a **Logon** call, the provider should scan this list of open stores and determine whether the store to be logged on to is already open.</span></span> <span data-ttu-id="53f0d-244">如果是这样, 则无需选中用户凭据, 并且应尽可能避免显示对话框 (如果可能)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-244">If it is, user credentials do not need to be checked and the display of a dialog box should be avoided, if possible.</span></span> <span data-ttu-id="53f0d-245">如果必须显示对话框, 则提供程序应检查返回的信息, 以查看是否已再次打开存储区。</span><span class="sxs-lookup"><span data-stu-id="53f0d-245">If dialog boxes must be displayed, the provider should check returned information to see whether a store has been opened a second time.</span></span> <span data-ttu-id="53f0d-246">此外, 提供程序应在**登录**呼叫处理开始时使用_lpEntryID_检查是否存在重复的空缺。</span><span class="sxs-lookup"><span data-stu-id="53f0d-246">In addition, the provider should check for duplicate openings by using  _lpEntryID_ at the beginning of **Logon** call processing.</span></span> 
  
<span data-ttu-id="53f0d-247">访问打开存储的**登录**呼叫的标准处理方式如下所示:</span><span class="sxs-lookup"><span data-stu-id="53f0d-247">Standard processing for a **Logon** call that accesses an open store is as follows:</span></span> 
  
1. <span data-ttu-id="53f0d-248">如果请求的新接口与现有存储区的接口相同, 则存储提供程序将对现有 store 对象调用**AddRef** 。</span><span class="sxs-lookup"><span data-stu-id="53f0d-248">The store provider calls **AddRef** for the existing store object if the new interface being requested is the same as the interface for the existing store.</span></span> <span data-ttu-id="53f0d-249">否则, 它调用**QueryInterface**以获取新接口。</span><span class="sxs-lookup"><span data-stu-id="53f0d-249">Otherwise, it calls **QueryInterface** to get the new interface.</span></span> <span data-ttu-id="53f0d-250">如果存储区不支持新接口, 则提供程序应返回错误值 MAPI_E_INTERFACE_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="53f0d-250">If the store does not support the new interface, the provider should return the error value MAPI_E_INTERFACE_NOT_SUPPORTED.</span></span> 
    
2. <span data-ttu-id="53f0d-251">提供程序返回指向_lppMDB_中现有 store 对象的所需接口的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-251">The provider returns a pointer to the required interface of the existing store object in  _lppMDB_.</span></span>
    
3. <span data-ttu-id="53f0d-252">提供程序在_lppMSLogon_中返回**null** 。</span><span class="sxs-lookup"><span data-stu-id="53f0d-252">The provider returns **null** in  _lppMSLogon_.</span></span>
    
4. <span data-ttu-id="53f0d-253">提供程序不应打开在呼叫中传递的支持对象的配置文件。</span><span class="sxs-lookup"><span data-stu-id="53f0d-253">The provider should not open the profile for the support object passed in the call.</span></span> <span data-ttu-id="53f0d-254">此外, 它不应注册提供程序的唯一标识符、注册状态行或返回 MAPI 后台处理程序登录数据。</span><span class="sxs-lookup"><span data-stu-id="53f0d-254">In addition, it should not register a provider unique identifier, register a status row, or return MAPI spooler logon data.</span></span>
    
5. <span data-ttu-id="53f0d-255">提供程序不应调用支持对象的**AddRef** , 因为它不需要指向对象的指针。</span><span class="sxs-lookup"><span data-stu-id="53f0d-255">The provider should not call **AddRef** for the support object, because it does not require a pointer to the object.</span></span> 
    
<span data-ttu-id="53f0d-256">只要有可能, 提供程序就会为**登录**调用返回适当的错误和警告字符串, 因为这样做可大大减轻用户在决定为什么不起作用的原因。</span><span class="sxs-lookup"><span data-stu-id="53f0d-256">Whenever possible, providers should return appropriate error and warning strings for **Logon** calls, because doing so greatly eases the burden of users in determining why something did not work.</span></span> <span data-ttu-id="53f0d-257">若要返回这些字符串, 提供程序将设置**MAPIERROR**结构中的成员。</span><span class="sxs-lookup"><span data-stu-id="53f0d-257">To return these strings, a provider sets the members in the **MAPIERROR** structure.</span></span> <span data-ttu-id="53f0d-258">MAPI 查找、使用和释放**MAPIERROR**结构 (如果提供程序返回)。</span><span class="sxs-lookup"><span data-stu-id="53f0d-258">MAPI looks for, uses, and releases the **MAPIERROR** structure if it is returned by a provider.</span></span> 
  
<span data-ttu-id="53f0d-259">应使用在**MSProviderInit**调用的_lpfAllocateBuffer_中传递的缓冲区分配此**MAPIERROR**结构的内存。</span><span class="sxs-lookup"><span data-stu-id="53f0d-259">Memory for this **MAPIERROR** structure should be allocated by using the buffer passed in  _lpfAllocateBuffer_ on the **MSProviderInit** call.</span></span> <span data-ttu-id="53f0d-260">如果在**登录** _ulFlags_中设置了 MAPI_UNICODE, 则返回的结构中包含的任何错误字符串都应采用 Unicode 格式; 否则, 它们应在 ANSI 字符集中。</span><span class="sxs-lookup"><span data-stu-id="53f0d-260">Any error strings contained in the returned structure should be in Unicode format if MAPI_UNICODE is set in the **Logon** _ulFlags;_ otherwise, they should be in the ANSI character set.</span></span> 
  
<span data-ttu-id="53f0d-261">对于从**登录**返回的大多数错误值, MAPI 都会禁用失败的提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="53f0d-261">For most error values returned from **Logon**, MAPI disables the message services to which the failing provider belongs.</span></span> <span data-ttu-id="53f0d-262">mapi 在 mapi 会话的有效期内不会调用任何属于这些服务的提供程序。</span><span class="sxs-lookup"><span data-stu-id="53f0d-262">MAPI will not call any providers that belong to those services for the life of the MAPI session.</span></span> <span data-ttu-id="53f0d-263">相比之下, 当**logon**从其登录中返回 MAPI_E_FAILONEPROVIDER 错误值时, MAPI 不会禁用该提供程序所属的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="53f0d-263">In contrast, when **Logon** returns the MAPI_E_FAILONEPROVIDER error value from its logon, MAPI does not disable the message service to which the provider belongs.</span></span> <span data-ttu-id="53f0d-264">如果遇到不保证在会话生命周期内禁用整个服务的错误, 则**登录**应返回 MAPI_E_FAILONEPROVIDER。</span><span class="sxs-lookup"><span data-stu-id="53f0d-264">**Logon** should return MAPI_E_FAILONEPROVIDER if it encounters an error that does not warrant disabling the entire service for the life of the session.</span></span> <span data-ttu-id="53f0d-265">例如, 当提供程序不允许显示用户界面且必需的密码不可用时, 该提供程序可能会返回此错误。</span><span class="sxs-lookup"><span data-stu-id="53f0d-265">For example, a provider might return this error when it does not allow the display of a user interface and a required password is unavailable.</span></span> 
  
<span data-ttu-id="53f0d-266">如果提供程序从其登录返回 MAPI_E_UNCONFIGURED, 则 MAPI 将调用提供程序的邮件服务条目功能, 然后重试该登录。</span><span class="sxs-lookup"><span data-stu-id="53f0d-266">If a provider returns MAPI_E_UNCONFIGURED from its logon, MAPI will call the provider's message service entry function and then retry the logon.</span></span> <span data-ttu-id="53f0d-267">MAPI 将 MSG_SERVICE_CONFIGURE 作为上下文, 使服务有机会对自身进行配置。</span><span class="sxs-lookup"><span data-stu-id="53f0d-267">MAPI passes MSG_SERVICE_CONFIGURE as the context to give the service a chance to configure itself.</span></span> <span data-ttu-id="53f0d-268">如果客户端已选择允许登录时使用用户界面, 则服务可以显示其配置属性表, 以便用户可以输入配置信息。</span><span class="sxs-lookup"><span data-stu-id="53f0d-268">If the client has chosen to allow a user interface on the logon, the service can present its configuration property sheet so the user can enter configuration information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53f0d-269">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53f0d-269">See also</span></span>



[<span data-ttu-id="53f0d-270">IMAPISession::GetMsgStoresTable</span><span class="sxs-lookup"><span data-stu-id="53f0d-270">IMAPISession::GetMsgStoresTable</span></span>](imapisession-getmsgstorestable.md)
  
[<span data-ttu-id="53f0d-271">IMAPISession::OpenMsgStore</span><span class="sxs-lookup"><span data-stu-id="53f0d-271">IMAPISession::OpenMsgStore</span></span>](imapisession-openmsgstore.md)
  
[<span data-ttu-id="53f0d-272">IMAPISession::OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="53f0d-272">IMAPISession::OpenProfileSection</span></span>](imapisession-openprofilesection.md)
  
[<span data-ttu-id="53f0d-273">IMAPISupport::ModifyProfile</span><span class="sxs-lookup"><span data-stu-id="53f0d-273">IMAPISupport::ModifyProfile</span></span>](imapisupport-modifyprofile.md)
  
[<span data-ttu-id="53f0d-274">IMAPISupport::ModifyStatusRow</span><span class="sxs-lookup"><span data-stu-id="53f0d-274">IMAPISupport::ModifyStatusRow</span></span>](imapisupport-modifystatusrow.md)
  
[<span data-ttu-id="53f0d-275">IMsgStore : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="53f0d-275">IMsgStore : IMAPIProp</span></span>](imsgstoreimapiprop.md)
  
[<span data-ttu-id="53f0d-276">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="53f0d-276">IMSProvider::SpoolerLogon</span></span>](imsprovider-spoolerlogon.md)
  
[<span data-ttu-id="53f0d-277">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="53f0d-277">IProfSect : IMAPIProp</span></span>](iprofsectimapiprop.md)
  
[<span data-ttu-id="53f0d-278">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="53f0d-278">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="53f0d-279">MSProviderInit</span><span class="sxs-lookup"><span data-stu-id="53f0d-279">MSProviderInit</span></span>](msproviderinit.md)
  
[<span data-ttu-id="53f0d-280">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="53f0d-280">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

