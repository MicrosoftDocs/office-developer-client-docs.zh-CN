---
title: 创建视图
TOCTitle: Create a view
ms:assetid: 2f8ad187-1030-420a-bc74-c327e3521550
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424468(v=office.15)
ms:contentKeyID: 55119902
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: e9a68fc6220e1439e517b3d4e7e2ecb30b919ee0
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406027"
---
# <a name="create-a-view"></a><span data-ttu-id="81e43-102">创建视图</span><span class="sxs-lookup"><span data-stu-id="81e43-102">Create a map view programmatically</span></span>

<span data-ttu-id="81e43-103">此示例展示如何使用 [Views](https://msdn.microsoft.com/library/bb644226\(v=office.15\)) 集合的 [Add(String, OlViewType, OlViewSaveOption)](https://msdn.microsoft.com/library/bb643986\(v=office.15\)) 方法创建 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象视图。</span><span class="sxs-lookup"><span data-stu-id="81e43-103">This example shows how to use the [Add(String, OlViewType, OlViewSaveOption)](https://msdn.microsoft.com/library/bb643986\(v=office.15\)) method of the [Views](https://msdn.microsoft.com/library/bb644226\(v=office.15\)) collection to create a view for a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object.</span></span>

## <a name="example"></a><span data-ttu-id="81e43-104">示例</span><span class="sxs-lookup"><span data-stu-id="81e43-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="81e43-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="81e43-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="81e43-p101">可以创建可自定义的视图，使得您能够在 Outlook 资源管理器窗口的“视图窗格”中排序、分组和查看所有不同类型的数据。也可以通过编程方式自定义内置视图。下表列出了表示 Outlook 视图的对象。 </span><span class="sxs-lookup"><span data-stu-id="81e43-p101">You can create customizable views that allow you to sort, group, and view data of all different types within the View Pane of the Outlook explorer window. You can also customize built-in views programmatically. The following table lists objects that represent Outlook views.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="81e43-109">对象名称</span><span class="sxs-lookup"><span data-stu-id="81e43-109">Object Name</span></span></p></th>
<th><p><span data-ttu-id="81e43-110">说明</span><span class="sxs-lookup"><span data-stu-id="81e43-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e43-111"><a href="https://msdn.microsoft.com/library/bb646315(v=office.15)">BusinessCardView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-111"><a href="https://msdn.microsoft.com/library/bb646315(v=office.15)">BusinessCardView Object</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-112">数据会作为一系列电子名片图像显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-112">Data is viewed as a series of Electronic Business Card images.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e43-113"><a href="https://msdn.microsoft.com/library/bb622874(v=office.15)">CalendarView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-113"><a href="https://msdn.microsoft.com/library/bb622874(v=office.15)">CalendarView</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-114">数据会以日历格式显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-114">Data is viewed in a calendar format.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e43-115"><a href="https://msdn.microsoft.com/library/bb609216(v=office.15)">CardView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-115"><a href="https://msdn.microsoft.com/library/bb609216(v=office.15)">CardView Object</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-116">数据会在一系列卡片中显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-116">Data is viewed in a series of cards.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e43-117"><a href="https://msdn.microsoft.com/library/bb612031(v=office.15)">IconView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-117"><a href="https://msdn.microsoft.com/library/bb612031(v=office.15)">IconView Object</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-118">数据会作为 Windows 文件夹图标或资源管理器图标显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-118">Data is viewed as Windows folder icons or explorer icons.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="81e43-119"><a href="https://msdn.microsoft.com/library/bb608854(v=office.15)">TableView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-119"><a href="https://msdn.microsoft.com/library/bb608854(v=office.15)">TableView Object</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-120">数据会在基于字段的简单表格中显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-120">Data is viewed in a simple field-based table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e43-121"><a href="https://msdn.microsoft.com/library/bb609455(v=office.15)">TimelineView</a></span><span class="sxs-lookup"><span data-stu-id="81e43-121"><a href="https://msdn.microsoft.com/library/bb609455(v=office.15)">TimelineView Object</a></span></span></p></td>
<td><p><span data-ttu-id="81e43-122">数据会在可自定义的线性时间线中显示。</span><span class="sxs-lookup"><span data-stu-id="81e43-122">Data is viewed in a customizable linear time line.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="81e43-123">你可以使用 [View](https://msdn.microsoft.com/library/bb647396\(v=office.15\)) 对象访问所有视图的通用属性和方法。</span><span class="sxs-lookup"><span data-stu-id="81e43-123">You can access properties and methods that are common to all views by using the [View](https://msdn.microsoft.com/library/bb647396\(v=office.15\)) object.</span></span> <span data-ttu-id="81e43-124">但是，若要访问并非对所有视图均通用的特定属性，则必须将 **View** 对象转换为要访问的属性所属的派生 **View** 对象。</span><span class="sxs-lookup"><span data-stu-id="81e43-124">However, to access certain properties that are not common to all views, you must cast the View object to a derived view object that the property you want to access belongs to.</span></span> <span data-ttu-id="81e43-125">例如，若要访问 **Cardview** 对象的 [HeadingsFont](https://msdn.microsoft.com/library/bb612522\(v=office.15\)) 属性，需将 **View** 对象转换为 **Cardview** 对象。</span><span class="sxs-lookup"><span data-stu-id="81e43-125">For example, to access the [HeadingsFont](https://msdn.microsoft.com/library/bb612522\(v=office.15\)) property of the **Cardview** object, cast the **View** object to the **CardView** object.</span></span> <span data-ttu-id="81e43-126">如果要确定某个 **View** 对象所代表的视图类型，请使用 [ViewType](https://msdn.microsoft.com/library/bb623693\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="81e43-126">If you want to determine which type of view is represented by a particular **View** object, use the [ViewType](https://msdn.microsoft.com/library/bb623693\(v=office.15\)) property.</span></span>

<span data-ttu-id="81e43-127">若要创建新的视图，请将 **Views** 集合的 **Add** 方法用于 **Folder** 对象。</span><span class="sxs-lookup"><span data-stu-id="81e43-127">To create a new view, use the **Add** method of the **Views** collection for a **Folder** object.</span></span> <span data-ttu-id="81e43-128">然后，设置视图的可见性，该操作可在创建视图时执行，也可在创建后的任意时间执行。</span><span class="sxs-lookup"><span data-stu-id="81e43-128">Then set the visibility for the view either at the time of creation, or at any time after the view is created.</span></span> <span data-ttu-id="81e43-129">若要在创建时设置视图的可见性，请在 **Add** 方法的 *SaveOption* 参数中指定 [OlViewSaveOption](https://msdn.microsoft.com/library/bb647502\(v=office.15\)) 常量。</span><span class="sxs-lookup"><span data-stu-id="81e43-129">To set the visibility for the view at the time of creation, specify an [OlViewSaveOption](https://msdn.microsoft.com/library/bb647502\(v=office.15\)) constant in the  *SaveOption* parameter of the **Add** method.</span></span> <span data-ttu-id="81e43-130">若要在创建视图后的任何时间设置可见性，请为 **View** 对象的 [SaveOption](https://msdn.microsoft.com/library/bb646426\(v=office.15\)) 属性指定 **OlViewSaveOption** 常量。</span><span class="sxs-lookup"><span data-stu-id="81e43-130">To set the visibility at any time after the view is created, specify an **OlViewSaveOption** constant for the [SaveOption](https://msdn.microsoft.com/library/bb646426\(v=office.15\)) property of the **View** object.</span></span> 

<span data-ttu-id="81e43-131">添加新视图时将引发 [Views](https://msdn.microsoft.com/library/bb647550\(v=office.15\)) 集合的 **ViewAdd** 事件。</span><span class="sxs-lookup"><span data-stu-id="81e43-131">Adding a new view raises the [ViewAdd](https://msdn.microsoft.com/library/bb647550\(v=office.15\)) event of the **Views** collection.</span></span> <span data-ttu-id="81e43-132">在创建视图之后，通过将 **View** 对象转换为派生对象之一然后进行所需的更改，以编程方式自定义视图。</span><span class="sxs-lookup"><span data-stu-id="81e43-132">Once the view is created, customize the view programmatically by casting the **View** object to one of the derived objects and then making necessary changes.</span></span> <span data-ttu-id="81e43-133">使用派生 **View** 对象或 **View** 对象的 **Save** 方法保存视图的所有更改。</span><span class="sxs-lookup"><span data-stu-id="81e43-133">Use the Save method of the derived view object or the View object to save any changes to the view.</span></span> <span data-ttu-id="81e43-134">最后，使用派生 **View** 对象或 **View** 对象的 **Apply** 方法将该视图应用于当前 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="81e43-134">Finally, use the Apply method of the derived view object or the View object to apply the view to the current Explorer object.</span></span> <span data-ttu-id="81e43-135">这会引发 **Explorer** 对象的 [ViewSwitch](https://msdn.microsoft.com/library/bb644066\(v=office.15\)) 事件。</span><span class="sxs-lookup"><span data-stu-id="81e43-135">This raises the [ViewSwitch](https://msdn.microsoft.com/library/bb644066\(v=office.15\)) event of the **Explorer** object.</span></span>

<span data-ttu-id="81e43-136">在下面的代码示例中，CreateMeetingRequestsView 通过将 **View** 对象转换为 **TableView** 对象，向用户的收件箱中添加一个名为“会议请求”的新视图。</span><span class="sxs-lookup"><span data-stu-id="81e43-136">In the following code example,   adds a new view named "Meeting Requests" to the user's Inbox by casting the View object to a TableView object.</span></span> <span data-ttu-id="81e43-137">然后，CreateMeetingRequestsView 会调用 **Views** 对象的 **Add** 方法，并将 *Name* 参数设置为“会议请求”、将 *ViewType* 参数设置为 **olTableView**。</span><span class="sxs-lookup"><span data-stu-id="81e43-137"> then calls the Add method of the Views object with the  Name parameter set to "Meeting Requests" and the  ViewType parameter set to olTableView.</span></span> <span data-ttu-id="81e43-138">将 **TableView** 对象的 [Filter](https://msdn.microsoft.com/library/bb610296\(v=office.15\)) 属性设置为 DAV 搜索和定位 (DASL) 字符串，这样，只有当项目的邮件类中包含“IPM.Schedule”时，才会显示视图。</span><span class="sxs-lookup"><span data-stu-id="81e43-138">The [Filter](https://msdn.microsoft.com/library/bb610296\(v=office.15\)) property of the **TableView** object is set to a DAV Searching and Locating (DASL) string that causes the view to display only when there are items that contain "IPM.Schedule" in the message class for the item.</span></span> <span data-ttu-id="81e43-139">然后，系统会保存并应用新视图。</span><span class="sxs-lookup"><span data-stu-id="81e43-139">The new view is then saved and applied.</span></span>

<span data-ttu-id="81e43-140">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="81e43-140">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="81e43-141">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="81e43-141">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="81e43-142">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="81e43-142">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="81e43-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e43-143">See also</span></span>

- [<span data-ttu-id="81e43-144">视图</span><span class="sxs-lookup"><span data-stu-id="81e43-144">Views</span></span>](views.md)

