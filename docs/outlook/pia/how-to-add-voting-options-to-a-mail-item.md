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
# <a name="add-voting-options-to-a-mail-item"></a>向邮件项添加投票选项

此代码示例展示了如何使用 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的 [VotingOptions](https://msdn.microsoft.com/library/bb652695\(v=office.15\)) 属性，向电子邮件添加投票选项。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


邮件上的投票选项用于向邮件收件人提供一个选项列表并跟踪收件人的响应。若要以编程方式创建投票选项，请设置一个以分号分隔的列表形式的字符串，其中包含 **MailItem** 对象的 **VotingOptions** 属性的值。**VotingOptions** 属性的值将显示在已接收邮件的功能区中“响应”组的“投票”命令下。 

在下面的代码示例中，OrderPizza 在新邮件中创建投票选项。 OrderPizza 先创建 **MailItem**，再将 **VotingOptions** 属性设置为“Cheese; Mushroom; Sausage; Combo; Veg Combo”，并将 [Subject](https://msdn.microsoft.com/library/bb611353\(v=office.15\)) 属性设置为“Pizza Order”。 在发送的“披萨订单”邮件中，收件人看到投票选项。 对于收到的每个答复，收件人的选择记录在发件人“已发送邮件”文件夹中邮件的“跟踪”页上。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

