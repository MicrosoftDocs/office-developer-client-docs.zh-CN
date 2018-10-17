---
title: 使用“选择姓名”对话框获取收件人并将其分配到约会
TOCTitle: Use the Select Names dialog box to obtain and assign recipients to an appointment
ms:assetid: b9bcb341-1912-425c-8d75-ed5be233145a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184636(v=office.15)
ms:contentKeyID: 55119878
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 57a7c99efa2bd82e1bc3d3f0855a90b62109719c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407000"
---
# <a name="use-the-select-names-dialog-box-to-obtain-and-assign-recipients-to-an-appointment"></a><span data-ttu-id="fbbcb-102">使用“选择姓名”对话框获取收件人并将其分配到约会</span><span class="sxs-lookup"><span data-stu-id="fbbcb-102">Uses the Select Names dialog box to obtain and assign recipients to an appointment item.</span></span>

<span data-ttu-id="fbbcb-103">此示例展示了如何使用“**选择姓名**”对话框获取收件人并将其分配到约会项。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-103">This example shows how to use the **Select Names** dialog box to obtain and assign recipients to an appointment item.</span></span>

## <a name="example"></a><span data-ttu-id="fbbcb-104">示例</span><span class="sxs-lookup"><span data-stu-id="fbbcb-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="fbbcb-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="fbbcb-106">若要显示“**选择姓名**”对话框，请调用 [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) 对象的 [Display()](https://msdn.microsoft.com/library/bb646086\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-106">To display the **Select Names** dialog box, call the [Display()](https://msdn.microsoft.com/library/bb646086\(v=office.15\)) method of the [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) object.</span></span> <span data-ttu-id="fbbcb-107">在向用户显示“**选择姓名**”对话框后，代码执行会中止，直至用户单击“**确定**”或关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-107">Once the **Select Names** dialog box is displayed to the user, code execution halts until the user clicks **OK** or closes the dialog box.</span></span> <span data-ttu-id="fbbcb-108">若要设置要在对话框中显示的初始收件人或获取对话框中已选中的收件人，请使用 **SelectNamesDialog** 对象的 [Recipients](https://msdn.microsoft.com/library/bb652601\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-108">To set initial recipients to display in the dialog box, or to get the recipients selected in the dialog box, use the [Recipients](https://msdn.microsoft.com/library/bb652601\(v=office.15\)) property of the **SelectNamesDialog** object.</span></span> <span data-ttu-id="fbbcb-109">此操作将返回与 **SelectNamesDialog** 相关联的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-109">This returns a [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) collection that is associated with the **SelectNamesDialog**.</span></span> <span data-ttu-id="fbbcb-110">若要向 **SelectNamesDialog** 的 **Recipients** 集合添加 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象，请使用集合的 [Add](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) 方法并指定 **Recipient** 对象的 [Type](https://msdn.microsoft.com/library/bb611841\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-110">To add a [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object to the **Recipients** collection for the **SelectNamesDialog**, use the [Add](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) method for the collection and specify the [Type](https://msdn.microsoft.com/library/bb611841\(v=office.15\)) property of the **Recipient** object.</span></span>

<span data-ttu-id="fbbcb-111">在下面的代码示例中，DemoSelectNamesDialogRecipients 会创建 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象并设置它的一些属性。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-111">In the following code example, DemoSelectNamesDialogRecipients creates an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object and sets some of its properties.</span></span> <span data-ttu-id="fbbcb-112">然后，它会创建 **SelectNamesDialog** 并使用 [SetDefaultDisplayMode(OlDefaultSelectNamesDisplayMode)](https://msdn.microsoft.com/library/bb623783\(v=office.15\)) 方法来设置“**选择姓名**”对话框的会议显示模式。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-112">It then creates a **SelectNamesDialog** and uses the [SetDefaultDisplayMode(OlDefaultSelectNamesDisplayMode)](https://msdn.microsoft.com/library/bb623783\(v=office.15\)) method to set a meeting display mode for the **Select Names** dialog box.</span></span> <span data-ttu-id="fbbcb-113">该示例会使用字符串“Conf Room 36/2739”来填充“**资源**”收件人选择器。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-113">The example populates the **Resource** recipient selector with the string "Conf Room 36/2739".</span></span> <span data-ttu-id="fbbcb-114">在向用户显示该对话框后，代码会枚举与此 **SelectNamesDialog** 实例关联的 **Recipients** 集合并将这些收件人添加到创建的约会。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-114">Once the dialog box is displayed to the user, the code enumerates the **Recipients** collection that is associated with this instance of **SelectNamesDialog** and adds those recipients to the appointment that was created.</span></span> <span data-ttu-id="fbbcb-115">最后，该示例会向用户显示会议请求。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-115">Finally, the example displays the meeting request to the user.</span></span>

<span data-ttu-id="fbbcb-116">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-116">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="fbbcb-117">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-117">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="fbbcb-118">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="fbbcb-118">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoSelectNamesDialogRecipients()
{
    Outlook.AppointmentItem appt = Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.MeetingStatus = Outlook.OlMeetingStatus.olMeeting;
    appt.Subject = "Team Morale Event";
    appt.Start = DateTime.Parse("5/17/2007 11:00 AM");
    appt.End = DateTime.Parse("5/17/2007 12:00 PM");
    Outlook.SelectNamesDialog snd =
        Application.Session.GetSelectNamesDialog();
    snd.SetDefaultDisplayMode(
        Outlook.OlDefaultSelectNamesDisplayMode.olDefaultMeeting);
    Outlook.Recipient confRoom =
        snd.Recipients.Add("Conf Room 36/2739");
    // Explicitly specify Recipient.Type.
    confRoom.Type = (int)Outlook.OlMeetingRecipientType.olResource;
    snd.Recipients.ResolveAll();
    snd.Display();
    // Add Recipients to meeting request.
    Outlook.Recipients recips = snd.Recipients;
    if (recips.Count > 0)
    {
        foreach (Outlook.Recipient recip in recips)
        {
            appt.Recipients.Add(recip.Name);
        }
    }
    appt.Recipients.ResolveAll();
    appt.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="fbbcb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbbcb-119">See also</span></span>

- [<span data-ttu-id="fbbcb-120">收件人</span><span class="sxs-lookup"><span data-stu-id="fbbcb-120">Recipients</span></span>](recipients.md)

