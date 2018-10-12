---
title: 添加作为邮件项响应的自定义操作
TOCTitle: Add a custom action as a response to a mail item
ms:assetid: 99e8ba6b-9c47-4b10-968b-436b08d199ec
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424474(v=office.15)
ms:contentKeyID: 55119870
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 1858372ec8283b1926e5ed82f2a511a97a8242ec
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406853"
---
# <a name="add-a-custom-action-as-a-response-to-a-mail-item"></a>添加作为邮件项响应的自定义操作

此代码示例展示了如何通过使用 [Actions](https://msdn.microsoft.com/library/bb612077\(v=office.15\)) 集合的 [Add()](https://msdn.microsoft.com/library/bb611963\(v=office.15\)) 方法，添加作为电子邮件项响应的自定义操作。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


可以编程方式创建自定义操作，使其显示在电子邮件响应中“邮件”**** 选项卡上“操作”**** 组的功能区内。 在下面的代码示例中，ReplyWithVoiceMail 创建“使用语音邮件回复”自定义操作，并将它添加到检查器命令栏。 ReplyWithVoiceMail 先获取 [\_MailItem](https://msdn.microsoft.com/library/bb610623\(v=office.15\)) 对象，再调用与 **MailItem** 关联的 **Actions** 集合的 **Add** 方法，以创建 [Action](https://msdn.microsoft.com/library/bb646971\(v=office.15\)) 对象。 然后，它将 **Action** 对象的 [Name](https://msdn.microsoft.com/library/bb624053\(v=office.15\)) 属性设置为“使用语音邮件回复”。 同时设置的属性还有 [ReplyStyle](https://msdn.microsoft.com/library/bb624278\(v=office.15\))、[ResponseStyle](https://msdn.microsoft.com/library/bb622491\(v=office.15\))、[CopyLike](https://msdn.microsoft.com/library/bb624213\(v=office.15\)) 和 [MessageClass](https://msdn.microsoft.com/library/bb624391\(v=office.15\))。 最后，保存 **MailItem**。


> [!NOTE]
> 也可以在设计时使用 Outlook 窗体设计器添加自定义操作。


如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [邮件](mail.md)

