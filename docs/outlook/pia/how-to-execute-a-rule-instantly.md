---
title: 立即执行规则
TOCTitle: Execute a rule instantly
ms:assetid: b41031d5-aa81-40e2-ae78-b45a2f79eb5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424476(v=office.15)
ms:contentKeyID: 55119919
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a6bb6ac5422b9785660cb3ec0020c01244002c6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320368"
---
# <a name="execute-a-rule-instantly"></a>立即执行规则

此代码示例展示了如何使用 [Rule](https://msdn.microsoft.com/library/bb647152\(v=office.15\)) 对象的 [Execute(Object, Object, Object, Object)](https://msdn.microsoft.com/library/bb645769\(v=office.15\)) 方法立即执行规则。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

通过对 **Rule** 对象调用 **Execute** 方法可使规则得到立即执行。 **Execute** 方法的参数是可选的；如果没有指定参数，则规则将应用于收件箱中的所有邮件，但不包括收件箱的子文件夹，并且将使用参数的默认值。下表列出了 **Execute** 方法的可选参数的默认值。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>默认值</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowProgress</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>文件夹</p></td>
<td><p>收件箱</p></td>
</tr>
<tr class="odd">
<td><p>IncludeSubfolders</p></td>
<td><p>False</p></td>
</tr>
<tr class="even">
<td><p>RuleExecuteOption</p></td>
<td><p>OlRuleExecuteOption.olRuleExecuteAllMessages</p></td>
</tr>
</tbody>
</table>


可使用“规则和警报向导”来取消执行规则。 也可以通过下面的方法来取消执行规则：先将 *ShowProgress* 参数设置为 **true**，再取消进度对话框。 取消进度对话框后，**Execute** 便会返回错误。

在下面的代码示例中，ExecuteManagerRule 获取通过主题[创建规则：存档来自经理的邮件项，并标记这些项以供跟进](how-to-create-a-rule-to-file-mail-items-from-a-manager-and-flag-them-for-follow-up.md)中的 CreateManagerRule 过程创建的规则。 然后，ExecuteManagerRule 检查规则是否不是空引用。 如果规则不是空引用，ExecuteManagerRule 便会对规则调用采用默认参数（即立即执行规则）的 **Execute** 方法。

> [!NOTE]
> [!注释] 不管 [Enabled](https://msdn.microsoft.com/library/bb609147(v=office.15)) 属性是否返回 **true**，若要立即应用规则，请使用 **Rule.Execute** 方法。若要为当前会话和其他会话应用规则，请同时使用 **Rule.Enabled** 属性和 [Save(Object)](https://msdn.microsoft.com/library/bb610738(v=office.15)) 方法。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。 下面几行代码展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ExecuteManagerRule()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        try
        {
            string managerName = currentUser.
                GetExchangeUser().GetExchangeUserManager().Name;
            Outlook.Rule managerRule =
                Application.Session.DefaultStore.GetRules()[managerName];
            if (managerRule != null)
            {
                managerRule.Execute(false, Type.Missing,
                    Type.Missing, Type.Missing);
            }
        }
        catch (Exception ex)
        {
            Debug.WriteLine(ex.Message);
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [规则](rules.md)

