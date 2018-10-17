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
# <a name="subscribe-to-an-rss-feed"></a>订阅 RSS 源

此代码示例展示了如何使用 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 方法订阅 RSS 源。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

Outlook 对象模型支持提供对共享数据（如 Internet 日历、RSS 源和 Microsoft SharePoint 列表和文档库中的数据）的访问。这样就能够连接到这些共享数据源，并设置同步上下文以继续轮询这些共享资源。Outlook 对象模型提供 [NameSpace](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 对象的 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法，用来下载特定类型的共享文件夹并与之保持同步。

在下面的示例中，AddRssFeed 使用引用名为“示例 RSS 源”的新 RSS 源的 URL 调用 **OpenSharedFolder** 方法，从而订阅该新的 RSS 源。**OpenSharedFolder** 方法的最后两个参数设置为 **true**，用于指示应下载附件并且 Outlook 应使用 RSS 源中提供的刷新频率。


> [!NOTE]
> 必须为 **OpenSharedFolder** 方法中的文件夹 URL 指定正确的协议处理程序，才能订阅 RSS 源。 例如，必须使用以 `feed://`（而不是 `https://`）开头的 URL。 除非 Windows NT LAN Manager (NTLM) 身份验证可用，否则 Outlook 无法打开需要身份验证的 RSS 源，它也无法从安全套接字层 (SSL) 位置加载 RSS 源。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [组共享](group-sharing.md)

