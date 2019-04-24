---
title: 添加作为邮件项响应的自定义操作
TOCTitle: Add a custom action as a response to a mail item
ms:assetid: 99e8ba6b-9c47-4b10-968b-436b08d199ec
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424474(v=office.15)
ms:contentKeyID: 55119870
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a6a82b02d357f86ca37d3ec4987ea6323d6d59cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359750"
---
# <a name="add-a-custom-action-as-a-response-to-a-mail-item"></a><span data-ttu-id="97bdd-102">添加作为邮件项响应的自定义操作</span><span class="sxs-lookup"><span data-stu-id="97bdd-102">Add a custom action as a response to a mail item</span></span>

<span data-ttu-id="97bdd-103">此代码示例展示了如何通过使用 [Actions](https://msdn.microsoft.com/library/bb612077\(v=office.15\)) 集合的 [Add()](https://msdn.microsoft.com/library/bb611963\(v=office.15\)) 方法，添加作为电子邮件项响应的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="97bdd-103">This example shows how to add custom actions as a response to an email item by using the [Add()](https://msdn.microsoft.com/library/bb612077\(v=office.15\)) method of the [Actions](https://msdn.microsoft.com/library/bb611963\(v=office.15\)) collection.</span></span>

## <a name="example"></a><span data-ttu-id="97bdd-104">示例</span><span class="sxs-lookup"><span data-stu-id="97bdd-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="97bdd-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="97bdd-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="97bdd-106">可以编程方式创建自定义操作，使其显示在电子邮件响应中“邮件”\*\*\*\* 选项卡上“操作”\*\*\*\* 组的功能区内。</span><span class="sxs-lookup"><span data-stu-id="97bdd-106">You can create custom actions programmatically to appear on the ribbon in the **Actions** group on the **Message** tab in an email response.</span></span> <span data-ttu-id="97bdd-107">在下面的代码示例中，ReplyWithVoiceMail 创建“使用语音邮件回复”自定义操作，并将它添加到检查器命令栏。</span><span class="sxs-lookup"><span data-stu-id="97bdd-107">In the following code example, ReplyWithVoiceMail creates and adds a custom action named “Reply with Voice Mail” to the inspector command bar.</span></span> <span data-ttu-id="97bdd-108">ReplyWithVoiceMail 先获取 [\_MailItem](https://msdn.microsoft.com/library/bb610623\(v=office.15\)) 对象，再调用与 **MailItem** 关联的 **Actions** 集合的 **Add** 方法，以创建 [Action](https://msdn.microsoft.com/library/bb646971\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="97bdd-108">ReplyWithVoiceMail first gets a [\_MailItem](https://msdn.microsoft.com/library/bb610623\(v=office.15\)) object and then creates an [Action](https://msdn.microsoft.com/library/bb646971\(v=office.15\)) object by calling the **Add** method of the **Actions** collection that is associated with the **MailItem**.</span></span> <span data-ttu-id="97bdd-109">然后，它将 **Action** 对象的 [Name](https://msdn.microsoft.com/library/bb624053\(v=office.15\)) 属性设置为“使用语音邮件回复”。</span><span class="sxs-lookup"><span data-stu-id="97bdd-109">It then sets the [Name](https://msdn.microsoft.com/library/bb624053\(v=office.15\)) property of the **Action** object to “Reply with Voice Mail”.</span></span> <span data-ttu-id="97bdd-110">同时设置的属性还有 [ReplyStyle](https://msdn.microsoft.com/library/bb624278\(v=office.15\))、[ResponseStyle](https://msdn.microsoft.com/library/bb622491\(v=office.15\))、[CopyLike](https://msdn.microsoft.com/library/bb624213\(v=office.15\)) 和 [MessageClass](https://msdn.microsoft.com/library/bb624391\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="97bdd-110">The [ReplyStyle](https://msdn.microsoft.com/library/bb624278\(v=office.15\)), [ResponseStyle](https://msdn.microsoft.com/library/bb622491\(v=office.15\)), [CopyLike](https://msdn.microsoft.com/library/bb624213\(v=office.15\)), and [MessageClass](https://msdn.microsoft.com/library/bb624391\(v=office.15\)) properties are also set.</span></span> <span data-ttu-id="97bdd-111">最后，保存 **MailItem**。</span><span class="sxs-lookup"><span data-stu-id="97bdd-111">Finally, the **MailItem**is saved.</span></span>


> [!NOTE]
> <span data-ttu-id="97bdd-112">也可以在设计时使用 Outlook 窗体设计器添加自定义操作。</span><span class="sxs-lookup"><span data-stu-id="97bdd-112">You can also add custom actions at design time by using the Outlook Forms Designer.</span></span>


<span data-ttu-id="97bdd-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="97bdd-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="97bdd-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="97bdd-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="97bdd-115">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="97bdd-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;

    private void ReplyWithVoiceMail()
    {
        Outlook.MailItem mail = (Outlook.MailItem)Application.ActiveInspector().CurrentItem;
        Outlook.Action action = mail.Actions.Add();
        action.Name = “Reply with Voice Mail”;
        action.ReplyStyle = Outlook.OlActionReplyStyle.olUserPreference;
        action.ResponseStyle = Outlook.OlActionResponseStyle.olOpen;
        action.CopyLike = Outlook.OlActionCopyLike.olReply;
        action.MessageClass = “IPM.Post.Voice Message”;
        mail.Save();
    }
```

## <a name="see-also"></a><span data-ttu-id="97bdd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97bdd-116">See also</span></span>

- [<span data-ttu-id="97bdd-117">邮件</span><span class="sxs-lookup"><span data-stu-id="97bdd-117">Mail</span></span>](mail.md)

