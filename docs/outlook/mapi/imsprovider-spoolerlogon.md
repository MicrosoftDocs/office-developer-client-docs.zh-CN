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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 794674df38266743cac8c947ec93dc1fcfff438b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430572"
---
# <a name="imsproviderspoolerlogon"></a><span data-ttu-id="a5796-103">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="a5796-103">IMSProvider::SpoolerLogon</span></span>

  
  
<span data-ttu-id="a5796-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a5796-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a5796-105">将 MAPI 后台处理程序记录到邮件存储。</span><span class="sxs-lookup"><span data-stu-id="a5796-105">Logs the MAPI spooler on to a message store.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="a5796-106">参数</span><span class="sxs-lookup"><span data-stu-id="a5796-106">Parameters</span></span>

 <span data-ttu-id="a5796-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="a5796-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="a5796-108">[in]指向邮件存储的 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-108">[in] A pointer to the MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="a5796-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="a5796-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="a5796-110">[in]该方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="a5796-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="a5796-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="a5796-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="a5796-112">[in]指向包含用于 MAPI 后台处理程序登录的配置文件名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-112">[in] A pointer to a string that contains the name of the profile being used for the MAPI spooler logon.</span></span> <span data-ttu-id="a5796-113">此字符串可以在对话框中显示、写入或日志文件或忽略。</span><span class="sxs-lookup"><span data-stu-id="a5796-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="a5796-114">如果在  _ulFlags_ 参数中设置了 MAPI_UNICODE 标志，则它必须采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a5796-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="a5796-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="a5796-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="a5796-116">[in]  _lpEntryID_ 参数指向的条目标识符的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a5796-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="a5796-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="a5796-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="a5796-118">[in]指向邮件存储的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="a5796-119">在  _lpEntryID_ 参数中传递 NULL 表示尚未选择邮件存储，并且会显示允许用户选择邮件存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="a5796-119">Passing NULL in the  _lpEntryID_ parameter indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="a5796-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="a5796-120">_ulFlags_</span></span>
  
> <span data-ttu-id="a5796-121">[in]控制如何执行登录的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a5796-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="a5796-122">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="a5796-122">The following flags can be set:</span></span>
    
<span data-ttu-id="a5796-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="a5796-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="a5796-124">即使基础对象对调用实现不可用，也允许调用成功。</span><span class="sxs-lookup"><span data-stu-id="a5796-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="a5796-125">如果该对象不可用，则对该对象的后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="a5796-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="a5796-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="a5796-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="a5796-127">传入字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="a5796-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="a5796-128">如果未MAPI_UNICODE，则字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="a5796-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="a5796-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="a5796-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="a5796-130">禁止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="a5796-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="a5796-131">如果设置此标志，则返回错误MAPI_E_LOGON_FAILED登录不成功时返回。</span><span class="sxs-lookup"><span data-stu-id="a5796-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="a5796-132">如果未设置此标志，则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="a5796-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="a5796-133">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="a5796-133">MDB_WRITE</span></span> 
  
> <span data-ttu-id="a5796-134">请求读/写权限。</span><span class="sxs-lookup"><span data-stu-id="a5796-134">Requests read/write permission.</span></span>
    
 <span data-ttu-id="a5796-135">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="a5796-135">_lpInterface_</span></span>
  
> <span data-ttu-id="a5796-136">[in]指向接口标识符的 (IID) 供邮件存储登录。</span><span class="sxs-lookup"><span data-stu-id="a5796-136">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="a5796-137">传递 NULL 指示返回 [IMsgStore](imsgstoreimapiprop.md) (邮件存储) MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="a5796-137">Passing NULL indicates the MAPI interface for the message store ([IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="a5796-138">_还可以将 lpInterface_ 参数设置为邮件存储应用程序的适当接口的标识符 (例如 IID_IUnknown 或 IID_IMAPIProp) 。</span><span class="sxs-lookup"><span data-stu-id="a5796-138">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="a5796-139">_cbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="a5796-139">_cbSpoolSecurity_</span></span>
  
> <span data-ttu-id="a5796-140">[in]指向  _lppbSpoolSecurity_ 参数中验证数据的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-140">[in] A pointer to the size, in bytes, of validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="a5796-141">_lpbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="a5796-141">_lpbSpoolSecurity_</span></span>
  
> <span data-ttu-id="a5796-142">[in]指向验证数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-142">[in] A pointer to a pointer to validation data.</span></span> <span data-ttu-id="a5796-143">**SpoolerLogon** 方法使用此数据通过 [IMSProvider：：Logon](imsprovider-logon.md)方法将 MAPI 后台处理程序记录到之前登录的消息存储提供程序所登录到的同一存储。</span><span class="sxs-lookup"><span data-stu-id="a5796-143">The **SpoolerLogon** method uses this data to log the MAPI spooler on to the same store as the message store provider previously logged on to by using the [IMSProvider::Logon](imsprovider-logon.md) method.</span></span> 
    
 <span data-ttu-id="a5796-144">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="a5796-144">_lppMAPIError_</span></span>
  
> <span data-ttu-id="a5796-145">[out]指向返回的 [MAPIERROR](mapierror.md) 结构的指针（如果有）的指针，其中包含错误的版本、组件和上下文信息。</span><span class="sxs-lookup"><span data-stu-id="a5796-145">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="a5796-146">如果没有要返回的 **MAPIERROR** 结构，可以将 _lppMAPIError_ 参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="a5796-146">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="a5796-147">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="a5796-147">_lppMSLogon_</span></span>
  
> <span data-ttu-id="a5796-148">[out]指向指向 MAPI 要登录的消息存储登录对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-148">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="a5796-149">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="a5796-149">_lppMDB_</span></span>
  
> <span data-ttu-id="a5796-150">[out]指向 MAPI 后台处理程序和客户端应用程序要登录的消息存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a5796-150">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a5796-151">返回值</span><span class="sxs-lookup"><span data-stu-id="a5796-151">Return value</span></span>

<span data-ttu-id="a5796-152">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5796-152">S_OK</span></span> 
  
> <span data-ttu-id="a5796-153">调用成功并返回了预期值。</span><span class="sxs-lookup"><span data-stu-id="a5796-153">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="a5796-154">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="a5796-154">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="a5796-155">配置文件包含的信息不足，无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="a5796-155">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="a5796-156">返回此值时，MAPI 将调用邮件存储提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="a5796-156">When this value is returned, MAPI calls the message store provider's message service entry point function.</span></span>
    
<span data-ttu-id="a5796-157">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="a5796-157">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="a5796-158">调用成功，但邮件存储提供程序提供错误信息。</span><span class="sxs-lookup"><span data-stu-id="a5796-158">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="a5796-159">返回此警告时，应成功处理呼叫。</span><span class="sxs-lookup"><span data-stu-id="a5796-159">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="a5796-160">若要测试此警告，请使用 **HR_FAILED** 宏。</span><span class="sxs-lookup"><span data-stu-id="a5796-160">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="a5796-161">有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="a5796-161">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="a5796-162">若要从提供程序获取错误信息，请调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="a5796-162">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="a5796-163">备注</span><span class="sxs-lookup"><span data-stu-id="a5796-163">Remarks</span></span>

<span data-ttu-id="a5796-164">MAPI 后台处理程序调用 **IMSProvider：：SpoolerLogon** 方法以登录到消息存储。</span><span class="sxs-lookup"><span data-stu-id="a5796-164">The MAPI spooler calls the **IMSProvider::SpoolerLogon** method to log on to a message store.</span></span> <span data-ttu-id="a5796-165">MAPI 后台处理程序应在登录期间和登录后使用邮件存储提供程序在  _lppMDB_ 参数中返回的邮件存储对象。</span><span class="sxs-lookup"><span data-stu-id="a5796-165">The MAPI spooler should use the message store object returned by the message store provider in the  _lppMDB_ parameter during and after logon.</span></span> 
  
<span data-ttu-id="a5796-166">为了与 [IMSProvider：：Logon](imsprovider-logon.md) 方法保持一致，提供程序还会在  _lppMSLogon_ 参数中返回消息存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="a5796-166">For consistency with the [IMSProvider::Logon](imsprovider-logon.md) method, the provider also returns a message store logon object in the  _lppMSLogon_ parameter.</span></span> <span data-ttu-id="a5796-167">存储对象的使用与通常存储登录的登录对象相同;登录对象和存储对象之间应该存在一对一的对应关系，这样对象的行为就就像它们是一个公开两个接口的对象一样。</span><span class="sxs-lookup"><span data-stu-id="a5796-167">The use of the store object and the logon object are identical for usual store logon; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="a5796-168">这两个对象一起创建并释放在一起。</span><span class="sxs-lookup"><span data-stu-id="a5796-168">The two objects are created together and freed together.</span></span> 
  
<span data-ttu-id="a5796-169">存储提供程序应在内部标记返回的邮件存储对象，以指示 MAPI 后台处理程序正在使用存储。</span><span class="sxs-lookup"><span data-stu-id="a5796-169">The store provider should internally mark the returned message store object to indicate that the store is being used by the MAPI spooler.</span></span> <span data-ttu-id="a5796-170">此存储对象的一些方法的行为不同于提供给客户端应用程序的邮件存储对象的行为。</span><span class="sxs-lookup"><span data-stu-id="a5796-170">Some of the methods for this store object behave differently than for the message store object provided to client applications.</span></span> <span data-ttu-id="a5796-171">保留此内部标记是触发特定于 MAPI 后台处理程序的行为的最常见方法。</span><span class="sxs-lookup"><span data-stu-id="a5796-171">Keeping this internal mark is the most common way of triggering the behavior specific to the MAPI spooler.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5796-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5796-172">See also</span></span>



[<span data-ttu-id="a5796-173">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="a5796-173">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="a5796-174">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="a5796-174">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="a5796-175">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a5796-175">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

