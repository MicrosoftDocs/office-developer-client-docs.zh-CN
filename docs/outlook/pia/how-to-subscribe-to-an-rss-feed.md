---
title: 订阅 RSS 源
TOCTitle: Subscribe to an RSS feed
ms:assetid: 7ecefbcd-1a34-48e8-afac-7d54e79fd159
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424473(v=office.15)
ms:contentKeyID: 55119852
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 30370e54e25cad6bc4f138f9d8cc0c8a156b8428
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405824"
---
# <a name="subscribe-to-an-rss-feed"></a><span data-ttu-id="d4902-102">订阅 RSS 源</span><span class="sxs-lookup"><span data-stu-id="d4902-102">Subscribe to an RSS feed</span></span>

<span data-ttu-id="d4902-103">此代码示例展示了如何使用 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 方法订阅 RSS 源。</span><span class="sxs-lookup"><span data-stu-id="d4902-103">This example shows how to subscribe to an RSS feed by using the [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="d4902-104">示例</span><span class="sxs-lookup"><span data-stu-id="d4902-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="d4902-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="d4902-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="d4902-p101">Outlook 对象模型支持提供对共享数据（如 Internet 日历、RSS 源和 Microsoft SharePoint 列表和文档库中的数据）的访问。这样就能够连接到这些共享数据源，并设置同步上下文以继续轮询这些共享资源。Outlook 对象模型提供 [NameSpace](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 对象的 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法，用来下载特定类型的共享文件夹并与之保持同步。</span><span class="sxs-lookup"><span data-stu-id="d4902-p101">The Outlook object model supports providing access to shared data, such as Internet calendars, RSS feeds, and data from Microsoft SharePoint lists and document libraries. It enables connecting to these shared sources of data and setting up the synchronization contexts to continue to poll those shared resources. The Outlook object model provides the [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) method of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object to download and synchronize with a particular type of shared folder.</span></span>

<span data-ttu-id="d4902-p102">在下面的示例中，AddRssFeed 使用引用名为“示例 RSS 源”的新 RSS 源的 URL 调用 **OpenSharedFolder** 方法，从而订阅该新的 RSS 源。**OpenSharedFolder** 方法的最后两个参数设置为 **true**，用于指示应下载附件并且 Outlook 应使用 RSS 源中提供的刷新频率。</span><span class="sxs-lookup"><span data-stu-id="d4902-p102">In the following example, AddRssFeed subscribes to a new RSS feed named “Example RSS Feed” by calling the **OpenSharedFolder** method with a URL that refers to the new RSS feed. The last two parameters of **OpenSharedFolder** method are set to **true** to indicate that attachments should be downloaded, and Outlook should use the refresh ratio provided in the RSS feed.</span></span>


> [!NOTE]
> <span data-ttu-id="d4902-111">必须为 **OpenSharedFolder** 方法中的文件夹 URL 指定正确的协议处理程序，才能订阅 RSS 源。</span><span class="sxs-lookup"><span data-stu-id="d4902-111">You must specify the correct protocol handler for the folder URL in the **OpenSharedFolder** method to subscribe to an RSS feed.</span></span> <span data-ttu-id="d4902-112">例如，必须使用以 `feed://`（而不是 `https://`）开头的 URL。</span><span class="sxs-lookup"><span data-stu-id="d4902-112">For example, you must use a URL that begins with feed:// instead of http://.</span></span> <span data-ttu-id="d4902-113">除非 Windows NT LAN Manager (NTLM) 身份验证可用，否则 Outlook 无法打开需要身份验证的 RSS 源，它也无法从安全套接字层 (SSL) 位置加载 RSS 源。</span><span class="sxs-lookup"><span data-stu-id="d4902-113">Outlook cannot open RSS feeds that require authentication unless Windows NT LAN Manager (NTLM) authentication is available, and it cannot load RSS feeds from Secure Sockets Layer (SSL) locations.</span></span>

<span data-ttu-id="d4902-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d4902-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="d4902-115">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d4902-115">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="d4902-116">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d4902-116">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AddRssFeed()
{
    string feedUrl = "feed://example.org/rssfeed.xml";
    Outlook.Folder subscriptionFolder =
        Application.Session.OpenSharedFolder(feedUrl, "Example RSS Feed", true, true) as Outlook.Folder;
    Outlook.Explorer exp =
        Application.Explorers.Add(subscriptionFolder, Outlook.OlFolderDisplayMode.olFolderDisplayNormal);
    exp.Display();
}
```

## <a name="see-also"></a><span data-ttu-id="d4902-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4902-117">See also</span></span>

- [<span data-ttu-id="d4902-118">组共享</span><span class="sxs-lookup"><span data-stu-id="d4902-118">Group Sharing</span></span>](group-sharing.md)

