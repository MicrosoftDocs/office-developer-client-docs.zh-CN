---
title: 将 Outlook 与 SharePoint 文件夹同步
TOCTitle: Synchronize Outlook with a SharePoint folder
ms:assetid: fecb04ab-39c6-43e1-9a21-12ecb29d94fb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424483(v=office.15)
ms:contentKeyID: 55119853
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ab8da62d75b5714967c3fbdc0d0f985370e617aa
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540635"
---
# <a name="synchronize-outlook-with-a-sharepoint-folder"></a>将 Outlook 与 SharePoint 文件夹同步

此代码示例展示了如何以编程方式将 Outlook 与 SharePoint 文件夹连接，并同步文件夹内容。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

可将 Outlook 中的日历、联系人列表、任务列表、讨论板和文档库同步到 SharePoint 文件夹。 基于同步时提供的 URL，Outlook 将创建基类型与 SharePoint 文件夹相同的新文件夹。 例如，同步到 SharePoint 日历文件夹时将在 Outlook 中创建新的日历文件夹。 SharePoint 同步文件夹存储在用户邮箱外部的其各自的 Outlook 个人文件夹 (.pst) 文件中。 您可以通过使用 [NameSpace](https://msdn.microsoft.com/library/bb610157\(v=office.15\)) 对象的 [OpenSharedFolder(String, Object, Object, Object)](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法连接到 SharePoint 文件夹。 请注意，您必须使用 stssync:// URL，该 URL 提供有关 SharePoint Server 和文件夹路径的详细信息，以及 Outlook 打开 SharePoint 文件夹所需的其他信息。

当以编程方式连接到 SharePoint 文件夹时，必须确定要用于创建共享关系的正确的 URL。 由于 SharePoint 用户界面中并不提供文件夹的 stssync:// URL，因此需要手动将目标文件夹链接到 Outlook。 然后，使用以下代码示例中的第一个过程 DisplaySharePointUrl 来获取正确的 URL。 DisplaySharePointUrl 使用 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象在活动资源管理器窗口的当前文件夹中查找共享绑定信息。 如果找到了一个或多个绑定上下文，则将显示所有可用共享上下文的 URL。

现在您有了正确的 URL 可用来创建共享关系。 若要在 Outlook 中同步新的 SharePoint 文件夹，请在第二个过程 AddSpsFolder 中复制该 URL 并将其粘贴到字符串变量 calendarUrl 的分配中。 AddSpsFolder 使用 **NameSpace.OpenSharedFolder** 方法和 URL (自动同步 Outlook 中的新 SharePoint 文件夹，即 DisplaySharePointUrl 过程) 生成的 `stssync://` URL。 AddSpsFolder 还提供自定义文件夹名称“SPS 日历示例”，并指定 Outlook 来使用文件夹的默认生存时间 (TTL)。 SharePoint 文件夹始终下载项目附件，这样您就必须在此处进行指定。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DisplaySharePointUrl()
{
    const string PROP_SYNC_URL = 
        "http://schemas.microsoft.com/mapi/id/{00062040-0000-0000-C000-000000000046}/8A24001E";

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

## <a name="see-also"></a>另请参阅

- [组共享](group-sharing.md)

