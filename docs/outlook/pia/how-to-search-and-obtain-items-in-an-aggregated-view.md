---
title: 搜索并在聚合视图中返回项目
TOCTitle: Search and obtain items in an aggregated view
ms:assetid: 1a875dc8-dd52-4e9c-b292-5f6ba3d7a940
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184592(v=office.15)
ms:contentKeyID: 55119925
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 540557973d395c23d26a87502ed6ba43176a0a3c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407574"
---
# <a name="search-and-obtain-items-in-an-aggregated-view"></a>搜索并在聚合视图中返回项目

本示例演示如何搜索多个文件夹和存储内的项目以及如何在聚合视图中返回这些项目。

## <a name="example"></a>示例

[TableView](https://msdn.microsoft.com/library/bb608854\(v=office.15\)) 对象的 [GetTable()](https://msdn.microsoft.com/library/ff184699\(v=office.15\)) 方法可在聚合视图中返回包含的项目来自同一存储或多个存储中的一个或多个文件夹的 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象。 在想要访问从某个搜索（例如，在存储内的所有邮件项上进行的搜索）返回的项目时，此功能十分有用。 本主题提供了一个示例，用来展示如何使用**即时搜索**来搜索当前用户的经理发送来的所有标记为重要的项目并在之后显示每个搜索结果的主题。

在以下代码示例中，**GetItemsInView** 方法会检查当前用户的主要送达存储帐户是否是 Exchange 帐户、当前用户是否有经理以及是否可在相应会话的默认存储中执行**即时搜索**。 由于搜索依赖于 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象的 [Search](https://msdn.microsoft.com/library/bb610561\(v=office.15\)) 方法，且搜索结果需使用 **GetTable** 方法获得，因此 **GetItemsInView** 会创建 **Explorer** 对象、在该对象中显示 Inbox 并用其设置搜索。 

**GetItemsInView** 会在所有 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 类型的文件夹中搜索来自当前用户的经理且标记为重要的项目。 在 **GetItemsInView** 调用 [Search](https://msdn.microsoft.com/library/bb610561\(v=office.15\)) 方法之后，所有搜索结果都会显示在资源管理器中，包括来自其他文件夹和存储的符合搜索条件的项目。 **GetItemsInView** 会获取包含搜索结果的此资源管理器视图的 **TableView** 对象。 然后，通过使用此 **TableView** 对象的 **GetTable** 方法，**GetItemsInView** 会得到包含搜索返回的聚合项目的 **Table** 对象。 最后，**GetItemsInView** 会显示 **Table** 对象的每一行（一行代表搜索结果中的一项）的主题栏。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetItemsInView()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;

    // Check whether the current user uses the Exchange Server.
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            currentUser.GetExchangeUser().GetExchangeUserManager();

        // Check whether the current user has a manager.
        if (manager != null)
        {
            string managerName = manager.Name;

            // Check whether Instant Search is enabled and 
            // operational in the default store.
            if (Application.Session.DefaultStore.IsInstantSearchEnabled)
            {
                Outlook.Folder inbox =
                    Application.Session.GetDefaultFolder(
                    Outlook.OlDefaultFolders.olFolderInbox);

                // Create a new explorer to display the Inbox as
                // the current folder.
                Outlook.Explorer explorer =
                    Application.Explorers.Add(inbox,
                    Outlook.OlFolderDisplayMode.olFolderDisplayNormal);

                // Make the new explorer visible.
                explorer.Display;

                // Search for items from the manager marked important, 
                // from all folders of the same item type as the current folder, 
                // which is the MailItem item type.
                string searchFor =
                    "from:" + "\"" + managerName 
                    + "\"" + " importance:high";
                explorer.Search(searchFor,
                    Outlook.OlSearchScope.olSearchScopeAllFolders);

                // Any search results are displayed in that new explorer
                // in an aggregated table view.
                Outlook.TableView tableView = 
                    explorer.CurrentView as Outlook.TableView;

                // Use GetTable of that table view to obtain items in that
                // aggregated view in a Table object.
                Outlook.Table table = tableView.GetTable();
                while (!table.EndOfTable)
                {
                    // Then display each row in the Table object
                    // that represents an item in the search results.
                    Outlook.Row nextRow = table.GetNextRow();
                    Debug.WriteLine(nextRow["Subject"]);
                }
            }
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

