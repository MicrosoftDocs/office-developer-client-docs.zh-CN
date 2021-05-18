---
title: 创建存档来自经理的邮件项并标记这些项以供跟进的规则
TOCTitle: Create a rule to file mail items from a manager and flag them for follow-up
ms:assetid: c50578c2-15de-4d5f-87d9-d6162034f083
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424477(v=office.15)
ms:contentKeyID: 55119880
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dba46c851050c3f948ec829ae2340e0492ca135f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360401"
---
# <a name="create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up"></a>创建存档来自经理的邮件项并标记这些项以供跟进的规则

此代码示例展示了如何创建以下规则：存档来自用户的经理的邮件项，并标记这些项以供跟进。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

Outlook 规则既可以作用于服务器端也可以作用于客户端，具体取决于帐户和规则的类型。在邮箱中组织项目时，可以通过多种方式来实现规则以强制实施您自己的组织方案。例如，可以创建按主题区域组织未读邮件和已读邮件的子文件夹层次结构。或者，也可以创建与邮件的发件人相对应的子文件夹层次结构。您还可以分类邮件，然后使用搜索文件夹来按照类别聚合邮件。

**Rules** 对象模型包含表示 Outlook 中规则的 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象，通过此对象模型可以编程方式创建规则以强制实施特定的组织方案，创建对于您的解决方案唯一的特定规则，或确保将特定规则部署到一组用户。 通过使用 **Rules** 对象模型，您可通过编程方式添加、编辑和删除规则。 通过使用 [Rules](https://msdn.microsoft.com/library/bb622788\(v=office.15\)) 集合和 **Rule** 对象，您也可以访问、添加和删除为会话定义的规则。 

**Rule** 对象具有一个指示规则是发送规则还是接收规则的 [RuleType](https://msdn.microsoft.com/library/bb645613\(v=office.15\)) 属性。 创建规则时会指定 **RuleType** 属性，如果没有删除规则并使用不同的 **RuleType** 属性重新创建规则，则无法更改该属性。 [RuleAction](https://msdn.microsoft.com/library/bb644297\(v=office.15\)) 和 [RuleCondition](https://msdn.microsoft.com/library/bb612469\(v=office.15\)) 对象、各自的集合对象以及派生的操作和条件对象也用于进一步支持编辑规则操作和规则条件。

虽然 **Rules** 对象模型并不支持您可以通过使用 Outlook 用户界面中的"规则和通知向导"创建的所有规则，但是支持最常用的规则操作和条件。使用"规则和通知向导"创建的应用于邮件（包括邮件项目、会议请求、任务请求、文档、送达回执、已读回执、投票响应和外出通知）的任何规则也可以编程方式进行创建。

规则既可以在 Exchange 服务器上执行，也可以在 Outlook 客户端上执行，前提是当前用户的邮箱托管于 Exchange 服务器上。 [Rule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) 对象的 **IsLocalRule** 属性返回 **true** 来指示在客户端上执行规则，必须运行 Outlook 才能执行规则。 如果在服务器上执行规则，则不必运行 Outlook 即可计算规则条件并完成规则操作。

> [!NOTE]
> [!注释] 不存在单独的集合表示规则例外条件。使用 [Rule](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._rule.exceptions?view=outlook-pia) 对象的 **Exceptions** 属性来获取表示规则例外条件的 [RuleConditions](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.ruleconditions?view=outlook-pia) 集合。

若要通过 Outlook 对象模型创建规则，请按照以下步骤操作：

1.  通过对默认的 **Store** 对象调用 [GetRules()](https://msdn.microsoft.com/library/bb623164\(v=office.15\)) 方法，从 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [DefaultStore](https://msdn.microsoft.com/library/bb609979\(v=office.15\)) 属性中获取 [Rules](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 集合。使用 **try…catch** 块来解释用户脱机或与 Exchange 服务器断开连接的情况。这样就可以防止 Outlook 引发错误。

2.  对 **Rules** 对象调用 [Create(String, OlRuleType)](https://msdn.microsoft.com/library/bb643857\(v=office.15\)) 方法，以创建实例变量或 **Rule** 对象，同时指定 Name 和 [OlRuleType](https://msdn.microsoft.com/library/bb645776\(v=office.15\)) 参数。

3.  使用 [RuleActions](https://msdn.microsoft.com/library/bb610113\(v=office.15\)) 和 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 集合启用 **Rule** 对象上的操作、条件和例外。请注意，在 **RuleConditions** 集合中启用的由 [Exceptions](https://msdn.microsoft.com/library/bb609880\(v=office.15\)) 属性返回的任何条件将被视为规则例外条件，无法将其他内置自定义操作或条件添加到该集合中。

4.  将 [Enabled](https://msdn.microsoft.com/library/bb609147\(v=office.15\)) 属性设置为 **true** 以便使任何给定的规则操作、条件或例外可执行。某些操作或条件（如 [Folder](https://msdn.microsoft.com/library/bb646755\(v=office.15\)) 属性）要求您在操作或条件上设置其他属性来保存 **Rule** 对象而不会出错。

5.  最后，对 [Rules](https://msdn.microsoft.com/library/bb610738\(v=office.15\)) 集合调用 **Save(Object)** 方法来保存创建或修改的规则。在 **try…catch** 块中放入 **Save** 方法来处理例外。

在下面的代码示例中，CreateManagerRule 实现上述步骤。 CreateManagerRule 先验证 [CurrentUser](https://msdn.microsoft.com/library/bb622574\(v=office.15\)) 属性是否表示 [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) 对象（表明当前用户是否是 Exchange 用户）。 如果当前用户是 Exchange 用户，CreateManagerRule 对 **NameSpace** 对象的 **CurrentUser** 属性的 **ExchangeUser** 对象调用 [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\)) 方法，以获取当前用户的经理。 然后，它创建接收规则，用于将收到的邮件移到收件箱的子文件夹，但前提条件如下：

- 邮件来自用户的经理。

- 收件人出现在邮件的“收件人:”行中。

- 邮件不是会议请求或更新。

最后，标记邮件便于当天跟踪。对于可能会引发异常的条件（如用户在缓存的 Exchange 模式下处于脱机状态或断开连接），CreateManagerRule 还会说明适当的错误处理。 

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [规则](rules.md)

