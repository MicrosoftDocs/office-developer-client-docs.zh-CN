---
title: 显示收件人的共享日历
TOCTitle: Display a shared calendar of a recipient
ms:assetid: 3dcfec17-c836-4bd0-a177-33c911a94b1f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184606(v=office.15)
ms:contentKeyID: 55119825
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a9230a63af66e8143a7da488ce41dadafe359429
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356425"
---
# <a name="display-a-shared-calendar-of-a-recipient"></a><span data-ttu-id="f27d4-102">显示收件人的共享日历</span><span class="sxs-lookup"><span data-stu-id="f27d4-102">Display a shared calendar of a recipient</span></span>

<span data-ttu-id="f27d4-103">此代码示例展示了如何使用 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 和 [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) 方法显示收件人的共享日历。</span><span class="sxs-lookup"><span data-stu-id="f27d4-103">This example shows how to display a recipient's shared calendar by using the [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) and [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) methods.</span></span>

## <a name="example"></a><span data-ttu-id="f27d4-104">示例</span><span class="sxs-lookup"><span data-stu-id="f27d4-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="f27d4-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="f27d4-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="f27d4-p101">可发送项目（如 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象）始终公开 [Recipients](https://msdn.microsoft.com/library/bb646686\(v=office.15\)) 属性，该属性反过来允许您访问可发送项目的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。若要创建不绑定到项目的 [Recipients](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 集合的 **Recipient** 对象，请使用 [NameSpace](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 对象的 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法。然后，将此未绑定的 **Recipient** 对象传递给 [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) 方法，该方法会返回共享的 Exchange 文件夹。然后，您可以打开这一共享的 Exchange 文件夹，并在资源管理器窗口中显示该文件夹。 GetSharedDefaultFolder 用在委托有权访问代理人的文件夹的 Exchange 委托方案中。在将 **Recipient** 对象传递给 GetSharedDefaultFolder 方法之前，必须先解析该对象。若要解析 **Recipient** 对象，请调用其 [Resolve()](https://msdn.microsoft.com/library/bb624165\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="f27d4-p101">Sendable items such as [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) objects always expose the [Recipients](https://msdn.microsoft.com/library/bb646686\(v=office.15\)) property which, in turn, enables you to access the [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) collection for the sendable item. To create a [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object that is not bound to the **Recipients** collection of an item, use the [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) method of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object. Then pass this unbound **Recipient** object to the [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) method, which returns a shared Exchange folder. You can then open the shared Exchange folder and display that folder in an explorer window. GetSharedDefaultFolder is used in Exchange delegate scenarios where the delegate has permission to access the folder of the delegator. Before you pass the **Recipient** object to the GetSharedDefaultFolder method, you must resolve it. To resolve a **Recipient** object, call its [Resolve()](https://msdn.microsoft.com/library/bb624165\(v=office.15\)) method.</span></span>

<span data-ttu-id="f27d4-p102">在下面的代码示例中，DisplayManagerCalendar 通过调用 **CreateRecipient** 和 **GetSharedDefaultFolder** 来打开和显示当前用户的经理的“日历”文件夹。如果用户无权打开经理的“日历”文件夹或出现错误，将显示警报对话框。 </span><span class="sxs-lookup"><span data-stu-id="f27d4-p102">In the following code example, DisplayManagerCalendar opens and displays the Calendar folder of the current user’s manager by calling **CreateRecipient** and **GetSharedDefaultFolder**. An alert dialog box is displayed if the user does not have permission to open the manager’s Calendar folder or an error occurs.</span></span>


> [!NOTE]
> <span data-ttu-id="f27d4-115">[!注释] 在使用 **Namespace** 对象的 **CreateRecipient** 方法或 **Recipients** 集合的 [Add(String)](https://msdn.microsoft.com/library/bb612668(v=office.15)) 方法创建 **Recipient** 对象时，必须提供收件人名称。</span><span class="sxs-lookup"><span data-stu-id="f27d4-115">When you create a **Recipient** object by using the **CreateRecipient** method of the **Namespace** object or the [Add(String)](https://msdn.microsoft.com/library/bb612668(v=office.15)) method of the **Recipients** collection, you must provide a recipient name.</span></span> <span data-ttu-id="f27d4-116">然后，此代码示例根据这个名称解析 **Recipient**。</span><span class="sxs-lookup"><span data-stu-id="f27d4-116">The **Recipient** is then resolved against this name.</span></span> <span data-ttu-id="f27d4-117">收件人姓名可采用下列任一格式：</span><span class="sxs-lookup"><span data-stu-id="f27d4-117">A recipient name can take any of the following formats:</span></span>
> - <span data-ttu-id="f27d4-118">显示名称</span><span class="sxs-lookup"><span data-stu-id="f27d4-118">Display name</span></span>
> - <span data-ttu-id="f27d4-119">Alias</span><span class="sxs-lookup"><span data-stu-id="f27d4-119">Alias</span></span>
> - <span data-ttu-id="f27d4-120">简单邮件传输协议 (SMTP) 地址</span><span class="sxs-lookup"><span data-stu-id="f27d4-120">Simple Mail Transfer Protocol (SMTP) address</span></span>

<span data-ttu-id="f27d4-121">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="f27d4-121">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="f27d4-122">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="f27d4-122">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="f27d4-123">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="f27d4-123">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void DisplayManagerCalendar()
{
    Outlook.AddressEntry addrEntry =
        Application.Session.CurrentUser.AddressEntry;
    if (addrEntry.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            Application.Session.CurrentUser.
            AddressEntry.GetExchangeUser().GetExchangeUserManager();
        if (manager != null)
        {
            Outlook.Recipient recip =
                Application.Session.CreateRecipient(manager.Name);
            if (recip.Resolve())
            {
                try
                {
                    Outlook.Folder folder =
                        Application.Session.GetSharedDefaultFolder(
                        recip, Outlook.OlDefaultFolders.olFolderCalendar)
                        as Outlook.Folder;
                    folder.Display();
                }
                catch
                {
                    MessageBox.Show("Could not open manager's calendar.",
                        "GetSharedDefaultFolder Example",
                        MessageBoxButtons.OK,
                        MessageBoxIcon.Error);
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f27d4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f27d4-124">See also</span></span>

- [<span data-ttu-id="f27d4-125">日历</span><span class="sxs-lookup"><span data-stu-id="f27d4-125">Calendar</span></span>](calendar.md)

