---
title: 向视图添加字段
TOCTitle: Add fields to a view
ms:assetid: ea371f27-ea65-47ef-ae44-ef843a78ab6f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424481(v=office.15)
ms:contentKeyID: 55119934
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4b850bf87be4024152ee808624ad93836b904897
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359694"
---
# <a name="add-fields-to-a-view"></a><span data-ttu-id="749ef-102">向视图添加字段</span><span class="sxs-lookup"><span data-stu-id="749ef-102">Add fields to a view</span></span>

<span data-ttu-id="749ef-103">此代码示例展示了如何自定义视图，具体方法是使用 [ViewFields](https://msdn.microsoft.com/library/bb645950\(v=office.15\)) 集合的 [Add(String)](https://msdn.microsoft.com/library/bb646040\(v=office.15\)) 方法将字段添加到视图中。</span><span class="sxs-lookup"><span data-stu-id="749ef-103">This example shows how to customize a view by using the [Add(String)](https://msdn.microsoft.com/library/bb646040\(v=office.15\)) method of the [ViewFields](https://msdn.microsoft.com/library/bb645950\(v=office.15\)) collection to add fields to a view.</span></span>

## <a name="example"></a><span data-ttu-id="749ef-104">示例</span><span class="sxs-lookup"><span data-stu-id="749ef-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="749ef-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="749ef-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="749ef-106">通过只在 **CardView** 和 [TableView](https://msdn.microsoft.com/library/bb609216\(v=office.15\)) 对象的 [ViewFields](https://msdn.microsoft.com/library/bb608854\(v=office.15\)) 集合中添加一个或多个属性，可以指定在视图中显示哪些 Outlook 项目属性。</span><span class="sxs-lookup"><span data-stu-id="749ef-106">You can specify which Outlook item properties are displayed in a view by adding one or more properties to the **ViewFields** collection for only the [CardView](https://msdn.microsoft.com/library/bb609216\(v=office.15\)) and [TableView](https://msdn.microsoft.com/library/bb608854\(v=office.15\)) objects.</span></span> <span data-ttu-id="749ef-107">对于其他派生的 **View** 对象（如 [BusinessCardView](https://msdn.microsoft.com/library/bb646315\(v=office.15\))、[CalendarView](https://msdn.microsoft.com/library/bb622874\(v=office.15\))、[IconView](https://msdn.microsoft.com/library/bb612031\(v=office.15\)) 和 [TimelineView](https://msdn.microsoft.com/library/bb609455\(v=office.15\)) 对象），使用其他方法来确定在视图中显示哪些 Outlook 项属性。</span><span class="sxs-lookup"><span data-stu-id="749ef-107">For other derived **View** objects such as [BusinessCardView](https://msdn.microsoft.com/library/bb646315\(v=office.15\)), [CalendarView](https://msdn.microsoft.com/library/bb622874\(v=office.15\)), [IconView](https://msdn.microsoft.com/library/bb612031\(v=office.15\)), and [TimelineView](https://msdn.microsoft.com/library/bb609455\(v=office.15\)) objects, use other methods of determining which Outlook item properties are displayed within the view.</span></span> <span data-ttu-id="749ef-108">例如，为 **BusinessCardView** 对象显示的字段取决于与每个显示的 Outlook 项关联的电子名片 (EBC) 布局。</span><span class="sxs-lookup"><span data-stu-id="749ef-108">For example, the fields displayed for the **BusinessCardView** object are determined by the electronic business card (EBC) layout associated with each displayed Outlook item.</span></span>

<span data-ttu-id="749ef-p102">若要获取视图的 **ViewFields** 集合，需使用关联的 **View** 对象（如 **CardView** 或 **TableView** 对象）的 **ViewFields** 属性。 **ViewFields** 集合的 **Add** 方法用于创建 [ViewField](https://msdn.microsoft.com/library/bb610583\(v=office.15\)) 对象，该对象表示要在视图中显示的 Outlook 项目属性。 **ViewField** 对象不仅标识要在视图中显示的 Outlook 项目属性，还描述应如何显示该属性的值。通过修改 [ViewField](https://msdn.microsoft.com/library/bb646462\(v=office.15\)) 对象的 **ColumnFormat** 属性，可以更改各个列属性在视图中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="749ef-p102">To get the **ViewFields** collection for a view, use the **ViewFields** property of the associated **View** object (for example, the **CardView** or **TableView** objects). The **Add** method of the **ViewFields** collection is used to create a [ViewField](https://msdn.microsoft.com/library/bb610583\(v=office.15\)) object that represents the Outlook item property to be displayed in the view. A **ViewField** object not only identifies an Outlook item property to display within the view, but it also describes how the values for that property should be displayed. You can change how individual column properties are displayed in a view by modifying the [ColumnFormat](https://msdn.microsoft.com/library/bb646462\(v=office.15\)) property of the **ViewField** object.</span></span>

<span data-ttu-id="749ef-p103">在下面的代码示例中，ModifyMeetingRequestsView 获取 **TableView** 对象，该对象表示用户收件箱中作为“会议请求”视图的所有视图。然后，该示例使用 **Add** 方法将“开始”和“结束”字段添加到与 **TableView** 对象对应的 **ViewFields** 对象中。该示例还将“发件人”字段的标签更改为“组织者”。ModifyMeetingRequestsView 然后保存修改后的 **TableView** 对象。</span><span class="sxs-lookup"><span data-stu-id="749ef-p103">In the following code example, ModifyMeetingRequestsView gets the **TableView** object that represents all the views from the user’s Inbox that are “Meeting Requests” views. The example then uses the **Add** method to add the “Start” and “End” fields to the **ViewFields** object that corresponds to the **TableView** object. It also changes the label for the “From” field to “Organized By”. ModifyMeetingRequestsView then saves the modified **TableView** object.</span></span>

<span data-ttu-id="749ef-117">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="749ef-117">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="749ef-118">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="749ef-118">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="749ef-119">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="749ef-119">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ModifyMeetingRequestsView()
{
    Outlook.TableView tableView = null;
    Outlook.ViewField startField = null;
    Outlook.ViewField endField = null;
    Outlook.ViewField fromField = null;
    try
    {
        tableView =
            Application.Session.GetDefaultFolder(
            Outlook.OlDefaultFolders.olFolderInbox)
            .Views["Meeting Requests"] as Outlook.TableView;
    }
    catch { }
    if (tableView != null)
    {
        try
        {
            startField = tableView.ViewFields["Start"];
        }
        catch{}
        if (startField == null)
        {
            startField = tableView.ViewFields.Add("Start");
        }
        try
        {
            endField = tableView.ViewFields["End"];
        }
        catch{}
        if (endField == null)
        {
            endField = tableView.ViewFields.Add("End");
        }
        try
        {
            fromField = tableView.ViewFields["From"];
        }
        catch{}
        if (fromField != null)
        {
            fromField.ColumnFormat.Label = "Organized By";
        }
        try
        {
            tableView.Save();
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="749ef-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="749ef-120">See also</span></span>

- [<span data-ttu-id="749ef-121">视图</span><span class="sxs-lookup"><span data-stu-id="749ef-121">Views</span></span>](views.md)

