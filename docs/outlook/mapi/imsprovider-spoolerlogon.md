---
title: IMSProviderSpoolerLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider.SpoolerLogon
api_type:
- COM
ms.assetid: 79d5af23-efad-4013-a330-56babfb2bb0f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 56c025713b0cc2b41a4bf4463f48f8d7c3d2124b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586415"
---
# <a name="imsproviderspoolerlogon"></a><span data-ttu-id="35910-103">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="35910-103">IMSProvider::SpoolerLogon</span></span>

  
  
<span data-ttu-id="35910-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="35910-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="35910-105">记录到的消息存储 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="35910-105">Logs the MAPI spooler on to a message store.</span></span>
  
```cpp
HRESULT SpoolerLogon(
  LPMAPISUP lpMAPISup,
  ULONG_PTR ulUIParam,
  LPSTR lpszProfileName,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  ULONG ulFlags,
  LPCIID lpInterface,
  ULONG cbSpoolSecurity,
  LPBYTE lpbSpoolSecurity,
  LPMAPIERROR FAR * lppMAPIError,
  LPMSLOGON FAR * lppMSLogon,
  LPMDB FAR * lppMDB     
);
```

## <a name="parameters"></a><span data-ttu-id="35910-106">参数</span><span class="sxs-lookup"><span data-stu-id="35910-106">Parameters</span></span>

 <span data-ttu-id="35910-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="35910-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="35910-108">[in]一个指向 MAPI 支持的消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="35910-108">[in] A pointer to the MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="35910-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="35910-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="35910-110">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="35910-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="35910-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="35910-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="35910-112">[in]一个指向一个字符串，包含要用于 MAPI 后台处理程序登录的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="35910-112">[in] A pointer to a string that contains the name of the profile being used for the MAPI spooler logon.</span></span> <span data-ttu-id="35910-113">可以显示在对话框中，写入日志文件，或只忽略此字符串。</span><span class="sxs-lookup"><span data-stu-id="35910-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="35910-114">如果_ulFlags_参数中设置 MAPI_UNICODE 标志，它必须是以 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="35910-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="35910-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="35910-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="35910-116">[in]以字节为单位_lpEntryID_参数指向的项标识符的大小。</span><span class="sxs-lookup"><span data-stu-id="35910-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="35910-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="35910-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="35910-118">[in]指向消息存储库的项标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="35910-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="35910-119">_LpEntryID_参数中传递 NULL 指示尚未选择的消息存储，并且可以提供让用户能够选择的消息存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="35910-119">Passing NULL in the  _lpEntryID_ parameter indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="35910-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="35910-120">_ulFlags_</span></span>
  
> <span data-ttu-id="35910-121">[in]位掩码的标志，控制如何执行登录。</span><span class="sxs-lookup"><span data-stu-id="35910-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="35910-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="35910-122">The following flags can be set:</span></span>
    
<span data-ttu-id="35910-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="35910-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="35910-124">若要成功执行，即使基础对象不可用的呼叫的实现，即允许该呼叫。</span><span class="sxs-lookup"><span data-stu-id="35910-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="35910-125">如果对象不可用，对对象的后续调用可能会引发一个错误。</span><span class="sxs-lookup"><span data-stu-id="35910-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="35910-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="35910-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="35910-127">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="35910-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="35910-128">如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="35910-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="35910-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="35910-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="35910-130">阻止登录对话框的显示。</span><span class="sxs-lookup"><span data-stu-id="35910-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="35910-131">如果设置此标志，如果登录失败，则返回错误值 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="35910-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="35910-132">如果未设置此标志，消息存储提供程序可以提示用户正确的名称或密码，插入磁盘，或执行其他操作所需建立连接到存储区。</span><span class="sxs-lookup"><span data-stu-id="35910-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="35910-133">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="35910-133">MDB_WRITE</span></span> 
  
> <span data-ttu-id="35910-134">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="35910-134">Requests read/write permission.</span></span>
    
 <span data-ttu-id="35910-135">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="35910-135">_lpInterface_</span></span>
  
> <span data-ttu-id="35910-136">[in]指向要登录到的邮件存储区的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="35910-136">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="35910-137">传递 NULL 指示返回的消息存储 ([IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 界面。</span><span class="sxs-lookup"><span data-stu-id="35910-137">Passing NULL indicates the MAPI interface for the message store ([IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="35910-138">_LpInterface_参数还可以设置为消息存储 （例如 IID_IUnknown 或 IID_IMAPIProp） 的适当的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="35910-138">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="35910-139">_cbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="35910-139">_cbSpoolSecurity_</span></span>
  
> <span data-ttu-id="35910-140">[in]指向的大小，以字节为单位_lppbSpoolSecurity_参数中的验证数据的指针。</span><span class="sxs-lookup"><span data-stu-id="35910-140">[in] A pointer to the size, in bytes, of validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="35910-141">_lpbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="35910-141">_lpbSpoolSecurity_</span></span>
  
> <span data-ttu-id="35910-142">[in]指向验证数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="35910-142">[in] A pointer to a pointer to validation data.</span></span> <span data-ttu-id="35910-143">**SpoolerLogon**方法使用此数据之前使用[IMSProvider::Logon](imsprovider-logon.md)方法登录到的消息存储提供程序以登录到同一个存储 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="35910-143">The **SpoolerLogon** method uses this data to log the MAPI spooler on to the same store as the message store provider previously logged on to by using the [IMSProvider::Logon](imsprovider-logon.md) method.</span></span> 
    
 <span data-ttu-id="35910-144">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="35910-144">_lppMAPIError_</span></span>
  
> <span data-ttu-id="35910-145">[输出]指向返回[MAPIERROR](mapierror.md)结构，如果有，其中包含的错误的版本、 组件及上下文信息的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="35910-145">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="35910-146">如果不没有返回任何**MAPIERROR**结构， _lppMAPIError_参数可以设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="35910-146">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="35910-147">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="35910-147">_lppMSLogon_</span></span>
  
> <span data-ttu-id="35910-148">[输出]指向该指针指向邮件存储 MAPI 登录到的登录对象。</span><span class="sxs-lookup"><span data-stu-id="35910-148">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="35910-149">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="35910-149">_lppMDB_</span></span>
  
> <span data-ttu-id="35910-150">[输出]指向该指针指向邮件存储 MAPI 后台处理程序和客户端应用程序登录到的对象。</span><span class="sxs-lookup"><span data-stu-id="35910-150">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="35910-151">返回值</span><span class="sxs-lookup"><span data-stu-id="35910-151">Return value</span></span>

<span data-ttu-id="35910-152">S_OK</span><span class="sxs-lookup"><span data-stu-id="35910-152">S_OK</span></span> 
  
> <span data-ttu-id="35910-153">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="35910-153">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="35910-154">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="35910-154">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="35910-155">配置文件不包含登录后，若要完成的足够信息。</span><span class="sxs-lookup"><span data-stu-id="35910-155">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="35910-156">返回此值时，MAPI 调用的消息存储提供程序的消息服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="35910-156">When this value is returned, MAPI calls the message store provider's message service entry point function.</span></span>
    
<span data-ttu-id="35910-157">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="35910-157">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="35910-158">调用成功，但消息存储提供程序已经可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="35910-158">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="35910-159">返回此警告时，应处理呼叫为成功。</span><span class="sxs-lookup"><span data-stu-id="35910-159">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="35910-160">若要测试此警告，请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="35910-160">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="35910-161">有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="35910-161">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="35910-162">要从提供程序获取错误的信息，请调用[IMAPISession::GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="35910-162">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="35910-163">注解</span><span class="sxs-lookup"><span data-stu-id="35910-163">Remarks</span></span>

<span data-ttu-id="35910-164">MAPI 后台处理程序调用**IMSProvider::SpoolerLogon**方法来登录到的消息存储。</span><span class="sxs-lookup"><span data-stu-id="35910-164">The MAPI spooler calls the **IMSProvider::SpoolerLogon** method to log on to a message store.</span></span> <span data-ttu-id="35910-165">MAPI 后台处理程序应使用期间和之后登录_lppMDB_参数中的消息存储提供程序返回的消息存储对象。</span><span class="sxs-lookup"><span data-stu-id="35910-165">The MAPI spooler should use the message store object returned by the message store provider in the  _lppMDB_ parameter during and after logon.</span></span> 
  
<span data-ttu-id="35910-166">对于与[IMSProvider::Logon](imsprovider-logon.md)方法保持一致，提供程序还_lppMSLogon_参数中返回的消息存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="35910-166">For consistency with the [IMSProvider::Logon](imsprovider-logon.md) method, the provider also returns a message store logon object in the  _lppMSLogon_ parameter.</span></span> <span data-ttu-id="35910-167">使用的存储对象和登录对象是相同的常用存储登录;应一一对应登录对象之间的存储对象，以便对象就像它们是公开两个接口的一个对象。</span><span class="sxs-lookup"><span data-stu-id="35910-167">The use of the store object and the logon object are identical for usual store logon; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="35910-168">两个对象一起创建组合在一起和释放。</span><span class="sxs-lookup"><span data-stu-id="35910-168">The two objects are created together and freed together.</span></span> 
  
<span data-ttu-id="35910-169">存储提供程序应将返回的消息存储对象，以指示存储正在使用 MAPI 后台处理程序内部标记。</span><span class="sxs-lookup"><span data-stu-id="35910-169">The store provider should internally mark the returned message store object to indicate that the store is being used by the MAPI spooler.</span></span> <span data-ttu-id="35910-170">一些用于此存储对象的方法的行为不同比消息存储提供给客户端应用程序的对象。</span><span class="sxs-lookup"><span data-stu-id="35910-170">Some of the methods for this store object behave differently than for the message store object provided to client applications.</span></span> <span data-ttu-id="35910-171">保留此内部标志是最常见的触发特定于 MAPI 后台处理程序的行为方式。</span><span class="sxs-lookup"><span data-stu-id="35910-171">Keeping this internal mark is the most common way of triggering the behavior specific to the MAPI spooler.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="35910-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35910-172">See also</span></span>



[<span data-ttu-id="35910-173">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="35910-173">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="35910-174">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="35910-174">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="35910-175">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="35910-175">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

