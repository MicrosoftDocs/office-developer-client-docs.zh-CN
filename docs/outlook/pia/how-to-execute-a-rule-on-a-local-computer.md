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
# <a name="execute-a-rule-on-a-local-computer"></a>在本地计算机上执行规则

此代码示例展示了如何使用 [RuleConditions](https://msdn.microsoft.com/library/bb610965\(v=office.15\)) 对象的 [OnLocalMachine](https://msdn.microsoft.com/library/bb612005\(v=office.15\)) 属性，在本地计算机上执行规则。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

如果您的邮箱承载于 Exchange 服务器上，则可以在 Exchange 服务器或 Outlook 客户端上执行某条规则。如果在服务器上执行规则，则不必运行 Outlook 即可计算规则条件并完成规则操作。如果在客户端上执行规则，则必须运行 Outlook 才能执行规则。如果 [Rule](https://msdn.microsoft.com/library/bb647386\(v=office.15\)) 对象的 [IsLocalRule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 属性返回 **true**，则在客户端上执行规则。

对于默认情况下在客户端上执行的规则操作（如显示新的邮件通知），将自动启用 **OnLocalMachine** 条件，并将仅客户端 [RuleAction](https://msdn.microsoft.com/library/bb611875\(v=office.15\)) 对象的 **Enabled** 属性设置为 [true](https://msdn.microsoft.com/library/bb644297\(v=office.15\))。 对于通常情况下在服务器上执行的规则操作，设置仅客户端 **RuleAction** 对象的 **Enabled** 属性以启用 **OnLocalMachine** 条件。 这样将强制在客户端上本地执行规则。 

如果为某条规则启用 **OnLocalMachine** 条件，则在从另一台计算机上检查同一条规则时，也将会启用 [OnOtherMachine](https://msdn.microsoft.com/library/bb624486\(v=office.15\)) 条件。 类型为 [olConditionOtherMachine](https://msdn.microsoft.com/library/bb645741\(v=office.15\)) 的规则条件指示只能在除当前计算机外的某台特定计算机上执行规则，并且无法以编程方式启用或禁用规则。 例如，如果某条规则是在当前计算机上创建的，并且启用了 **OnLocalMachine** 规则条件，则该规则只能在该计算机上执行。 如果其他计算机上也执行了相同的规则，那么规则会指明 **OnOtherMachine** 规则条件已启用。

在下面的代码示例中，DemoOnMachineOnly 创建规则，并通过将 **Enabled** 属性设置为 **true** 来启用 [OnlyToMe](https://msdn.microsoft.com/library/bb609250\(v=office.15\)) 条件和 [Forward](https://msdn.microsoft.com/library/bb652908\(v=office.15\)) 操作。 然后，它启用 **OnLocalMachine** 条件，同时强制服务器端规则在本地执行并保存规则。 默认情况下， **Forward** 操作和 **OnlyToMe** 条件将在服务器上运行。 已启用的 **OnLocalMachine** 条件作为客户端规则运行。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [规则](rules.md)

