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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309735"
---
# <a name="imsproviderspoolerlogon"></a><span data-ttu-id="34dd5-103">IMSProvider::SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="34dd5-103">IMSProvider::SpoolerLogon</span></span>

  
  
<span data-ttu-id="34dd5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34dd5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34dd5-105">将 MAPI 后台处理程序记录到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="34dd5-105">Logs the MAPI spooler on to a message store.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="34dd5-106">参数</span><span class="sxs-lookup"><span data-stu-id="34dd5-106">Parameters</span></span>

 <span data-ttu-id="34dd5-107">_lpMAPISup_</span><span class="sxs-lookup"><span data-stu-id="34dd5-107">_lpMAPISup_</span></span>
  
> <span data-ttu-id="34dd5-108">实时指向邮件存储区的 MAPI 支持对象的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-108">[in] A pointer to the MAPI support object for the message store.</span></span>
    
 <span data-ttu-id="34dd5-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="34dd5-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="34dd5-110">实时此方法显示的任何对话框或窗口的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="34dd5-110">[in] A handle to the parent window of any dialog boxes or windows this method displays.</span></span> 
    
 <span data-ttu-id="34dd5-111">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="34dd5-111">_lpszProfileName_</span></span>
  
> <span data-ttu-id="34dd5-112">实时指向包含要用于 MAPI 后台处理程序登录的配置文件的名称的字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-112">[in] A pointer to a string that contains the name of the profile being used for the MAPI spooler logon.</span></span> <span data-ttu-id="34dd5-113">此字符串可以显示在对话框中, 将其写出到日志文件中, 或简单地忽略。</span><span class="sxs-lookup"><span data-stu-id="34dd5-113">This string can be displayed in dialog boxes, written out to a log file, or simply ignored.</span></span> <span data-ttu-id="34dd5-114">如果在_ulFlags_参数中设置了 MAPI_UNICODE 标志, 则它必须采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="34dd5-114">It must be in Unicode format if the MAPI_UNICODE flag is set in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="34dd5-115">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="34dd5-115">_cbEntryID_</span></span>
  
> <span data-ttu-id="34dd5-116">实时由_lpEntryID_参数指向的条目标识符的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="34dd5-116">[in] The size, in bytes, of the entry identifier pointed to by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="34dd5-117">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="34dd5-117">_lpEntryID_</span></span>
  
> <span data-ttu-id="34dd5-118">实时指向邮件存储区的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-118">[in] A pointer to the entry identifier for the message store.</span></span> <span data-ttu-id="34dd5-119">在_lpEntryID_参数中传递 NULL 表示尚未选择邮件存储, 并且可以显示允许用户选择邮件存储的对话框。</span><span class="sxs-lookup"><span data-stu-id="34dd5-119">Passing NULL in the  _lpEntryID_ parameter indicates that a message store has not yet been selected and that dialog boxes that enable the user to select a message store can be presented.</span></span> 
    
 <span data-ttu-id="34dd5-120">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="34dd5-120">_ulFlags_</span></span>
  
> <span data-ttu-id="34dd5-121">实时用于控制登录执行方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="34dd5-121">[in] A bitmask of flags that controls how the logon is performed.</span></span> <span data-ttu-id="34dd5-122">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="34dd5-122">The following flags can be set:</span></span>
    
<span data-ttu-id="34dd5-123">MAPI_DEFERRED_ERRORS</span><span class="sxs-lookup"><span data-stu-id="34dd5-123">MAPI_DEFERRED_ERRORS</span></span> 
  
> <span data-ttu-id="34dd5-124">即使基础对象对调用实现不可用, 也允许该调用成功。</span><span class="sxs-lookup"><span data-stu-id="34dd5-124">The call is allowed to succeed even if the underlying object is not available to the calling implementation.</span></span> <span data-ttu-id="34dd5-125">如果该对象不可用, 则对该对象的后续调用可能会引发错误。</span><span class="sxs-lookup"><span data-stu-id="34dd5-125">If the object is not available, a subsequent call to the object might raise an error.</span></span>
    
<span data-ttu-id="34dd5-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="34dd5-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="34dd5-127">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="34dd5-127">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="34dd5-128">如果未设置 MAPI_UNICODE, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="34dd5-128">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
<span data-ttu-id="34dd5-129">MDB_NO_DIALOG</span><span class="sxs-lookup"><span data-stu-id="34dd5-129">MDB_NO_DIALOG</span></span> 
  
> <span data-ttu-id="34dd5-130">阻止显示登录对话框。</span><span class="sxs-lookup"><span data-stu-id="34dd5-130">Prevents the display of logon dialog boxes.</span></span> <span data-ttu-id="34dd5-131">如果设置了此标志, 如果登录不成功, 则返回错误值 MAPI_E_LOGON_FAILED。</span><span class="sxs-lookup"><span data-stu-id="34dd5-131">If this flag is set, the error value MAPI_E_LOGON_FAILED is returned if the logon is unsuccessful.</span></span> <span data-ttu-id="34dd5-132">如果未设置此标志, 则邮件存储提供程序可以提示用户更正名称或密码、插入磁盘或执行与存储建立连接所需的其他操作。</span><span class="sxs-lookup"><span data-stu-id="34dd5-132">If this flag is not set, the message store provider can prompt the user to correct a name or password, to insert a disk, or to perform other actions necessary to establish connection to the store.</span></span>
    
<span data-ttu-id="34dd5-133">MDB_WRITE</span><span class="sxs-lookup"><span data-stu-id="34dd5-133">MDB_WRITE</span></span> 
  
> <span data-ttu-id="34dd5-134">请求读取/写入权限。</span><span class="sxs-lookup"><span data-stu-id="34dd5-134">Requests read/write permission.</span></span>
    
 <span data-ttu-id="34dd5-135">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="34dd5-135">_lpInterface_</span></span>
  
> <span data-ttu-id="34dd5-136">实时指向要登录到的邮件存储区的接口标识符 (IID) 的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-136">[in] A pointer to the interface identifier (IID) for the message store to log on to.</span></span> <span data-ttu-id="34dd5-137">传递 NULL 表示将返回邮件存储 ([IMsgStore](imsgstoreimapiprop.md)) 的 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="34dd5-137">Passing NULL indicates the MAPI interface for the message store ([IMsgStore](imsgstoreimapiprop.md)) is returned.</span></span> <span data-ttu-id="34dd5-138">也可以将_lpInterface_参数设置为邮件存储区的相应接口的标识符 (例如 IID_IUnknown 或 IID_IMAPIProp)。</span><span class="sxs-lookup"><span data-stu-id="34dd5-138">The  _lpInterface_ parameter can also be set to an identifier for an appropriate interface for the message store (for example IID_IUnknown or IID_IMAPIProp).</span></span> 
    
 <span data-ttu-id="34dd5-139">_cbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="34dd5-139">_cbSpoolSecurity_</span></span>
  
> <span data-ttu-id="34dd5-140">实时一个指针, 指向_lppbSpoolSecurity_参数中的验证数据的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="34dd5-140">[in] A pointer to the size, in bytes, of validation data in the  _lppbSpoolSecurity_ parameter.</span></span> 
    
 <span data-ttu-id="34dd5-141">_lpbSpoolSecurity_</span><span class="sxs-lookup"><span data-stu-id="34dd5-141">_lpbSpoolSecurity_</span></span>
  
> <span data-ttu-id="34dd5-142">实时指向指向验证数据的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-142">[in] A pointer to a pointer to validation data.</span></span> <span data-ttu-id="34dd5-143">**SpoolerLogon**方法使用此数据, 通过使用[IMSProvider:: Logon](imsprovider-logon.md)方法将 MAPI 后台处理程序记录在与之前登录的邮件存储提供程序相同的存储中。</span><span class="sxs-lookup"><span data-stu-id="34dd5-143">The **SpoolerLogon** method uses this data to log the MAPI spooler on to the same store as the message store provider previously logged on to by using the [IMSProvider::Logon](imsprovider-logon.md) method.</span></span> 
    
 <span data-ttu-id="34dd5-144">_lppMAPIError_</span><span class="sxs-lookup"><span data-stu-id="34dd5-144">_lppMAPIError_</span></span>
  
> <span data-ttu-id="34dd5-145">排除指向包含错误的版本、组件和上下文信息的返回的[MAPIERROR](mapierror.md)结构的指针 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="34dd5-145">[out] A pointer to a pointer to the returned [MAPIERROR](mapierror.md) structure, if any, that contains version, component, and context information for an error.</span></span> <span data-ttu-id="34dd5-146">如果没有要返回的**MAPIERROR**结构, 则可以将_lppMAPIError_参数设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="34dd5-146">The  _lppMAPIError_ parameter can be set to NULL if there is no **MAPIERROR** structure to return.</span></span> 
    
 <span data-ttu-id="34dd5-147">_lppMSLogon_</span><span class="sxs-lookup"><span data-stu-id="34dd5-147">_lppMSLogon_</span></span>
  
> <span data-ttu-id="34dd5-148">排除指向邮件存储区登录对象的指针, MAPI 将登录到该对象。</span><span class="sxs-lookup"><span data-stu-id="34dd5-148">[out] A pointer to the pointer to the message store logon object for MAPI to log on to.</span></span>
    
 <span data-ttu-id="34dd5-149">_lppMDB_</span><span class="sxs-lookup"><span data-stu-id="34dd5-149">_lppMDB_</span></span>
  
> <span data-ttu-id="34dd5-150">排除指向指向要登录到的 MAPI 后台处理程序和客户端应用程序的邮件存储对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="34dd5-150">[out] A pointer to the pointer to the message store object for the MAPI spooler and client applications to log on to.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="34dd5-151">返回值</span><span class="sxs-lookup"><span data-stu-id="34dd5-151">Return value</span></span>

<span data-ttu-id="34dd5-152">S_OK</span><span class="sxs-lookup"><span data-stu-id="34dd5-152">S_OK</span></span> 
  
> <span data-ttu-id="34dd5-153">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="34dd5-153">The call succeeded and has returned the expected value or values.</span></span>
    
<span data-ttu-id="34dd5-154">MAPI_E_UNCONFIGURED</span><span class="sxs-lookup"><span data-stu-id="34dd5-154">MAPI_E_UNCONFIGURED</span></span> 
  
> <span data-ttu-id="34dd5-155">配置文件中包含的信息不足, 无法完成登录。</span><span class="sxs-lookup"><span data-stu-id="34dd5-155">The profile does not contain enough information for the logon to complete.</span></span> <span data-ttu-id="34dd5-156">返回此值时, MAPI 会调用邮件存储提供程序的邮件服务入口点函数。</span><span class="sxs-lookup"><span data-stu-id="34dd5-156">When this value is returned, MAPI calls the message store provider's message service entry point function.</span></span>
    
<span data-ttu-id="34dd5-157">MAPI_W_ERRORS_RETURNED</span><span class="sxs-lookup"><span data-stu-id="34dd5-157">MAPI_W_ERRORS_RETURNED</span></span> 
  
> <span data-ttu-id="34dd5-158">调用成功, 但邮件存储区提供程序有可用的错误信息。</span><span class="sxs-lookup"><span data-stu-id="34dd5-158">The call succeeded, but the message store provider has error information available.</span></span> <span data-ttu-id="34dd5-159">返回此警告时, 应以成功的方式处理该调用。</span><span class="sxs-lookup"><span data-stu-id="34dd5-159">When this warning is returned, the call should be handled as successful.</span></span> <span data-ttu-id="34dd5-160">若要测试此警告, 请使用**HR_FAILED**宏。</span><span class="sxs-lookup"><span data-stu-id="34dd5-160">To test for this warning, use the **HR_FAILED** macro.</span></span> <span data-ttu-id="34dd5-161">有关详细信息, 请参阅[使用宏进行错误处理](using-macros-for-error-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="34dd5-161">For more information, see [Using Macros for Error Handling](using-macros-for-error-handling.md).</span></span> <span data-ttu-id="34dd5-162">若要从提供程序获取错误消息, 请调用[IMAPISession:: GetLastError](imapisession-getlasterror.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34dd5-162">To get the error information from the provider, call the [IMAPISession::GetLastError](imapisession-getlasterror.md) method.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="34dd5-163">注解</span><span class="sxs-lookup"><span data-stu-id="34dd5-163">Remarks</span></span>

<span data-ttu-id="34dd5-164">MAPI 后台处理程序调用**IMSProvider:: SpoolerLogon**方法以登录到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="34dd5-164">The MAPI spooler calls the **IMSProvider::SpoolerLogon** method to log on to a message store.</span></span> <span data-ttu-id="34dd5-165">在登录期间和之后, MAPI 后台处理程序应使用_lppMDB_参数中的邮件存储提供程序返回的邮件存储对象对象。</span><span class="sxs-lookup"><span data-stu-id="34dd5-165">The MAPI spooler should use the message store object returned by the message store provider in the  _lppMDB_ parameter during and after logon.</span></span> 
  
<span data-ttu-id="34dd5-166">为了与[IMSProvider:: Logon](imsprovider-logon.md)方法保持一致, 提供程序还会在_lppMSLogon_参数中返回邮件存储登录对象。</span><span class="sxs-lookup"><span data-stu-id="34dd5-166">For consistency with the [IMSProvider::Logon](imsprovider-logon.md) method, the provider also returns a message store logon object in the  _lppMSLogon_ parameter.</span></span> <span data-ttu-id="34dd5-167">store 对象和 logon 对象的使用与通常的存储登录相同;登录对象和 store 对象之间应存在一对一的对应关系, 这样, 这些对象就像是一个公开两个接口的对象一样。</span><span class="sxs-lookup"><span data-stu-id="34dd5-167">The use of the store object and the logon object are identical for usual store logon; there should be a one-to-one correspondence between the logon object and the store object such that the objects act as if they are one object that exposes two interfaces.</span></span> <span data-ttu-id="34dd5-168">这两个对象一起创建并一起释放。</span><span class="sxs-lookup"><span data-stu-id="34dd5-168">The two objects are created together and freed together.</span></span> 
  
<span data-ttu-id="34dd5-169">存储提供程序应在内部标记返回的邮件存储对象, 以指示 MAPI 后台处理程序正在使用该存储区。</span><span class="sxs-lookup"><span data-stu-id="34dd5-169">The store provider should internally mark the returned message store object to indicate that the store is being used by the MAPI spooler.</span></span> <span data-ttu-id="34dd5-170">此 store 对象的某些方法的行为与向客户端应用程序提供的邮件存储对象的行为不同。</span><span class="sxs-lookup"><span data-stu-id="34dd5-170">Some of the methods for this store object behave differently than for the message store object provided to client applications.</span></span> <span data-ttu-id="34dd5-171">保持此内部标记是触发特定于 MAPI 后台处理程序的行为的最常见方法。</span><span class="sxs-lookup"><span data-stu-id="34dd5-171">Keeping this internal mark is the most common way of triggering the behavior specific to the MAPI spooler.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="34dd5-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34dd5-172">See also</span></span>



[<span data-ttu-id="34dd5-173">IMSProvider::Logon</span><span class="sxs-lookup"><span data-stu-id="34dd5-173">IMSProvider::Logon</span></span>](imsprovider-logon.md)
  
[<span data-ttu-id="34dd5-174">MAPIERROR</span><span class="sxs-lookup"><span data-stu-id="34dd5-174">MAPIERROR</span></span>](mapierror.md)
  
[<span data-ttu-id="34dd5-175">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34dd5-175">IMSProvider : IUnknown</span></span>](imsprovideriunknown.md)

