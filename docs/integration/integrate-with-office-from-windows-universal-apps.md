---
title: 从 Windows 通用应用程序与 Office 集成
manager: soliver
ms.date: 02/06/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 60b4fa23-0075-4f6a-8bd0-9e53e99432d5
description: 您可以将 Windows 通用应用程序平台第三方应用程序与 Excel Mobile、PowerPoint Mobile 和 Word Mobile 集成。通用应用程序将通过 Windows 文件选取器合约、expando 属性和缓存文件更新程序合约与 Office 应用程序集成在一起。
ms.openlocfilehash: 2c170fd55c9c6f10d348610ffbc75ffa86447529
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774098"
---
# <a name="integrate-with-office-from-windows-universal-apps"></a><span data-ttu-id="c129b-104">从 Windows 通用应用程序与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="c129b-104">Integrate with Office from Windows universal apps</span></span>

<span data-ttu-id="c129b-p102">您可以将 Windows 通用应用程序平台第三方应用程序与 Excel Mobile、PowerPoint Mobile 和 Word Mobile 集成。通用应用程序将通过 Windows [文件选取器合约](https://msdn.microsoft.com/zh-CN/library/windows/apps/hh465174.aspx)、[expando 属性](https://msdn.microsoft.com/zh-CN/library/windows/apps/xaml/hh770655.aspx)和[缓存文件更新程序合约](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx)与 Office 应用程序集成在一起。</span><span class="sxs-lookup"><span data-stu-id="c129b-p102">You can integrate your Windows universal app platform third-party apps with Excel Mobile, PowerPoint Mobile, and Word Mobile. Universal apps integrate with Office apps via Windows [file picker contracts](https://msdn.microsoft.com/zh-CN/library/windows/apps/hh465174.aspx), [expando properties](https://msdn.microsoft.com/zh-CN/library/windows/apps/xaml/hh770655.aspx), and [Cached File Updater contracts](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx).</span></span>
  
<span data-ttu-id="c129b-p103">当您将通用应用程序与 Excel、PowerPoint 或 Word Mobile 集成在一起时，您的用户在 Office 中浏览或在使用 Windows 打开您的应用程序中的文件时，他们可以打开您的应用程序提供的 Office 文档。用户还可以将文件保存回可将文件上载到您的服务的通用应用程序。</span><span class="sxs-lookup"><span data-stu-id="c129b-p103">When you integrate your universal app with Excel, PowerPoint, or Word Mobile, your users can open Office documents that your app provides, either when they browse from within Office or when they use Windows to open files from within your app. Users can also save the file back to your universal app, which uploads the file back to your service.</span></span>
  
<span data-ttu-id="c129b-109">这种方式打开的文件会显示在 Office 中的最近列表中，因此您的用户可以轻松地查找并重新打开这些文件。</span><span class="sxs-lookup"><span data-stu-id="c129b-109">Files opened this way appear in the Recent list in Office, so your users can easily find and reopen them.</span></span>
  
<span data-ttu-id="c129b-110">这种集成要求您的通用应用程序：</span><span class="sxs-lookup"><span data-stu-id="c129b-110">This integration requires that your universal app:</span></span>
    
- <span data-ttu-id="c129b-111">实施 Windows [文件选取器合同](https://msdn.microsoft.com/zh-CN/library/windows/apps/hh465174.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c129b-111">Implements the Windows [file picker contracts](https://msdn.microsoft.com/zh-CN/library/windows/apps/hh465174.aspx).</span></span>
    
- <span data-ttu-id="c129b-112">表示文件存储（例如，允许访问云存储的应用程序）。</span><span class="sxs-lookup"><span data-stu-id="c129b-112">Represents a file store (for example, an app that allows access to cloud storage).</span></span>
    
## <a name="expando-properties"></a><span data-ttu-id="c129b-113">Expando 属性</span><span class="sxs-lookup"><span data-stu-id="c129b-113">Expando properties</span></span>

<span data-ttu-id="c129b-p104">Windows 通用应用程序可以使用 Expando 属性沟通与文件相关联的其他信息。有关如何在 Windows 中工作的信息，请参阅 [StorageItemContentProperties.SavePropertiesAsync ](https://msdn.microsoft.com/zh-CN/library/windows/apps/xaml/hh770655.aspx) 中的"System.ExpandoProperties"。</span><span class="sxs-lookup"><span data-stu-id="c129b-p104">Windows universal apps can use Expando properties to communicate additional information that is associated with files. For information about how this works in Windows, see "System.ExpandoProperties" in [StorageItemContentProperties.SavePropertiesAsync](https://msdn.microsoft.com/zh-CN/library/windows/apps/xaml/hh770655.aspx).</span></span>
  
<span data-ttu-id="c129b-p105">下表介绍了您的应用程序需要向 Office 提供的属性，以支持文件打开方案。如果未提供此信息，您的应用程序中的所有文件将以只读模式打开。用户能否打开文件进行编辑取决于其拥有的 Office 许可证类型以及其尝试打开的文档类型。</span><span class="sxs-lookup"><span data-stu-id="c129b-p105">The following table describes the properties that your app has to provide to Office to enable file open scenarios. If this information is not provided, all files from your app are opened as read only. Whether users can open files for editing depends on the type of Office license they have and the type of document they're trying to open.</span></span>
  
<span data-ttu-id="c129b-119">在 **System.ExpandoProperties** 属性集中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="c129b-119">Set these properties in the **System.ExpandoProperties** property set.</span></span> 
  
|<span data-ttu-id="c129b-120">**属性**</span><span class="sxs-lookup"><span data-stu-id="c129b-120">**Property**</span></span>|<span data-ttu-id="c129b-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="c129b-121">**Description**</span></span>|<span data-ttu-id="c129b-122">**类型**</span><span class="sxs-lookup"><span data-stu-id="c129b-122">**Type**</span></span>|<span data-ttu-id="c129b-123">**示例**</span><span class="sxs-lookup"><span data-stu-id="c129b-123">**Example**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c129b-124">**AppDisplayName**</span><span class="sxs-lookup"><span data-stu-id="c129b-124">**AppDisplayName**</span></span> <br/> |<span data-ttu-id="c129b-p106">向用户显示的提供程序名称。将出现在 Office 中的多个位置，如最近的文档列表。</span><span class="sxs-lookup"><span data-stu-id="c129b-p106">Provider name to display to the user. Appears in multiple places in Office, such as the recent document list.</span></span>  <br/> |<span data-ttu-id="c129b-127">String</span><span class="sxs-lookup"><span data-stu-id="c129b-127">String</span></span>  <br/> |<span data-ttu-id="c129b-128">Contoso</span><span class="sxs-lookup"><span data-stu-id="c129b-128">Contoso</span></span>  <br/> |
|<span data-ttu-id="c129b-129">**MicrosoftOfficeOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="c129b-129">**MicrosoftOfficeOwnershipType**</span></span> <br/> |<span data-ttu-id="c129b-p107">对于许可，则表示文档/位置是个人/使用者还是工作/企业。允许值为 1（个人）和 2（企业）。例如，如果用户的文件存储在 Contoso Business 中，则可使用值"2"来表示企业。</span><span class="sxs-lookup"><span data-stu-id="c129b-p107">For licensing, indicate whether the document/location is Personal/Consumer or Work/Business. Allowed values are 1 (personal) and 2 (business). For example, if your user's file is stored in Contoso Business, use the value "2" for business.</span></span>  <br/> |<span data-ttu-id="c129b-133">Unit32</span><span class="sxs-lookup"><span data-stu-id="c129b-133">Unit32</span></span>  <br/> | <span data-ttu-id="c129b-134">1 或 2</span><span class="sxs-lookup"><span data-stu-id="c129b-134">1 or 2</span></span>  <br/> <span data-ttu-id="c129b-135">例如，如果用户的文件存储在 Contoso Business 中，则应将此文件标记为"2"来表示企业。</span><span class="sxs-lookup"><span data-stu-id="c129b-135">For example, if your user's file is stored in Contoso Business, this file should be marked 2 for business.</span></span>  <br/> |
|<span data-ttu-id="c129b-136">**MicrosoftOfficeTermsOfUse**</span><span class="sxs-lookup"><span data-stu-id="c129b-136">**MicrosoftOfficeTermsOfUse**</span></span> <br/> |<span data-ttu-id="c129b-p108">声明您提供的信息准确对应于每条使用条款的法律文本。此文本不向用户进行显示。它是在您、应用程序供应商和 Microsoft 之间拟定的协议。</span><span class="sxs-lookup"><span data-stu-id="c129b-p108">Legal text to declare that the information you provide is accurate per our terms of use. This text is not displayed to the user. It is an agreement between you, the application provider, and Microsoft.</span></span>  <br/> <span data-ttu-id="c129b-140">有关示例，请参阅以下内容。</span><span class="sxs-lookup"><span data-stu-id="c129b-140">See the following for an example.</span></span>  <br/> | <span data-ttu-id="c129b-141">String</span><span class="sxs-lookup"><span data-stu-id="c129b-141">String</span></span>  <br/> | <span data-ttu-id="c129b-142">我同意 [https://go.microsoft.com/fwlink/p/?LinkId=528381](third-party-applications-integrating-with-office-mobile-products.md) 中的条款</span><span class="sxs-lookup"><span data-stu-id="c129b-142">I agree to the terms located in [https://go.microsoft.com/fwlink/p/?LinkId=528381](third-party-applications-integrating-with-office-mobile-products.md)</span></span> <br/> |
   
<span data-ttu-id="c129b-143">以下代码示例演示如何设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="c129b-143">The following code example shows how to set these properties.</span></span>
  
```cs
public static async Task SetExpandoProperties(StorageFile file,... other params ...) 
  { 
     var expandoProperties = new PropertySet(); 
     expandoProperties.Add("AppDisplayName", "Contoso",);  
     // String value. 
     expandoProperties.Add("MicrosoftOfficeOwnershipType", 1);  
     // Unit32 value - 1 (for personal), 2 (for business).  
     expandoProperties.Add("MicrosoftOfficeTermsOfUse", "I agree to the terms located at https://go.microsoft.com/fwlink/p/?LinkId=528381");   
    // String value. 
          
       var fileProperties = new PropertySet(); 
       fileProperties.Add("System.ExpandoProperties", expandoProperties); 
       await file.Properties.SavePropertiesAsync(fileProperties); 
  } 

```

## <a name="cached-file-updater-contracts"></a><span data-ttu-id="c129b-144">缓存的文件更新程序合约</span><span class="sxs-lookup"><span data-stu-id="c129b-144">Cached File Updater contracts</span></span>

<span data-ttu-id="c129b-p109">如果在缓存文件更新程序合约中加入您的通用应用程序，则它将收到对文件更改了另一个通用应用程序（如 Office）的通知。有关如何在 Windows 中工作的信息，请参阅 [CachedFileUpdater 类](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c129b-p109">If your universal app participates in Cached File Updater contracts, it will be notified of changes another universal app (such as Office) makes to the file. For information about how this works in Windows, see [CachedFileUpdater class](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx).</span></span>
  
<span data-ttu-id="c129b-p110">Office 使用 **AllowOnlyReaders** 选项打开您的通用应用程序通过文件选取器合约提供的读写文件。这意味着，当文件在 Office 中打开时，该文件不能被移动、删除、重命名，或通过其他（包括您自己的）应用程序来写入。Office 将自动保存文件，但将 CachedFileManager.DeferUpdates 设置为在 Office 关闭文档之前阻止激活您的应用程序，否则（当用户切换到另一个应用程序时）Office 会被 Windows 挂起 。当 Office 关闭该文件时，您的应用程序可以对其进行写入。</span><span class="sxs-lookup"><span data-stu-id="c129b-p110">Office uses the **AllowOnlyReaders** option to open the read-write files your universal app provides via the file picker contracts. This means the file cannot be moved, deleted, renamed, or written to by another app, including your own, while it is open in Office. Office will autosave the file, but sets CachedFileManager.DeferUpdates to prevent activating your app until Office closes the document, or Office is suspended by Windows (when the user switches to another app). When Office closes the file, your app can write to it.</span></span> 
  
<span data-ttu-id="c129b-151">您的应用程序必须处理与您的服务进行的所有通信，包括下载、刷新和上载。</span><span class="sxs-lookup"><span data-stu-id="c129b-151">Your app must handle all communication with your service, including download, refresh, and upload.</span></span>
  
<span data-ttu-id="c129b-152">下表列出了设置用来在您的应用程序和 Office 之间处理交互的参数。</span><span class="sxs-lookup"><span data-stu-id="c129b-152">The following tables lists the parameters to set to handle interactions between your app and Office.</span></span>
  
|<span data-ttu-id="c129b-153">**参数**</span><span class="sxs-lookup"><span data-stu-id="c129b-153">**Parameter**</span></span>|<span data-ttu-id="c129b-154">**说明**</span><span class="sxs-lookup"><span data-stu-id="c129b-154">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c129b-155">ReadActivationMode</span><span class="sxs-lookup"><span data-stu-id="c129b-155">ReadActivationMode</span></span>](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.readactivationmode.aspx) <br/> |<span data-ttu-id="c129b-156">设置 **BeforeAccess** 以允许您的应用程序更新该文件，然后再将它发送到 Office。</span><span class="sxs-lookup"><span data-stu-id="c129b-156">Set **BeforeAccess** to allow your app to update the file before it sends it to Office.</span></span>  <br/> |
|[<span data-ttu-id="c129b-157">WriteActivationMode</span><span class="sxs-lookup"><span data-stu-id="c129b-157">WriteActivationMode</span></span>](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.writeactivationmode.aspx) <br/> |<span data-ttu-id="c129b-p111">设置 **ReadOnly** 使文件处于只读状态。 设置 **AfterWrite** 以确保使用该文件完成 Office 操作时，CacheFileUpdater 将触发您的应用程序。  </span><span class="sxs-lookup"><span data-stu-id="c129b-p111">Set **ReadOnly** to make the file read only. Set **AfterWrite** to ensure that your app will be triggered by the CacheFileUpdater when Office is finished with the file.</span></span><br/><br/><span data-ttu-id="c129b-160">**注意**：如果不设置 **AfterWrite**，你的应用就不会收到上载更改的通知，这意味着用户的更改将只是一些本地更改。</span><span class="sxs-lookup"><span data-stu-id="c129b-160">If you do not set **AfterWrite**, your app will not be notified to upload the changes, which means that the user’s changes will only be local. 
</span></span>           |
|[<span data-ttu-id="c129b-161">CachedFileOptions.RequireUpdateOnAccess</span><span class="sxs-lookup"><span data-stu-id="c129b-161">CachedFileOptions.RequireUpdateOnAccess</span></span>](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.storage.provider.cachedfileoptions.aspx) <br/> |<span data-ttu-id="c129b-162">设置此属性以确保当用户从最近列表中访问文件时，您的应用程序可以更新该文件。</span><span class="sxs-lookup"><span data-stu-id="c129b-162">Set this property to ensure that your app can update the file when a user accesses it from the Recent list.</span></span>  <br/> |
   
## <a name="invoking-office-from-your-app"></a><span data-ttu-id="c129b-163">从您的应用程序调用 Office</span><span class="sxs-lookup"><span data-stu-id="c129b-163">Invoking Office from your app</span></span>

<span data-ttu-id="c129b-p112">当用户从您的应用程序打开 Office 文档时，该文档可以在 Excel Mobile、PowerPoint Mobile 和 Word Mobile 中打开。例如，当用户在您的应用程序中选择 \*.docx 文件时，Word Mobile 启动的同时将打开 \*.docx 文件。打开哪个 Office 应用程序依据的是用户将文件类型与哪个应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="c129b-p112">When a user opens an Office document from your app, the document can open in Excel Mobile, PowerPoint Mobile, and Word Mobile. For example, when a user selects a \*.docx file in your app, Word Mobile launches with the \*.docx file opened. The Office app that opens is based on which app the user associated with the file type.</span></span>
  
<span data-ttu-id="c129b-p113">若要在 Office 中打开您的应用程序中的文件，建议您使用 **LaunchFileAsync()** 启动该文件。不建议您使用 **LaunchUriAsync()** 启动该文件，因为这将导致为 URI 方案注册的应用程序会启动（浏览器） 而不是 Office。尽管 **LaunchUriAsync()** 带有 **LauncherOptions.ContentType()** 选项，可以调用 Office，但在这种情况下，打开的文件被标记为临时，并且在 Office 中是只读状态。</span><span class="sxs-lookup"><span data-stu-id="c129b-p113">To open a file from your app in Office, we recommend that you use **LaunchFileAsync()** to launch the file. We don't recommend that you use **LaunchUriAsync()** to launch the file because that will cause the application registered for the URI scheme to launch (the browser) instead of Office. Although **LaunchUriAsync()** with the **LauncherOptions.ContentType()** option can invoke Office, in this case the file opened is marked as temporary and is read-only in Office.</span></span> 
  
<span data-ttu-id="c129b-170">有关详细信息，请参阅[启动器类](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.system.launcher.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c129b-170">For more information, see [Launcher class](https://msdn.microsoft.com/zh-CN/library/windows/apps/windows.system.launcher.aspx).</span></span>
  
## <a name="temporary-and-read-only-files"></a><span data-ttu-id="c129b-171">临时和只读文件</span><span class="sxs-lookup"><span data-stu-id="c129b-171">Temporary and read-only files</span></span>

<span data-ttu-id="c129b-172">在您的应用程序中，对临时文件设置 **FILE_ATTRIBUTE_TEMPORARY** 属性，对只读文件设置 **FILE_ATTRIBUTE_READONLY** 属性。</span><span class="sxs-lookup"><span data-stu-id="c129b-172">Set the **FILE_ATTRIBUTE_TEMPORARY** attribute on temporary files and the **FILE_ATTRIBUTE_READONLY** attribute on read-only files in your app.</span></span> 
  
<span data-ttu-id="c129b-p114">具有 **FILE_ATTRIBUTE_TEMPORARY** 或 **FILE_ATTRIBUTE_READONLY** 属性的文件设置为，在 Office 中以只读方式打开。 **FILE_ATTRIBUTE_TEMPORARY** 还会阻止该文件显示在最近列表中。</span><span class="sxs-lookup"><span data-stu-id="c129b-p114">Files that have the **FILE_ATTRIBUTE_TEMPORARY** or **FILE_ATTRIBUTE_READONLY** attributes set open as read-only in Office. The **FILE_ATTRIBUTE_TEMPORARY** also prevents the file from appearing in the Recent list.</span></span> 
  
<span data-ttu-id="c129b-175">有关文件属性的详细信息，请参阅 [SetFileAttributes 函数](https://msdn.microsoft.com/zh-CN/library/windows/desktop/aa365535%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c129b-175">For more information about file attributes, see [SetFileAttributes function](https://msdn.microsoft.com/zh-CN/library/windows/desktop/aa365535%28v=vs.85%29.aspx).</span></span>
  
## <a name="other-best-practices"></a><span data-ttu-id="c129b-176">其他最佳做法</span><span class="sxs-lookup"><span data-stu-id="c129b-176">Other best practices</span></span>

<span data-ttu-id="c129b-177">为了优化文件的一致性，例如，冲突编辑或错误发生时，应用以下最佳实践：</span><span class="sxs-lookup"><span data-stu-id="c129b-177">To optimize for file consistency, for example when conflicting edits or errors occur, apply the following best practices:</span></span>
  
- <span data-ttu-id="c129b-178">阻止保存冲突。</span><span class="sxs-lookup"><span data-stu-id="c129b-178">Prevent save conflicts.</span></span>
    
  - <span data-ttu-id="c129b-p115">发生服务器冲突时，暂停上载以避免分叉（分叉仅出现在 Office 不再打开写入文件时）。通常情况下，如果您的应用程序中的文件在 Office 中打开，则仅在 Office 关闭或被 Windows 挂起时，才会激活您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c129b-p115">Pause uploads when server conflicts occur to avoid forking (only fork when Office no longer has a write file open). Typically, if a file from your app is open in Office, your app is activated only when Office closes or is suspended by Windows.</span></span>
    
  - <span data-ttu-id="c129b-181">如果你需要 UI 来处理冲突，请使用 toast 通知。</span><span class="sxs-lookup"><span data-stu-id="c129b-181">◦If you need UI to handle conflicts, implement toast notifications.</span></span> <span data-ttu-id="c129b-182">挂起 Office 时，完整 UI 不可用。</span><span class="sxs-lookup"><span data-stu-id="c129b-182">Full UI is not available when Office is suspended.</span></span>
    
- <span data-ttu-id="c129b-183">处理错误。</span><span class="sxs-lookup"><span data-stu-id="c129b-183">Handle errors.</span></span>
    
  - <span data-ttu-id="c129b-184">当锁定解除时，会通知用户发生冲突，并提供在您的应用程序中解决此问题的路径。</span><span class="sxs-lookup"><span data-stu-id="c129b-184">When a lock is released, notify users of the conflict and provide a path to resolve it within your app.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c129b-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c129b-185">See also</span></span>

- [<span data-ttu-id="c129b-186">与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="c129b-186">Integrate with Office</span></span>](integrate-with-office.md)   
- [<span data-ttu-id="c129b-187">从 Win32 同步客户端与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="c129b-187">Integrate with Office from Win32 sync clients</span></span>](integrate-with-office-from-win32-sync-clients.md)
    

