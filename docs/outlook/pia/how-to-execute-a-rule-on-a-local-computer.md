---
title: 在本地计算机上执行规则
TOCTitle: Execute a rule on a local computer
ms:assetid: 65e91010-3e4c-4921-a0fb-ad90a7b841b2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424471(v=office.15)
ms:contentKeyID: 55119883
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 76587a72d9c77a5484d9aa9788173f9f40f57614
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405838"
---
# <a name="execute-a-rule-on-a-local-computer"></a><span data-ttu-id="311cd-102">在本地计算机上执行规则</span><span class="sxs-lookup"><span data-stu-id="311cd-102">Execute a rule on a local computer</span></span>

<span data-ttu-id="311cd-103">此代码示例展示了如何使用 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 对象的 [OnLocalMachine](https://msdn.microsoft.com/library/bb612005\(v=office.15\)) 属性，在本地计算机上执行规则。</span><span class="sxs-lookup"><span data-stu-id="311cd-103">This example shows how to execute a rule on a local computer by using the [OnLocalMachine](https://msdn.microsoft.com/library/bb612005\(v=office.15\)) property of the [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) object.</span></span>

## <a name="example"></a><span data-ttu-id="311cd-104">示例</span><span class="sxs-lookup"><span data-stu-id="311cd-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="311cd-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="311cd-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="311cd-p101">如果您的邮箱承载于 Exchange 服务器上，则可以在 Exchange 服务器或 Outlook 客户端上执行某条规则。如果在服务器上执行规则，则不必运行 Outlook 即可计算规则条件并完成规则操作。如果在客户端上执行规则，则必须运行 Outlook 才能执行规则。如果 [Rule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) 对象的 [IsLocalRule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 属性返回 **true**，则在客户端上执行规则。</span><span class="sxs-lookup"><span data-stu-id="311cd-p101">If your mailbox is hosted on an Exchange server, a rule can be executed on the Exchange server or on the Outlook client. If the rule is executed on the server, Outlook does not have to be running for the rule conditions to be evaluated and the rule actions to be completed. If the rule is executed on the client, Outlook must be running for the rule to execute. If the [IsLocalRule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) property of the [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) object returns **true**, the rule is executed on the client.</span></span>

<span data-ttu-id="311cd-110">对于默认情况下在客户端上执行的规则操作（如显示新的邮件通知），将自动启用 **OnLocalMachine** 条件，并将仅客户端 [RuleAction](https://msdn.microsoft.com/library/bb611875\(v=office.15\)) 对象的 **Enabled** 属性设置为 [true](https://msdn.microsoft.com/library/bb644297\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="311cd-110">For rule actions that execute on the client by default (such as displaying a new mail alert), the **OnLocalMachine** condition will automatically be enabled, and the [Enabled](https://msdn.microsoft.com/library/bb611875\(v=office.15\)) property is set to **true** for a client-side-only [RuleAction](https://msdn.microsoft.com/library/bb644297\(v=office.15\)) object.</span></span> <span data-ttu-id="311cd-111">对于通常情况下在服务器上执行的规则操作，设置仅客户端 **RuleAction** 对象的 **Enabled** 属性以启用 **OnLocalMachine** 条件。</span><span class="sxs-lookup"><span data-stu-id="311cd-111">For rule actions that generally execute on the server, set the **Enabled** property of the client-side-only **RuleAction** object to enable the **OnLocalMachine** condition.</span></span> <span data-ttu-id="311cd-112">这样将强制在客户端上本地执行规则。</span><span class="sxs-lookup"><span data-stu-id="311cd-112">This will force the rule to execute locally on the client.</span></span> 

<span data-ttu-id="311cd-113">如果为某条规则启用 **OnLocalMachine** 条件，则在从另一台计算机上检查同一条规则时，也将会启用 [OnOtherMachine](https://msdn.microsoft.com/library/bb624486\(v=office.15\)) 条件。</span><span class="sxs-lookup"><span data-stu-id="311cd-113">When the **OnLocalMachine** condition for a rule is enabled, the [OnOtherMachine](https://msdn.microsoft.com/library/bb624486\(v=office.15\)) condition will also be enabled when the same rule is examined from another machine.</span></span> <span data-ttu-id="311cd-114">类型为 [olConditionOtherMachine](https://msdn.microsoft.com/library/bb645741\(v=office.15\)) 的规则条件指示只能在除当前计算机外的某台特定计算机上执行规则，并且无法以编程方式启用或禁用规则。</span><span class="sxs-lookup"><span data-stu-id="311cd-114">A rule condition of type [olConditionOtherMachine](https://msdn.microsoft.com/library/bb645741\(v=office.15\)) indicates that the rule can execute only on a specific computer other than the current one, and cannot be programmatically enabled or disabled.</span></span> <span data-ttu-id="311cd-115">例如，如果某条规则是在当前计算机上创建的，并且启用了 **OnLocalMachine** 规则条件，则该规则只能在该计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="311cd-115">For example, if a rule is created on the current computer and the **OnLocalMachine** rule condition is enabled, the rule can execute only on that computer.</span></span> <span data-ttu-id="311cd-116">如果其他计算机上也执行了相同的规则，那么规则会指明 **OnOtherMachine** 规则条件已启用。</span><span class="sxs-lookup"><span data-stu-id="311cd-116">If the same rule is executed on another computer, the rule will show that the **OnOtherMachine** rule condition is enabled.</span></span>

<span data-ttu-id="311cd-117">在下面的代码示例中，DemoOnMachineOnly 创建规则，并通过将 **Enabled** 属性设置为 **true** 来启用 [OnlyToMe](https://msdn.microsoft.com/library/bb609250\(v=office.15\)) 条件和 [Forward](https://msdn.microsoft.com/library/bb652908\(v=office.15\)) 操作。</span><span class="sxs-lookup"><span data-stu-id="311cd-117">In the following code example,   creates a rule and enables the OnlyToMe condition and Forward action by setting the Enabled properties to true.</span></span> <span data-ttu-id="311cd-118">然后，它启用 **OnLocalMachine** 条件，同时强制服务器端规则在本地执行并保存规则。</span><span class="sxs-lookup"><span data-stu-id="311cd-118">The **OnLocalMachine** condition is then enabled, forcing a server-side rule to execute locally, and the rules are saved.</span></span> <span data-ttu-id="311cd-119">默认情况下， **Forward** 操作和 **OnlyToMe** 条件将在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="311cd-119">By default, a **Forward** action and **OnlyToMe** condition will operate on the server.</span></span> <span data-ttu-id="311cd-120">已启用的 **OnLocalMachine** 条件作为客户端规则运行。</span><span class="sxs-lookup"><span data-stu-id="311cd-120">Once the **OnLocalMachine** condition has been enabled, they will operate as a client-side rule.</span></span>

<span data-ttu-id="311cd-121">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="311cd-121">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="311cd-122">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="311cd-122">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="311cd-123">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="311cd-123">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoOnMachineOnly()
{
    Outlook.Rules rules =
        Application.Session.DefaultStore.GetRules();
    Outlook.Rule rule =
        rules.Create("Demo Machine Only Rule",
        Outlook.OlRuleType.olRuleReceive);
    rule.Conditions.OnlyToMe.Enabled = true;
    rule.Actions.Forward.Enabled = true;
    rule.Actions.Forward.Recipients.Add("someone@example.com");
    rule.Actions.Forward.Recipients.ResolveAll();

    // Force the rule to execute locally
    rule.Conditions.OnLocalMachine.Enabled = true;
    rules.Save(true);
}
```

## <a name="see-also"></a><span data-ttu-id="311cd-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="311cd-124">See also</span></span>

- [<span data-ttu-id="311cd-125">规则</span><span class="sxs-lookup"><span data-stu-id="311cd-125">Rules</span></span>](rules.md)

