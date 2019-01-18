---
title: 枚举表视图中的项
TOCTitle: Enumerate items in a table view
ms:assetid: c7d9a667-cfec-49c1-af7a-4c8063991588
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184640(v=office.15)
ms:contentKeyID: 55119900
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b3bde66fd07a39aa8a63219876b9bdbcf72e00f7
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717676"
---
# <a name="enumerate-items-in-a-table-view"></a><span data-ttu-id="1ca87-102">枚举表视图中的项</span><span class="sxs-lookup"><span data-stu-id="1ca87-102">Enumerate items in a table view</span></span>

<span data-ttu-id="1ca87-103">此代码示例使用 [GetTable()](https://msdn.microsoft.com/library/ff184699\(v=office.15\)) 方法枚举表视图中的项。</span><span class="sxs-lookup"><span data-stu-id="1ca87-103">This example enumerates items in a table view by using the [GetTable()](https://msdn.microsoft.com/library/ff184699\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="1ca87-104">示例</span><span class="sxs-lookup"><span data-stu-id="1ca87-104">Example</span></span>

<span data-ttu-id="1ca87-p101">下面的代码示例从"收件箱"文件夹的当前视图中获取 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象。该代码示例将活动的资源管理器的当前文件夹设置为收件箱，然后检查收件箱的当前视图是否是表视图。如果当前视图是表，则该代码示例调用 [GetTable()](https://msdn.microsoft.com/library/ff184699\(v=office.15\)) 方法并显示返回的 **Table** 中的各行所表示的各个项目。</span><span class="sxs-lookup"><span data-stu-id="1ca87-p101">The following code example obtains a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object from the current view of the Inbox folder. The code example sets the current folder of the active explorer to the Inbox, and then checks that the current view of the Inbox is a table view. If the current view is a table, the code example calls the [GetTable()](https://msdn.microsoft.com/library/ff184699\(v=office.15\)) method and displays each item represented by each row in the returned **Table**.</span></span>

<span data-ttu-id="1ca87-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="1ca87-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="1ca87-109">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="1ca87-109">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="1ca87-110">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="1ca87-110">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoViewGetTable()
{
    // Obtain Inbox.
    Outlook.Folder inbox =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Set ActiveExplorer.CurrentFolder to Inbox.
    // Inbox must be current folder
    // for View.GetTable to work correctly.
    Application.ActiveExplorer().CurrentFolder = inbox;
    // Ensure that current view is TableView.
    if (inbox.CurrentView.ViewType == 
        Outlook.OlViewType.olTableView)
    {
        Outlook.TableView view = 
            inbox.CurrentView as Outlook.TableView;
        // No arguments needed for View.GetTable.
        Outlook.Table table = view.GetTable();
        Debug.WriteLine("View Count=" 
            + table.GetRowCount().ToString());
        while (!table.EndOfTable)
        {
            // First row in Table.
            Outlook.Row nextRow = table.GetNextRow();
            Debug.WriteLine(nextRow["Subject"]
                + " Modified: "
                + nextRow["LastModificationTime"]);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="1ca87-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ca87-111">See also</span></span>

- [<span data-ttu-id="1ca87-112">视图</span><span class="sxs-lookup"><span data-stu-id="1ca87-112">Views</span></span>](views.md)

