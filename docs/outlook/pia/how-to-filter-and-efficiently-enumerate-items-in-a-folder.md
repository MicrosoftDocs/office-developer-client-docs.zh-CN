---
title: 筛选并高效枚举文件夹中的项
TOCTitle: Filter and efficiently enumerate items in a folder
ms:assetid: efee7704-b7d9-4586-a72e-4e960ec1ffdb
ms:mtpsurl: https://msdn.microsoft.com/library/Bb612664(v=office.15)
ms:contentKeyID: 55119884
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 35215c24a9b953bf8406b268a6169abbd536202b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705615"
---
# <a name="filter-and-efficiently-enumerate-items-in-a-folder"></a><span data-ttu-id="aeaf4-102">筛选并高效枚举文件夹中的项</span><span class="sxs-lookup"><span data-stu-id="aeaf4-102">Filter and efficiently enumerate items in a folder</span></span>

<span data-ttu-id="aeaf4-103">该示例演示如何使用 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象筛选收件箱中带附件的项目，并高效枚举此类项目，以显示每个项目的所选属性。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-103">This example shows how to use the [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object to filter for items in the Inbox that have attachments, and efficiently enumerate such items, displaying selected properties for each item.</span></span>

## <a name="example"></a><span data-ttu-id="aeaf4-104">示例</span><span class="sxs-lookup"><span data-stu-id="aeaf4-104">Example</span></span>

<span data-ttu-id="aeaf4-105">此代码示例指定包含 MAPI 命名空间的属性 **PR\_HASATTACH**，并使用这个属性在对 Inbox 执行的 [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) 方法中创建初始筛选器。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-105">The code sample specifies the property **PR\_HASATTACH** with the MAPI namespace, and uses the property to create the initial filter in the [GetTable](https://msdn.microsoft.com/library/bb612592\(v=office.15\)) method on the Inbox.</span></span> <span data-ttu-id="aeaf4-106">项类型的 **Table** 对象包含，表示相应项类型的特定属性的默认列。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-106">A **Table** object for an item type has default columns representing certain properties of that item type.</span></span> <span data-ttu-id="aeaf4-107">为自定义这些列，该示例首先对该 [Table](https://msdn.microsoft.com/library/bb611528\(v=office.15\)) 的 [Columns](https://msdn.microsoft.com/library/bb646214\(v=office.15\)) 集合调用 **RemoveAll** 方法，然后对 [Columns](https://msdn.microsoft.com/library/bb652865\(v=office.15\)) 集合调用 **Add** 方法以添加使用内置属性名称的 **EntryID**、 **Subject** 和 **ReceivedTime** 属性，并且 **ReceivedTime** 列用于存储采用本地日期时间表示形式的值。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-107">To customize the columns, this example first calls the [RemoveAll](https://msdn.microsoft.com/library/bb611528\(v=office.15\)) method on the [Columns](https://msdn.microsoft.com/library/bb646214\(v=office.15\)) collection of that **Table**, and then calls the [Add](https://msdn.microsoft.com/library/bb652865\(v=office.15\)) method on the **Columns** collection to add the **EntryID**, **Subject**, and **ReceivedTime** properties using the built-in property names, with the **ReceivedTime** column storing values in local date-time representation.</span></span> 

<span data-ttu-id="aeaf4-108">该示例然后再次调用 **Columns.Add** 以添加 **ReceiveTime** 属性，从而指定其 MAPI 命名空间，因此，该列会将值存储为协调世界时 (UTC) 日期时间值。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-108">The example then calls **Columns.Add** one more time to add the **ReceiveTime** property specifying its MAPI namespace so that this column will store the value as a Universal Coordinated Time (UTC) date-time value.</span></span> <span data-ttu-id="aeaf4-109">最后，此代码示例枚举 Table 中的每一项，同时显示指定为表列的四个属性的值。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-109">Finally, the example enumerates each item in the Table, displaying the value of each of the four properties specified as the table columns.</span></span>

<span data-ttu-id="aeaf4-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="aeaf4-111">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-111">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="aeaf4-112">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="aeaf4-112">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub DemoTableColumns()
    Const PR_HAS_ATTACH As String = _
        "https://schemas.microsoft.com/mapi/proptag/0x0E1B000B"
    ' Obtain Inbox
    Dim folder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderInbox), _
        Outlook.Folder)
    ' Create filter
    Dim filter As String = "@SQL=" & Chr(34) _
        & PR_HAS_ATTACH & Chr(34) & " = 1"
    Dim table As Outlook.Table = _
        folder.GetTable(filter, _
        Outlook.OlTableContents.olUserItems)
    ' Remove default columns
    table.Columns.RemoveAll()
    ' Add using built-in name
    table.Columns.Add("EntryID")
    table.Columns.Add("Subject")
    table.Columns.Add("ReceivedTime")
    table.Sort("ReceivedTime", Outlook.OlSortOrder.olDescending)
    ' Add using namespace
    ' Date received
    table.Columns.Add( _
        "urn:schemas:httpmail:datereceived")
    While Not (table.EndOfTable)
        Dim nextRow As Outlook.Row = table.GetNextRow()
        Dim sb As StringBuilder = New StringBuilder()
        sb.AppendLine(nextRow("Subject").ToString())
        ' Reference column by name 
        sb.AppendLine("Received (Local): " _
            & nextRow("ReceivedTime").ToString())
        ' Reference column by index
        sb.AppendLine("Received (UTC): " & nextRow(4).ToString())
        sb.AppendLine()
        Debug.WriteLine(sb.ToString())
    End While
End Sub
```


```csharp
private void DemoTableColumns()
{
    const string PR_HAS_ATTACH =
        "https://schemas.microsoft.com/mapi/proptag/0x0E1B000B";
    // Obtain Inbox
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Create filter
    string filter = "@SQL=" + "\""
        + PR_HAS_ATTACH + "\"" + " = 1";
    Outlook.Table table =
        folder.GetTable(filter,
        Outlook.OlTableContents.olUserItems);
    // Remove default columns
    table.Columns.RemoveAll();
    // Add using built-in name
    table.Columns.Add("EntryID");
    table.Columns.Add("Subject");
    table.Columns.Add("ReceivedTime");
    table.Sort("ReceivedTime", Outlook.OlSortOrder.olDescending);
    // Add using namespace
    // Date received
    table.Columns.Add(
        "urn:schemas:httpmail:datereceived");
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        StringBuilder sb = new StringBuilder();
        sb.AppendLine(nextRow["Subject"].ToString());
        // Reference column by name 
        sb.AppendLine("Received (Local): "
            + nextRow["ReceivedTime"]);
        // Reference column by index
        sb.AppendLine("Received (UTC): " + nextRow[4]);
        sb.AppendLine();
        Debug.WriteLine(sb.ToString());
    }
}
```

## <a name="see-also"></a><span data-ttu-id="aeaf4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aeaf4-113">See also</span></span>

- [<span data-ttu-id="aeaf4-114">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="aeaf4-114">Search and filter</span></span>](search-and-filter.md)

