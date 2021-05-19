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
# <a name="display-a-shared-calendar-of-a-recipient"></a>显示收件人的共享日历

此代码示例展示了如何使用 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 和 [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) 方法显示收件人的共享日历。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

可发送项目（如 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象）始终公开 [Recipients](https://msdn.microsoft.com/library/bb646686\(v=office.15\)) 属性，该属性反过来允许您访问可发送项目的 [Recipients](https://msdn.microsoft.com/library/bb646361\(v=office.15\)) 集合。若要创建不绑定到项目的 [Recipients](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 集合的 **Recipient** 对象，请使用 [NameSpace](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 对象的 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法。然后，将此未绑定的 **Recipient** 对象传递给 [GetSharedDefaultFolder(Recipient, OlDefaultFolders)](https://msdn.microsoft.com/library/bb644850\(v=office.15\)) 方法，该方法会返回共享的 Exchange 文件夹。然后，您可以打开这一共享的 Exchange 文件夹，并在资源管理器窗口中显示该文件夹。 GetSharedDefaultFolder 用在委托有权访问代理人的文件夹的 Exchange 委托方案中。在将 **Recipient** 对象传递给 GetSharedDefaultFolder 方法之前，必须先解析该对象。若要解析 **Recipient** 对象，请调用其 [Resolve()](https://msdn.microsoft.com/library/bb624165\(v=office.15\)) 方法。

在下面的代码示例中，DisplayManagerCalendar 通过调用 **CreateRecipient** 和 **GetSharedDefaultFolder** 来打开和显示当前用户的经理的“日历”文件夹。如果用户无权打开经理的“日历”文件夹或出现错误，将显示警报对话框。 


> [!NOTE]
> [!注释] 在使用 **Namespace** 对象的 **CreateRecipient** 方法或 **Recipients** 集合的 [Add(String)](https://msdn.microsoft.com/library/bb612668(v=office.15)) 方法创建 **Recipient** 对象时，必须提供收件人名称。 然后，此代码示例根据这个名称解析 **Recipient**。 收件人姓名可采用下列任一格式：
> - 显示名称
> - Alias
> - 简单邮件传输协议 (SMTP) 地址

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [日历](calendar.md)

