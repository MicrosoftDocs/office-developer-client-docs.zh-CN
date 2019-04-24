---
title: 向邮件项添加投票选项
TOCTitle: Add voting options to a mail item
ms:assetid: 0fb209a8-178d-411e-9551-0a72e041fd65
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424466(v=office.15)
ms:contentKeyID: 55119867
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3befe70363d1e2226b8a3a3a6ebb8db39aa2c6ef
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359722"
---
# <a name="add-voting-options-to-a-mail-item"></a><span data-ttu-id="48418-102">向邮件项添加投票选项</span><span class="sxs-lookup"><span data-stu-id="48418-102">Add voting options to a mail item</span></span>

<span data-ttu-id="48418-103">此代码示例展示了如何使用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的 [VotingOptions](https://msdn.microsoft.com/library/bb652695\(v=office.15\)) 属性，向电子邮件添加投票选项。</span><span class="sxs-lookup"><span data-stu-id="48418-103">This example shows how to use the [VotingOptions](https://msdn.microsoft.com/library/bb652695\(v=office.15\)) property of the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object to add voting options to an email message.</span></span>

## <a name="example"></a><span data-ttu-id="48418-104">示例</span><span class="sxs-lookup"><span data-stu-id="48418-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="48418-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="48418-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="48418-p101">邮件上的投票选项用于向邮件收件人提供一个选项列表并跟踪收件人的响应。若要以编程方式创建投票选项，请设置一个以分号分隔的列表形式的字符串，其中包含 **MailItem** 对象的 **VotingOptions** 属性的值。**VotingOptions** 属性的值将显示在已接收邮件的功能区中“响应”\*\*\*\* 组的“投票”\*\*\*\* 命令下。 </span><span class="sxs-lookup"><span data-stu-id="48418-p101">Voting options on messages are used to give message recipients a list of choices and to track their responses. To create voting options programmatically, set a string that is a semicolon-delimited list of values for the **VotingOptions** property of a **MailItem** object. The values for the **VotingOptions** property will appear under the **Vote** command in the **Respond** group in the ribbon of the received message.</span></span>

<span data-ttu-id="48418-109">在下面的代码示例中，OrderPizza 在新邮件中创建投票选项。</span><span class="sxs-lookup"><span data-stu-id="48418-109">In the following example, OrderPizza creates voting options in a new mail message.</span></span> <span data-ttu-id="48418-110">OrderPizza 先创建 **MailItem**，再将 **VotingOptions** 属性设置为“Cheese; Mushroom; Sausage; Combo; Veg Combo”，并将 [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) 属性设置为“Pizza Order”。</span><span class="sxs-lookup"><span data-stu-id="48418-110">OrderPizza first creates a **MailItem**, and then sets the **VotingOptions** property to “Cheese; Mushroom; Sausage; Combo; Veg Combo”, and the [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) property to “Pizza Order”.</span></span> <span data-ttu-id="48418-111">在发送的“披萨订单”邮件中，收件人看到投票选项。</span><span class="sxs-lookup"><span data-stu-id="48418-111">When the “Pizza Order” message is sent, the voting options appear to recipients.</span></span> <span data-ttu-id="48418-112">对于收到的每个答复，收件人的选择记录在发件人“已发送邮件”文件夹中邮件的“跟踪”\*\*\*\* 页上。</span><span class="sxs-lookup"><span data-stu-id="48418-112">For each response received, the recipient’s choice will be tallied on the **Tracking** page of the message in the sender’s Sent Items folder.</span></span>

<span data-ttu-id="48418-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="48418-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="48418-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="48418-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="48418-115">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="48418-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;

    private void OrderPizza()
    {
        Outlook.MailItem mail = (Outlook.MailItem)Application.CreateItem(
            Outlook.OlItemType.olMailItem);
        mail.VotingOptions = “Cheese; Mushroom; Sausage; Combo; Veg Combo;”
        mail.Subject = “Pizza Order”;
        mail.Display(false);
    }
```

## <a name="see-also"></a><span data-ttu-id="48418-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48418-116">See also</span></span>

- [<span data-ttu-id="48418-117">邮件</span><span class="sxs-lookup"><span data-stu-id="48418-117">Mail</span></span>](mail.md)

