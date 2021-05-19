---
title: 使用“选择姓名”对话框获取收件人并将其分配到约会
TOCTitle: Use the Select Names dialog box to obtain and assign recipients to an appointment
ms:assetid: b9bcb341-1912-425c-8d75-ed5be233145a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184636(v=office.15)
ms:contentKeyID: 55119878
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 408d2fbdc3c89b7f2bad1fe9c2c76c1f47ae05ff
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335376"
---
# <a name="use-the-select-names-dialog-box-to-obtain-and-assign-recipients-to-an-appointment"></a>使用“选择姓名”对话框获取收件人并将其分配到约会

此示例展示了如何使用“**选择姓名**”对话框获取收件人并将其分配到约会项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要显示“**选择姓名**”对话框，请调用 [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) 对象的 [Display()](https://msdn.microsoft.com/library/bb646086\(v=office.15\)) 方法。 在向用户显示“**选择姓名**”对话框后，代码执行会中止，直至用户单击“**确定**”或关闭对话框。 若要设置要在对话框中显示的初始收件人或获取对话框中已选中的收件人，请使用 **SelectNamesDialog** 对象的 [Recipients](https://msdn.microsoft.com/library/bb652601\(v=office.15\)) 属性。 此操作将返回与 **SelectNamesDialog** 相关联的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。 若要向 **SelectNamesDialog** 的 **Recipients** 集合添加 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象，请使用集合的 [Add](https://msdn.microsoft.com/library/bb612668\(v=office.15\)) 方法并指定 **Recipient** 对象的 [Type](https://msdn.microsoft.com/library/bb611841\(v=office.15\)) 属性。

在下面的代码示例中，DemoSelectNamesDialogRecipients 会创建 [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) 对象并设置它的一些属性。 然后，它会创建 **SelectNamesDialog** 并使用 [SetDefaultDisplayMode(OlDefaultSelectNamesDisplayMode)](https://msdn.microsoft.com/library/bb623783\(v=office.15\)) 方法来设置“**选择姓名**”对话框的会议显示模式。 该示例会使用字符串“Conf Room 36/2739”来填充“**资源**”收件人选择器。 在向用户显示该对话框后，代码会枚举与此 **SelectNamesDialog** 实例关联的 **Recipients** 集合并将这些收件人添加到创建的约会。 最后，该示例会向用户显示会议请求。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [收件人](recipients.md)

