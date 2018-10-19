---
title: 使用 Hotmail 帐户发送邮件项
TOCTitle: Send a mail item by using a Hotmail account
ms:assetid: f25853a7-67c0-46a3-a298-5cdf72ebc53f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184652(v=office.15)
ms:contentKeyID: 55119797
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f95d5202f17c21e1c4be4545687f2eee96a00da3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407301"
---
# <a name="send-a-mail-item-by-using-a-hotmail-account"></a><span data-ttu-id="3979e-102">使用 Hotmail 帐户发送邮件项</span><span class="sxs-lookup"><span data-stu-id="3979e-102">Send a mail item by using a Hotmail account</span></span>

<span data-ttu-id="3979e-103">此代码示例使用 [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) 属性，通过 Windows Live Hotmail 帐户发送邮件项。</span><span class="sxs-lookup"><span data-stu-id="3979e-103">This example uses the [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) property to send a mail item by using a Windows Live Hotmail account.</span></span>

## <a name="example"></a><span data-ttu-id="3979e-104">示例</span><span class="sxs-lookup"><span data-stu-id="3979e-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3979e-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="3979e-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="3979e-106">配置文件定义一个或多个电子邮件帐户，每个电子邮件帐户都与特定类型的服务器（如 Microsoft Exchange Server 或邮局协议 3 (POP3)）关联。</span><span class="sxs-lookup"><span data-stu-id="3979e-106">A profile defines one or more e-mail accounts, and each e-mail account is associated with a server of a specific type, such as Microsoft Exchange Server or Post Office Protocol 3 (POP3).</span></span> <span data-ttu-id="3979e-107">由于配置文件中可能有多个帐户，因此必须先指定要用来发送项的电子邮件帐户，再获取表示帐户的 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="3979e-107">Because you may have multiple accounts in your profile, you must specify which e-mail account you want to use to send the item, and then obtain an [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object to represent it.</span></span>

<span data-ttu-id="3979e-108">在下面的代码示例中，创建的邮件中附加了行程，然后通过 Windows Live Hotmail 帐户进行发送。</span><span class="sxs-lookup"><span data-stu-id="3979e-108">In the following code example, a message is created with an attached itinerary and then sent by using a Windows Live Hotmail account.</span></span> <span data-ttu-id="3979e-109">Hotmail 电子邮件帐户用作用户配置文件中的 **Account** 对象。</span><span class="sxs-lookup"><span data-stu-id="3979e-109">The Hotmail e-mail account is used as the **Account** object in the user's profile.</span></span> <span data-ttu-id="3979e-110">然后，此代码示例将 SendUsingAccount 属性设置为这个 Account 对象，并调用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象中的 [Send()](https://msdn.microsoft.com/library/bb644139\(v=office.15\)) 方法。</span><span class="sxs-lookup"><span data-stu-id="3979e-110">The code example then sets the SendUsingAccount property to that Account and calls the [Send()](https://msdn.microsoft.com/library/bb644139\(v=office.15\)) method from the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object.</span></span>

<span data-ttu-id="3979e-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="3979e-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="3979e-112">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="3979e-112">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="3979e-113">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="3979e-113">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SendUsingAccountExample()
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.Subject = "Our itinerary";
    mail.Attachments.Add(@"c:\travel\itinerary.doc",
        Outlook.OlAttachmentType.olByValue,
        Type.Missing, Type.Missing);
    Outlook.Account account =
        Application.Session.Accounts["Hotmail"];
    mail.SendUsingAccount = account;
    mail.Send();
}
```

## <a name="see-also"></a><span data-ttu-id="3979e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3979e-114">See also</span></span>

- [<span data-ttu-id="3979e-115">帐户</span><span class="sxs-lookup"><span data-stu-id="3979e-115">Accounts</span></span>](accounts.md)

