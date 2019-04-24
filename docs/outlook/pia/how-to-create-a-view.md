---
title: 创建视图
TOCTitle: Create a view
ms:assetid: 2f8ad187-1030-420a-bc74-c327e3521550
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424468(v=office.15)
ms:contentKeyID: 55119902
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c91f43001d6c56ad3b4c316aede9845a5e0a0064
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349488"
---
# <a name="create-a-view"></a>创建视图

此示例展示如何使用 [Views](https://msdn.microsoft.com/library/bb644226\(v=office.15\)) 集合的 [Add(String, OlViewType, OlViewSaveOption)](https://msdn.microsoft.com/library/bb643986\(v=office.15\)) 方法创建 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象视图。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


可以创建可自定义的视图，使得您能够在 Outlook 资源管理器窗口的“视图窗格”中排序、分组和查看所有不同类型的数据。也可以通过编程方式自定义内置视图。下表列出了表示 Outlook 视图的对象。 

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>对象名称</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/bb646315(v=office.15)">BusinessCardView</a></p></td>
<td><p>数据会作为一系列电子名片图像显示。</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/bb622874(v=office.15)">CalendarView</a></p></td>
<td><p>数据会以日历格式显示。</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/bb609216(v=office.15)">CardView</a></p></td>
<td><p>数据会在一系列卡片中显示。</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/bb612031(v=office.15)">IconView</a></p></td>
<td><p>数据会作为 Windows 文件夹图标或资源管理器图标显示。</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/library/bb608854(v=office.15)">TableView</a></p></td>
<td><p>数据会在基于字段的简单表格中显示。</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/library/bb609455(v=office.15)">TimelineView</a></p></td>
<td><p>数据会在可自定义的线性时间线中显示。</p></td>
</tr>
</tbody>
</table>


你可以使用 [View](https://msdn.microsoft.com/library/bb647396\(v=office.15\)) 对象访问所有视图的通用属性和方法。 但是，若要访问并非对所有视图均通用的特定属性，则必须将 **View** 对象转换为要访问的属性所属的派生 **View** 对象。 例如，若要访问 **Cardview** 对象的 [HeadingsFont](https://msdn.microsoft.com/library/bb612522\(v=office.15\)) 属性，需将 **View** 对象转换为 **Cardview** 对象。 如果要确定某个 **View** 对象所代表的视图类型，请使用 [ViewType](https://msdn.microsoft.com/library/bb623693\(v=office.15\)) 属性。

若要创建新的视图，请将 **Views** 集合的 **Add** 方法用于 **Folder** 对象。 然后，设置视图的可见性，该操作可在创建视图时执行，也可在创建后的任意时间执行。 若要在创建时设置视图的可见性，请在 **Add** 方法的 *SaveOption* 参数中指定 [OlViewSaveOption](https://msdn.microsoft.com/library/bb647502\(v=office.15\)) 常量。 若要在创建视图后的任何时间设置可见性，请为 **View** 对象的 [SaveOption](https://msdn.microsoft.com/library/bb646426\(v=office.15\)) 属性指定 **OlViewSaveOption** 常量。 

添加新视图时将引发 [Views](https://msdn.microsoft.com/library/bb647550\(v=office.15\)) 集合的 **ViewAdd** 事件。 在创建视图之后，通过将 **View** 对象转换为派生对象之一然后进行所需的更改，以编程方式自定义视图。 使用派生 **View** 对象或 **View** 对象的 **Save** 方法保存视图的所有更改。 最后，使用派生 **View** 对象或 **View** 对象的 **Apply** 方法将该视图应用于当前 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象。 这会引发 **Explorer** 对象的 [ViewSwitch](https://msdn.microsoft.com/library/bb644066\(v=office.15\)) 事件。

在下面的代码示例中，CreateMeetingRequestsView 通过将 **View** 对象转换为 **TableView** 对象，向用户的收件箱中添加一个名为“会议请求”的新视图。 然后，CreateMeetingRequestsView 会调用 **Views** 对象的 **Add** 方法，并将 *Name* 参数设置为“会议请求”、将 *ViewType* 参数设置为 **olTableView**。 将 **TableView** 对象的 [Filter](https://msdn.microsoft.com/library/bb610296\(v=office.15\)) 属性设置为 DAV 搜索和定位 (DASL) 字符串，这样，只有当项目的邮件类中包含“IPM.Schedule”时，才会显示视图。 然后，系统会保存并应用新视图。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateMeetingRequestsView()
{
    const string PR_MESSAGE_CLASS =
        "https://schemas.microsoft.com/mapi/proptag/0x001A001E";
    Outlook.Views views =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox).Views;
    Outlook.TableView tableView = (Outlook.TableView)
        views.Add("Meeting Requests",
        Outlook.OlViewType.olTableView,
        Outlook.OlViewSaveOption.olViewSaveOptionThisFolderEveryone);
    tableView.Filter = "\"" + PR_MESSAGE_CLASS + "\"" +
        " like 'IPM.Schedule%'";
    tableView.Save();
    tableView.Apply();
}
```

## <a name="see-also"></a>另请参阅

- [视图](views.md)

