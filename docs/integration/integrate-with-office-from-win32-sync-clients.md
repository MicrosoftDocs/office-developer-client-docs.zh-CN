---
title: 从 Win32 同步客户端与 Office 集成
manager: soliver
ms.date: 07/29/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 348555d3-3cd4-4e4a-b5ad-436571c25251
description: 将第三方 Win32 同步客户端与 Excel Mobile、PowerPoint Mobile 和 Word Mobile Office 应用程序集成。
ms.openlocfilehash: 83bc6e4cddc17e539b371999fff620c72c595534
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303134"
---
# <a name="integrate-with-office-from-win32-sync-clients"></a><span data-ttu-id="da591-103">从 Win32 同步客户端与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="da591-103">Integrate with Office from Win32 sync clients</span></span>

<span data-ttu-id="da591-104">将第三方 Win32 同步客户端与 Excel Mobile、PowerPoint Mobile 和 Word Mobile Office 应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="da591-104">Integrate your third-party Win32 sync clients with Excel Mobile, PowerPoint Mobile, and Word Mobile Office applications.</span></span> 
  
<span data-ttu-id="da591-p101">您可以将 Windows 通用应用程序与 Excel Mobile、PowerPoint Mobile 和 Word Mobile 客户端通过注册为同步根提供程序来进行集成。本文介绍用于确保您的 Win32 同步客户端很好地使用 Office 应用程序的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="da591-p101">You can integrate your Windows universal app with Excel Mobile, PowerPoint Mobile, and Word Mobile clients by registering as a sync root provider. This article describes the best practices to apply to ensure that your Win32 sync clients work well with Office applications.</span></span>
  
<span data-ttu-id="da591-107">这种集成要求 Win32 同步客户端有同步引擎。</span><span class="sxs-lookup"><span data-stu-id="da591-107">This integration requires that your Win32 sync client has a sync engine.</span></span>
  
## <a name="register-as-a-sync-root-provider"></a><span data-ttu-id="da591-108">注册为同步根提供程序</span><span class="sxs-lookup"><span data-stu-id="da591-108">Register as a sync root provider</span></span>

<span data-ttu-id="da591-p102">除非您的同步客户端已注册为同步根提供程序，否则 Office 将按照它处理常规本地文件的方式处理同步文件夹中的文件。这意味着，当用户尝试共享文档时，Office 将为他们提供"移动至 OneDrive"选项。若要避免对您同步的文件执行此操作，就必须注册为同步根提供程序。有关如何注册的信息，请参阅[集成云存储提供程序](https://msdn.microsoft.com/library/windows/desktop/dn889934%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="da591-p102">Unless your sync client is registered as a sync root provider, Office will treat files in your sync folder the way that it treats regular local files. This means that Office will provide "move to OneDrive" options for users when they attempt to share the document. To avoid this for files you sync, you must register as a sync root provider. For information about how to register, see [Integrate a Cloud Storage Provider](https://msdn.microsoft.com/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span></span>
  
## <a name="integrate-your-app-into-the-root-node-of-the-navigation-pane"></a><span data-ttu-id="da591-113">将您的应用程序集成到导航窗格的根节点</span><span class="sxs-lookup"><span data-stu-id="da591-113">Integrate your app into the root node of the navigation pane</span></span>

<span data-ttu-id="da591-p103">为了在文件资源管理器和 Windows 文件选取器中使 Win32 同步客户端显示为导航窗格中的一个根节点，您需要将您的应用程序集成到根级别。有关如何执行此操作的信息，请参阅[集成云存储提供程序](https://msdn.microsoft.com/library/windows/desktop/dn889934%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="da591-p103">In order for your Win32 sync client to show up as a root node in the navigation pane in the File Explorer and Windows file picker, you need to integrate your app into the root level. For information about how to do this, see [Integrate a Cloud Storage Provider](https://msdn.microsoft.com/library/windows/desktop/dn889934%28v=vs.85%29.aspx).</span></span> 
  
## <a name="add-your-sync-folder-as-a-document-library-optional"></a><span data-ttu-id="da591-116">将您的同步文件夹添加为文档库（可选）</span><span class="sxs-lookup"><span data-stu-id="da591-116">Add your sync folder as a document library (optional)</span></span>

<span data-ttu-id="da591-p104">在 Office 中，用户可以在其文档库中使用单个操作创建文档。若要将您的同步位置添加到文档库，请使用 [SHAddFolderPathToLibrary 函数](https://msdn.microsoft.com/library/windows/desktop/dd378432%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="da591-p104">In Office, users can create documents in their document libraries with a single action. To add your sync location to the document library, use the [SHAddFolderPathToLibrary function](https://msdn.microsoft.com/library/windows/desktop/dd378432%28v=vs.85%29.aspx).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da591-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da591-119">See also</span></span>
<span data-ttu-id="da591-120"><a name="bk_addresources"> </a></span><span class="sxs-lookup"><span data-stu-id="da591-120"><a name="bk_addresources"> </a></span></span>

- [<span data-ttu-id="da591-121">与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="da591-121">Integrate with Office</span></span>](integrate-with-office.md)
    
- [<span data-ttu-id="da591-122">从 Windows 通用应用程序与 Office 集成</span><span class="sxs-lookup"><span data-stu-id="da591-122">Integrate with Office from Windows universal apps</span></span>](integrate-with-office-from-windows-universal-apps.md)
    

