---
title: 创建存档来自经理的邮件项并标记这些项以供跟进的规则
TOCTitle: Create a rule to file mail items from a manager and flag them for follow-up
ms:assetid: c50578c2-15de-4d5f-87d9-d6162034f083
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424477(v=office.15)
ms:contentKeyID: 55119880
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 2fc6f5fe60b2f643590e8f7545804cf6d8a4c11c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405985"
---
# <a name="create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up"></a><span data-ttu-id="23ca2-102">创建存档来自经理的邮件项并标记这些项以供跟进的规则</span><span class="sxs-lookup"><span data-stu-id="23ca2-102">Create a rule to file mail items from a manager and flag them for follow-up</span></span>

<span data-ttu-id="23ca2-103">此代码示例展示了如何创建以下规则：存档来自用户的经理的邮件项，并标记这些项以供跟进。</span><span class="sxs-lookup"><span data-stu-id="23ca2-103">This example shows how to set up a rule to file mail items from the user’s manager and flag them for follow up.</span></span>

## <a name="example"></a><span data-ttu-id="23ca2-104">示例</span><span class="sxs-lookup"><span data-stu-id="23ca2-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="23ca2-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="23ca2-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="23ca2-p101">Outlook 规则既可以作用于服务器端也可以作用于客户端，具体取决于帐户和规则的类型。在邮箱中组织项目时，可以通过多种方式来实现规则以强制实施您自己的组织方案。例如，可以创建按主题区域组织未读邮件和已读邮件的子文件夹层次结构。或者，也可以创建与邮件的发件人相对应的子文件夹层次结构。您还可以分类邮件，然后使用搜索文件夹来按照类别聚合邮件。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p101">Outlook rules can operate either server-side or client-side, depending on the type of account and rule. There are many ways you can implement rules to enforce your own organizational schemes when you organize items in your mailbox. For example, you can create a subfolder hierarchy that organizes unread mail and read mail by subject area. Or, you can create a subfolder hierarchy that corresponds to the sender of the message. You can also categorize your mail and then use search folders to aggregate the mail by category.</span></span>

<span data-ttu-id="23ca2-111">**Rules** 对象模型包含表示 Outlook 中规则的 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象，通过此对象模型可以编程方式创建规则以强制实施特定的组织方案，创建对于您的解决方案唯一的特定规则，或确保将特定规则部署到一组用户。</span><span class="sxs-lookup"><span data-stu-id="23ca2-111">The **Rules** object model, which includes a [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) object that represents a rule in Outlook, allows you to create rules programmatically to enforce a certain organizational scheme, create a specific rule that is unique to your solution, or ensure that certain rules are deployed to a group of users.</span></span> <span data-ttu-id="23ca2-112">通过使用 **Rules** 对象模型，您可通过编程方式添加、编辑和删除规则。</span><span class="sxs-lookup"><span data-stu-id="23ca2-112">By using the **Rules** object model, you can programmatically add, edit, and delete rules.</span></span> <span data-ttu-id="23ca2-113">通过使用 [Rules](https://msdn.microsoft.com/library/bb622788\(v=office.15\)) 集合和 **Rule** 对象，您也可以访问、添加和删除为会话定义的规则。</span><span class="sxs-lookup"><span data-stu-id="23ca2-113">By using the [Rules](https://msdn.microsoft.com/library/bb622788\(v=office.15\)) collection and the **Rule** object, you can also access, add, and delete rules defined for a session.</span></span> 

<span data-ttu-id="23ca2-114">**Rule** 对象具有一个指示规则是发送规则还是接收规则的 [RuleType](https://msdn.microsoft.com/library/bb645613\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="23ca2-114">A **Rule** object has a [RuleType](https://msdn.microsoft.com/library/bb645613\(v=office.15\)) property that indicates whether the rule is a send or receive rule.</span></span> <span data-ttu-id="23ca2-115">创建规则时会指定 **RuleType** 属性，如果没有删除规则并使用不同的 **RuleType** 属性重新创建规则，则无法更改该属性。</span><span class="sxs-lookup"><span data-stu-id="23ca2-115">When a rule is created, the **RuleType** property is specified, and cannot be changed without deleting and re-creating the rule with a different **RuleType** property.</span></span> <span data-ttu-id="23ca2-116">[RuleAction](https://msdn.microsoft.com/library/bb644297\(v=office.15\)) 和 [RuleCondition](https://msdn.microsoft.com/library/bb612469\(v=office.15\)) 对象、各自的集合对象以及派生的操作和条件对象也用于进一步支持编辑规则操作和规则条件。</span><span class="sxs-lookup"><span data-stu-id="23ca2-116">The [RuleAction](https://msdn.microsoft.com/library/bb644297\(v=office.15\)) and [RuleCondition](https://msdn.microsoft.com/library/bb612469\(v=office.15\)) objects, their collection objects, and derived action and condition objects are also used to further support editing rule actions and rule conditions.</span></span>

<span data-ttu-id="23ca2-p104">虽然 **Rules** 对象模型并不支持您可以通过使用 Outlook 用户界面中的"规则和通知向导"创建的所有规则，但是支持最常用的规则操作和条件。使用"规则和通知向导"创建的应用于邮件（包括邮件项目、会议请求、任务请求、文档、送达回执、已读回执、投票响应和外出通知）的任何规则也可以编程方式进行创建。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p104">The **Rules** object model does not support all rules that you can create by using the Rules and Alert Wizard in the Outlook user interface, but it supports the most commonly used rule actions and conditions. Any rules created by using the Rules and Alerts Wizard that are applied to messages, which include mail items, meeting requests, task requests, documents, delivery receipts, read receipts, voting responses, and out-of-office notices, can also be created programmatically.</span></span>

<span data-ttu-id="23ca2-119">规则既可以在 Exchange 服务器上执行，也可以在 Outlook 客户端上执行，前提是当前用户的邮箱托管于 Exchange 服务器上。</span><span class="sxs-lookup"><span data-stu-id="23ca2-119">A rule can execute on the Exchange server or on the Outlook client, provided that the current user's mailbox is hosted on an Exchange server.</span></span> <span data-ttu-id="23ca2-120">[Rule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) 对象的 **IsLocalRule** 属性返回 **true** 来指示在客户端上执行规则，必须运行 Outlook 才能执行规则。</span><span class="sxs-lookup"><span data-stu-id="23ca2-120">The [IsLocalRule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) property of the **Rule** object returns **true** to indicate that the rule executes on a client, and Outlook must be running for the rule to execute.</span></span> <span data-ttu-id="23ca2-121">如果在服务器上执行规则，则不必运行 Outlook 即可计算规则条件并完成规则操作。</span><span class="sxs-lookup"><span data-stu-id="23ca2-121">If the rule executes on the server, Outlook does not have to be running for the rule conditions to be evaluated and the rule actions to be completed.</span></span>

> [!NOTE]
> <span data-ttu-id="23ca2-p106">[!注释] 不存在单独的集合表示规则例外条件。使用 [Rule](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._rule.exceptions?view=outlook-pia) 对象的 **Exceptions** 属性来获取表示规则例外条件的 [RuleConditions](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.ruleconditions?view=outlook-pia) 集合。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p106">There is no separate collection that represents rule exception conditions. Use the [Exceptions](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._rule.exceptions?view=outlook-pia) property of the **Rule** object to get a [RuleConditions](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.ruleconditions?view=outlook-pia) collection that represents rule exception conditions.</span></span>

<span data-ttu-id="23ca2-124">若要通过 Outlook 对象模型创建规则，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="23ca2-124">To create rules through the Outlook object model, follow these steps:</span></span>

1.  <span data-ttu-id="23ca2-p107">通过对默认的 **Store** 对象调用 [GetRules()](https://msdn.microsoft.com/library/bb623164\(v=office.15\)) 方法，从 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [DefaultStore](https://msdn.microsoft.com/library/bb609979\(v=office.15\)) 属性中获取 [Rules](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 集合。使用 **try…catch** 块来解释用户脱机或与 Exchange 服务器断开连接的情况。这样就可以防止 Outlook 引发错误。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p107">Get the **Rules** collection from the [DefaultStore](https://msdn.microsoft.com/library/bb623164\(v=office.15\)) property of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object by calling the [GetRules()](https://msdn.microsoft.com/library/bb609979\(v=office.15\)) method on the default [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) object. Use a **try…catch** block to account for the user being offline or disconnected from the Exchange server. This prevents Outlook from raising an error.</span></span>

2.  <span data-ttu-id="23ca2-128">对 **Rules** 对象调用 [Create(String, OlRuleType)](https://msdn.microsoft.com/library/bb643857\(v=office.15\)) 方法，以创建实例变量或 **Rule** 对象，同时指定 Name 和 [OlRuleType](https://msdn.microsoft.com/library/bb645776\(v=office.15\)) 参数。</span><span class="sxs-lookup"><span data-stu-id="23ca2-128">Call the [Create(String, OlRuleType)](https://msdn.microsoft.com/library/bb643857\(v=office.15\)) method on the **Rules** object to create an instance variable or a **Rule** object, specifying a  Name and a [OlRuleType](https://msdn.microsoft.com/library/bb645776\(v=office.15\)) parameter.</span></span>

3.  <span data-ttu-id="23ca2-p108">使用 [RuleActions](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) 和 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 集合启用 **Rule** 对象上的操作、条件和例外。请注意，在 **RuleConditions** 集合中启用的由 [Exceptions](https://msdn.microsoft.com/library/bb609880\(v=office.15\)) 属性返回的任何条件将被视为规则例外条件，无法将其他内置自定义操作或条件添加到该集合中。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p108">Use the [RuleActions](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) and [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) collections to enable actions, conditions, and exceptions on the **Rule** object. Note that any condition enabled in the **RuleConditions** collection, returned by the [Exceptions](https://msdn.microsoft.com/library/bb609880\(v=office.15\)) property, is treated as a rule exception condition, and additional built-in custom actions or conditions cannot be added to the collection.</span></span>

4.  <span data-ttu-id="23ca2-p109">将 [Enabled](https://msdn.microsoft.com/library/bb609147\(v=office.15\)) 属性设置为 **true** 以便使任何给定的规则操作、条件或例外可执行。某些操作或条件（如 [Folder](https://msdn.microsoft.com/library/bb646755\(v=office.15\)) 属性）要求您在操作或条件上设置其他属性来保存 **Rule** 对象而不会出错。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p109">Set the [Enabled](https://msdn.microsoft.com/library/bb609147\(v=office.15\)) property to **true** for any given rule action, condition, or exception to be operational. Some actions or conditions, such as the [Folder](https://msdn.microsoft.com/library/bb646755\(v=office.15\)) property, require that you set additional properties on the action or condition to save the **Rule** object without an error.</span></span>

5.  <span data-ttu-id="23ca2-p110">最后，对 [Rules](https://msdn.microsoft.com/library/bb610738\(v=office.15\)) 集合调用 **Save(Object)** 方法来保存创建或修改的规则。在 **try…catch** 块中放入 **Save** 方法来处理例外。</span><span class="sxs-lookup"><span data-stu-id="23ca2-p110">Finally, call the [Save(Object)](https://msdn.microsoft.com/library/bb610738\(v=office.15\)) method on the **Rules** collection to save the created or modified rules. Enclose the **Save** method in a **try…catch** block to handle exceptions.</span></span>

<span data-ttu-id="23ca2-135">在下面的代码示例中，CreateManagerRule 实现上述步骤。</span><span class="sxs-lookup"><span data-stu-id="23ca2-135">In the following code example,   implements the steps previously described.</span></span> <span data-ttu-id="23ca2-136">CreateManagerRule 先验证 [CurrentUser](https://msdn.microsoft.com/library/bb622574\(v=office.15\)) 属性是否表示 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象（表明当前用户是否是 Exchange 用户）。</span><span class="sxs-lookup"><span data-stu-id="23ca2-136"> first verifies whether the CurrentUser property represents an ExchangeUser object, indicating that the current user is an Exchange user.</span></span> <span data-ttu-id="23ca2-137">如果当前用户是 Exchange 用户，CreateManagerRule 对 **NameSpace** 对象的 **CurrentUser** 属性的 **ExchangeUser** 对象调用 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，以获取当前用户的经理。</span><span class="sxs-lookup"><span data-stu-id="23ca2-137">If the current user is an Exchange user,   gets the current user's manager by calling the GetExchangeUserManager() method on the ExchangeUser object of the CurrentUser property of the NameSpace object.</span></span> <span data-ttu-id="23ca2-138">然后，它创建接收规则，用于将收到的邮件移到收件箱的子文件夹，但前提条件如下：</span><span class="sxs-lookup"><span data-stu-id="23ca2-138">A receive rule is then created to move received messages to a subfolder of the Inbox for the following conditions:</span></span>

- <span data-ttu-id="23ca2-139">邮件来自用户的经理。</span><span class="sxs-lookup"><span data-stu-id="23ca2-139">The message is from the user’s manager.</span></span>

- <span data-ttu-id="23ca2-140">收件人出现在邮件的“收件人:”\*\*\*\* 行中。</span><span class="sxs-lookup"><span data-stu-id="23ca2-140">The recipient is on the **To:** line of the message.</span></span>

- <span data-ttu-id="23ca2-141">邮件不是会议请求或更新。</span><span class="sxs-lookup"><span data-stu-id="23ca2-141">The message is not a meeting request or update.</span></span>

<span data-ttu-id="23ca2-p112">最后，标记邮件便于当天跟踪。对于可能会引发异常的条件（如用户在缓存的 Exchange 模式下处于脱机状态或断开连接），CreateManagerRule 还会说明适当的错误处理。 </span><span class="sxs-lookup"><span data-stu-id="23ca2-p112">Finally, the message is flagged for follow-up today. CreateManagerRule also illustrates appropriate error handling for conditions that could raise an exception such as the user being offline or disconnected in cached Exchange mode.</span></span>

<span data-ttu-id="23ca2-144">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="23ca2-144">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="23ca2-145">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="23ca2-145">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="23ca2-146">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="23ca2-146">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateManagerRule()
{
    Outlook.ExchangeUser manager;
    Outlook.Folder managerFolder;
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        try
        {
            manager = currentUser.
                GetExchangeUser().GetExchangeUserManager();
        }
        catch
        {
            Debug.WriteLine("Could not obtain user's manager.");
            return;
        }
        Outlook.Rules rules;
        try
        {
            rules = Application.Session.DefaultStore.GetRules();
        }
        catch
        {
            Debug.WriteLine("Could not obtain rules collection.");
            return;
        }
        if (manager != null)
        {
            string displayName = manager.Name;
            Outlook.Folders folders =
                Application.Session.GetDefaultFolder(
                Outlook.OlDefaultFolders.olFolderInbox).Folders;
            try
            {
                managerFolder =
                    folders[displayName] as Outlook.Folder;
            }
            catch
            {
                managerFolder =
                    folders.Add(displayName, Type.Missing)
                    as Outlook.Folder;
            }
            Outlook.Rule rule = rules.Create(displayName,
                Outlook.OlRuleType.olRuleReceive);

            // Rule conditions
            // From condition
            rule.Conditions.From.Recipients.Add(
                manager.PrimarySmtpAddress);
            rule.Conditions.From.Recipients.ResolveAll();
            rule.Conditions.From.Enabled = true;

            // Sent only to me
            rule.Conditions.ToMe.Enabled = true;

            // Rule exceptions
            // Meeting invite or update
            rule.Exceptions.MeetingInviteOrUpdate.Enabled = true;

            // Rule actions
            // MarkAsTask action
            rule.Actions.MarkAsTask.MarkInterval =
                Outlook.OlMarkInterval.olMarkToday;
            rule.Actions.MarkAsTask.FlagTo = "Follow-up";
            rule.Actions.MarkAsTask.Enabled = true;

            // MoveToFolder action
            rule.Actions.MoveToFolder.Folder = managerFolder;
            rule.Actions.MoveToFolder.Enabled = true;
            try
            {
                rules.Save(true);
            }
            catch (Exception ex)
            {
                Debug.WriteLine(ex.Message);
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="23ca2-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23ca2-147">See also</span></span>

- [<span data-ttu-id="23ca2-148">规则</span><span class="sxs-lookup"><span data-stu-id="23ca2-148">Rules</span></span>](rules.md)

