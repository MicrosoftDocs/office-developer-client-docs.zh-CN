---
title: 将 Outlook 与 SharePoint 文件夹同步
TOCTitle: Synchronize Outlook with a SharePoint folder
ms:assetid: fecb04ab-39c6-43e1-9a21-12ecb29d94fb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424483(v=office.15)
ms:contentKeyID: 55119853
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d7fdf4f6cf9d6d473257d335ce968ce8f518ebe2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407175"
---
# <a name="synchronize-outlook-with-a-sharepoint-folder"></a><span data-ttu-id="9ad2a-102">将 Outlook 与 SharePoint 文件夹同步</span><span class="sxs-lookup"><span data-stu-id="9ad2a-102">How to: Synchronize Outlook with a SharePoint Folder</span></span>

<span data-ttu-id="9ad2a-103">此代码示例展示了如何以编程方式将 Outlook 与 SharePoint 文件夹连接，并同步文件夹内容。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-103">This example shows how to programmatically connect Outlook with a SharePoint folder and to synchronize the folder contents.</span></span>

## <a name="example"></a><span data-ttu-id="9ad2a-104">示例</span><span class="sxs-lookup"><span data-stu-id="9ad2a-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="9ad2a-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="9ad2a-106">可将 Outlook 中的日历、联系人列表、任务列表、讨论板和文档库同步到 SharePoint 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-106">In Outlook, you can synchronize calendars, contact lists, task lists, discussion boards, and document libraries to SharePoint folders.</span></span> <span data-ttu-id="9ad2a-107">基于同步时提供的 URL，Outlook 将创建基类型与 SharePoint 文件夹相同的新文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-107">Based on the URL provided upon synchronization, Outlook will create a new folder of the same base type as the SharePoint folder.</span></span> <span data-ttu-id="9ad2a-108">例如，如果同步到 SharePoint 日历文件夹，便可在 Outlook 中新建日历文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-108">For example, synchronizing to a SharePoint calendar folder will create a new calendar folder in Outlook.</span></span> <span data-ttu-id="9ad2a-109">SharePoint 同步文件夹的存储位置为，其各自在用户邮箱外部的 Outlook 个人文件夹 (.pst) 文件中。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-109">SharePoint synchronization folders are stored in their own Outlook Personal Folders (.pst) file outside of the user's mailbox.</span></span> <span data-ttu-id="9ad2a-110">可使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 方法连接到 SharePoint 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-110">You can connect to a SharePoint folder by using the [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) method of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span> <span data-ttu-id="9ad2a-111">请注意，您必须使用 stssync:// URL，该 URL 提供有关 SharePoint Server 和文件夹路径的详细信息，以及 Outlook 打开 SharePoint 文件夹所需的其他信息。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-111">Note that you must use a stssync:// URL that provides details about the SharePoint server, folder path, and other information that Outlook needs to open a SharePoint folder.</span></span>

<span data-ttu-id="9ad2a-112">当以编程方式连接到 SharePoint 文件夹时，必须确定要用于创建共享关系的正确的 URL。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-112">When connecting to a SharePoint folder programmatically, you must determine the proper URL to use to create the sharing relationship.</span></span> <span data-ttu-id="9ad2a-113">由于未在文件夹的 SharePoint 用户界面中提供 stssync:// URL，因此需要手动将目标文件夹链接到 Outlook。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-113">Because the stssync:// URL is not provided in the SharePoint user interface for the folder, manually link the destination folder into Outlook.</span></span> <span data-ttu-id="9ad2a-114">然后，使用下面代码示例中的第一个过程 DisplaySharePointUrl，以获取正确 URL。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-114">Then use the first procedure,  , in the following code example, to get the correct URL.</span></span> <span data-ttu-id="9ad2a-115">DisplaySharePointUrl 使用 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象，在有效资源管理器窗口的当前文件夹中查找共享绑定信息。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-115"> uses the Table object to look for the sharing binding information in the current folder for the active explorer window.</span></span> <span data-ttu-id="9ad2a-116">如果找到一个或多个绑定上下文，它便会显示所有可用共享上下文的 URL。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-116">If one or more binding contexts are found, the URLs for all available sharing contexts will be displayed.</span></span>

<span data-ttu-id="9ad2a-117">现在便拥有可用于创建共享关系的正确 URL。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-117">Now you have the proper URL to create the sharing relationship.</span></span> <span data-ttu-id="9ad2a-118">若要在 Outlook 中同步新 SharePoint 文件夹，请在第二个过程 AddSpsFolder 中将 URL 复制并粘贴到分配的字符串变量 calendarUrl 中。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-118">To synchronize the new SharePoint folder in Outlook, copy and paste the URL to the assignment of the string variable   in the second procedure,  .</span></span> <span data-ttu-id="9ad2a-119">AddSpsFolder 结合使用 **NameSpace.OpenSharedFolder** 方法和 `stssync://` URL（在此示例中，即为 DisplaySharePointUrl 过程生成的 URL），自动在 Outlook 中同步新 SharePoint 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-119"> automates the synchronization of the new SharePoint folder in Outlook by using the NameSpace.OpenSharedFolder method with a stssync:// URL (in this case, the URL produced by the   procedure).</span></span> <span data-ttu-id="9ad2a-120">AddSpsFolder 还提供自定义文件夹名称“示例 SPS 日历”，并指定 Outlook 使用文件夹的默认生存时间 (TTL)。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-120">also provides a custom folder name, "Example SPS Calendar", and specifies Outlook to use the default Time to Live (TTL) for the folder.</span></span> <span data-ttu-id="9ad2a-121">因为 SharePoint 文件夹始终下载项附件，所以此时无需指定这一点。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-121">SharePoint folders always download item attachments, so you do not have to specify that here.</span></span>

<span data-ttu-id="9ad2a-122">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-122">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="9ad2a-123">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-123">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="9ad2a-124">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="9ad2a-124">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DisplaySharePointUrl()
{
    const string PROP_SYNC_URL = 
        "https://schemas.microsoft.com/mapi/id/{00062040-0000-0000-C000-000000000046}/8A24001E";

    Outlook.Folder folder = Application.ActiveExplorer().CurrentFolder as Outlook.Folder;
    Outlook.Table table = folder.GetTable(Type.Missing, Outlook.OlTableContents.olHiddenItems);
    table.Columns.RemoveAll();
    table.Columns.Add("MessageClass");
    table.Columns.Add(PROP_SYNC_URL);

    StringBuilder sb = new StringBuilder();
    while (!table.EndOfTable)
    {
        Outlook.Row row = table.GetNextRow();
        string msgClass, spsUrl;
        msgClass = row["MessageClass"] as string;
        spsUrl = row[PROP_SYNC_URL] as string;

        if (msgClass == "IPM.Sharing.Binding.In")
        {
            sb.Append(spsUrl);
            sb.Append("\r\n");
        }
    }
    if (sb.Length > 0)
    {
        System.Windows.Forms.MessageBox.Show(
            "The following SharePoint Folder URLs were found:\r\n" + sb.ToString());
    }
    else
    {
        System.Windows.Forms.MessageBox.Show("No SharePoint URLs were found in this folder.");
    }
}

private void AddSpsFolder()
{
    string calendarUrl = "stssync://sts/?ver=1.1&type=calendar&cmd=add-folder&base-url=
        https://example.org/calendar&list-url=/Lists/Calendar/calendar.aspx&guid=&site-name=
        Example%20Site&list-name=Calendar";
    string folderName = "Example SPS Calendar";
    bool useDefaultTTL = true;
    Outlook.Folder calendarFolder =
        Application.Session.OpenSharedFolder(calendarUrl, folderName, Type.Missing, useDefaultTTL) 
        as Outlook.Folder;
    Outlook.Explorer exp =
        Application.Explorers.Add(calendarFolder, Outlook.OlFolderDisplayMode.olFolderDisplayNormal);
    exp.Display();
}
```

## <a name="see-also"></a><span data-ttu-id="9ad2a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9ad2a-125">See also</span></span>

- [<span data-ttu-id="9ad2a-126">组共享</span><span class="sxs-lookup"><span data-stu-id="9ad2a-126">Group Sharing</span></span>](group-sharing.md)

