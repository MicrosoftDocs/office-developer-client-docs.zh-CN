---
title: 从 Windows 通用应用程序与 Office 集成
manager: soliver
ms.date: 02/06/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 60b4fa23-0075-4f6a-8bd0-9e53e99432d5
description: 您可以将 Windows 通用应用程序平台第三方应用程序与 Excel Mobile、PowerPoint Mobile 和 Word Mobile 集成。通用应用程序将通过 Windows 文件选取器合约、expando 属性和缓存文件更新程序合约与 Office 应用程序集成在一起。
ms.openlocfilehash: ad04ccc3ceb6e0f1d53e4aebc12cf9724ab8ab66
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388222"
---
# <a name="integrate-with-office-from-windows-universal-apps"></a>从 Windows 通用应用程序与 Office 集成

您可以将 Windows 通用应用程序平台第三方应用程序与 Excel Mobile、PowerPoint Mobile 和 Word Mobile 集成。通用应用程序将通过 Windows [文件选取器合约](https://msdn.microsoft.com/library/windows/apps/hh465174.aspx)、[expando 属性](https://msdn.microsoft.com/library/windows/apps/xaml/hh770655.aspx)和[缓存文件更新程序合约](https://msdn.microsoft.com/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx)与 Office 应用程序集成在一起。
  
当您将通用应用程序与 Excel、PowerPoint 或 Word Mobile 集成在一起时，您的用户在 Office 中浏览或在使用 Windows 打开您的应用程序中的文件时，他们可以打开您的应用程序提供的 Office 文档。用户还可以将文件保存回可将文件上载到您的服务的通用应用程序。
  
这种方式打开的文件会显示在 Office 中的最近列表中，因此您的用户可以轻松地查找并重新打开这些文件。
  
这种集成要求您的通用应用程序：
    
- 实施 Windows [文件选取器合同](https://msdn.microsoft.com/library/windows/apps/hh465174.aspx)。
    
- 表示文件存储（例如，允许访问云存储的应用程序）。
    
## <a name="expando-properties"></a>Expando 属性

Windows 通用应用程序可以使用 Expando 属性沟通与文件相关联的其他信息。有关如何在 Windows 中工作的信息，请参阅 [StorageItemContentProperties.SavePropertiesAsync ](https://msdn.microsoft.com/library/windows/apps/xaml/hh770655.aspx) 中的"System.ExpandoProperties"。
  
下表介绍了您的应用程序需要向 Office 提供的属性，以支持文件打开方案。如果未提供此信息，您的应用程序中的所有文件将以只读模式打开。用户能否打开文件进行编辑取决于其拥有的 Office 许可证类型以及其尝试打开的文档类型。
  
在 **System.ExpandoProperties** 属性集中设置这些属性。 
  
|**属性**|**说明**|**类型**|**示例**|
|:-----|:-----|:-----|:-----|
|**AppDisplayName** <br/> |向用户显示的提供程序名称。将出现在 Office 中的多个位置，如最近的文档列表。  <br/> |String  <br/> |Contoso  <br/> |
|**MicrosoftOfficeOwnershipType** <br/> |对于许可，则表示文档/位置是个人/使用者还是工作/企业。允许值为 1（个人）和 2（企业）。例如，如果用户的文件存储在 Contoso Business 中，则可使用值"2"来表示企业。  <br/> |Unit32  <br/> | 1 或 2  <br/> 例如，如果用户的文件存储在 Contoso Business 中，则应将此文件标记为"2"来表示企业。  <br/> |
|**MicrosoftOfficeTermsOfUse** <br/> |声明您提供的信息准确对应于每条使用条款的法律文本。此文本不向用户进行显示。它是在您、应用程序供应商和 Microsoft 之间拟定的协议。  <br/> 有关示例，请参阅以下内容。  <br/> | String  <br/> | 我同意 [https://go.microsoft.com/fwlink/p/?LinkId=528381](third-party-applications-integrating-with-office-mobile-products.md) 中的条款 <br/> |
   
以下代码示例演示如何设置这些属性。
  
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

## <a name="cached-file-updater-contracts"></a>缓存的文件更新程序合约

如果在缓存文件更新程序合约中加入您的通用应用程序，则它将收到对文件更改了另一个通用应用程序（如 Office）的通知。有关如何在 Windows 中工作的信息，请参阅 [CachedFileUpdater 类](https://msdn.microsoft.com/library/windows/apps/windows.storage.provider.cachedfileupdater.aspx)。
  
Office 使用 **AllowOnlyReaders** 选项打开您的通用应用程序通过文件选取器合约提供的读写文件。这意味着，当文件在 Office 中打开时，该文件不能被移动、删除、重命名，或通过其他（包括您自己的）应用程序来写入。Office 将自动保存文件，但将 CachedFileManager.DeferUpdates 设置为在 Office 关闭文档之前阻止激活您的应用程序，否则（当用户切换到另一个应用程序时）Office 会被 Windows 挂起 。当 Office 关闭该文件时，您的应用程序可以对其进行写入。 
  
您的应用程序必须处理与您的服务进行的所有通信，包括下载、刷新和上载。
  
下表列出了设置用来在您的应用程序和 Office 之间处理交互的参数。
  
|**参数**|**说明**|
|:-----|:-----|
|[ReadActivationMode](https://msdn.microsoft.com/library/windows/apps/windows.storage.provider.readactivationmode.aspx) <br/> |设置 **BeforeAccess** 以允许您的应用程序更新该文件，然后再将它发送到 Office。  <br/> |
|[WriteActivationMode](https://msdn.microsoft.com/library/windows/apps/windows.storage.provider.writeactivationmode.aspx) <br/> |设置 **ReadOnly** 使文件处于只读状态。 设置 **AfterWrite** 以确保使用该文件完成 Office 操作时，CacheFileUpdater 将触发您的应用程序。  <br/><br/>**注意**：如果不设置 **AfterWrite**，你的应用就不会收到上载更改的通知，这意味着用户的更改将只是一些本地更改。           |
|[CachedFileOptions.RequireUpdateOnAccess](https://msdn.microsoft.com/library/windows/apps/windows.storage.provider.cachedfileoptions.aspx) <br/> |设置此属性以确保当用户从最近列表中访问文件时，您的应用程序可以更新该文件。  <br/> |
   
## <a name="invoking-office-from-your-app"></a>从您的应用程序调用 Office

当用户从您的应用程序打开 Office 文档时，该文档可以在 Excel Mobile、PowerPoint Mobile 和 Word Mobile 中打开。例如，当用户在您的应用程序中选择 \*.docx 文件时，Word Mobile 启动的同时将打开 \*.docx 文件。打开哪个 Office 应用程序依据的是用户将文件类型与哪个应用程序相关联。
  
若要在 Office 中打开您的应用程序中的文件，建议您使用 **LaunchFileAsync()** 启动该文件。不建议您使用 **LaunchUriAsync()** 启动该文件，因为这将导致为 URI 方案注册的应用程序会启动（浏览器） 而不是 Office。尽管 **LaunchUriAsync()** 带有 **LauncherOptions.ContentType()** 选项，可以调用 Office，但在这种情况下，打开的文件被标记为临时，并且在 Office 中是只读状态。 
  
有关详细信息，请参阅[启动器类](https://msdn.microsoft.com/library/windows/apps/windows.system.launcher.aspx)。
  
## <a name="temporary-and-read-only-files"></a>临时和只读文件

在您的应用程序中，对临时文件设置 **FILE_ATTRIBUTE_TEMPORARY** 属性，对只读文件设置 **FILE_ATTRIBUTE_READONLY** 属性。 
  
具有 **FILE_ATTRIBUTE_TEMPORARY** 或 **FILE_ATTRIBUTE_READONLY** 属性的文件设置为，在 Office 中以只读方式打开。 **FILE_ATTRIBUTE_TEMPORARY** 还会阻止该文件显示在最近列表中。 
  
有关文件属性的详细信息，请参阅 [SetFileAttributes 函数](https://msdn.microsoft.com/library/windows/desktop/aa365535%28v=vs.85%29.aspx)。
  
## <a name="other-best-practices"></a>其他最佳做法

为了优化文件的一致性，例如，冲突编辑或错误发生时，应用以下最佳实践：
  
- 阻止保存冲突。
    
  - 发生服务器冲突时，暂停上载以避免分叉（分叉仅出现在 Office 不再打开写入文件时）。通常情况下，如果您的应用程序中的文件在 Office 中打开，则仅在 Office 关闭或被 Windows 挂起时，才会激活您的应用程序。
    
  - 如果你需要 UI 来处理冲突，请使用 toast 通知。 挂起 Office 时，完整 UI 不可用。
    
- 处理错误。
    
  - 当锁定解除时，会通知用户发生冲突，并提供在您的应用程序中解决此问题的路径。
    
## <a name="see-also"></a>另请参阅

- [与 Office 集成](integrate-with-office.md)   
- [从 Win32 同步客户端与 Office 集成](integrate-with-office-from-win32-sync-clients.md)
    

