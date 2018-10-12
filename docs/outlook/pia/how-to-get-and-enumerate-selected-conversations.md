---
title: 获取并枚举选定对话
TOCTitle: Get and enumerate selected conversations
ms:assetid: 835312ea-2b29-49a5-b128-f69cf8d4427c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184621(v=office.15)
ms:contentKeyID: 55119833
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: cf36003f183c9ddfe40cb2c27a9feab2962324d6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405593"
---
# <a name="get-and-enumerate-selected-conversations"></a>获取并枚举选定对话

此代码示例使用 [GetSelection(OlSelectionContents)](https://msdn.microsoft.com/library/ff185002\(v=office.15\)) 方法获取并枚举选定对话。

## <a name="example"></a>示例

可以将 Microsoft Outlook 设置为按会话显示收件箱中的项目。如果用户在收件箱中进行选择，您可以通过编程方式获取此选择内容，包括会话标题和会话项。此主题中的代码示例演示如何在收件箱中获取选择内容，以及如何枚举选择内容中每个会话中的邮件项。

此代码示例包含方法 DemoConversationHeadersFromSelection。 该方法将当前视图设置为收件箱，然后检查当前视图是否为按日期排序来显示会话的表视图。 为了获取选定内容（包括任何选定 [ConversationHeader](https://msdn.microsoft.com/library/ff184727\(v=office.15\)) 对象），DemoConversationHeadersFromSelection 使用 [Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) 对象的 **GetSelection** 方法，同时将 [olConversationHeaders](https://msdn.microsoft.com/library/ff184867\(v=office.15\)) 常数指定为参数。 如果选定内容为对话标题，DemoConversationHeadersFromSelection 先使用 [SimpleItems](https://msdn.microsoft.com/library/ff184992\(v=office.15\)) 对象来枚举每个选定对话中的项，再显示属于 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的对话项的主题。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoConversationHeadersFromSelection()
{
    // Obtain Inbox.
    Outlook.Folder inbox =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    // Set ActiveExplorer.CurrentFolder to Inbox.
    // Inbox must be current folder.
    Application.ActiveExplorer().CurrentFolder = inbox;
    // Ensure that current view is TableView.
    if (inbox.CurrentView.ViewType ==
        Outlook.OlViewType.olTableView)
    {
        Outlook.TableView view =
            inbox.CurrentView as Outlook.TableView;
        if (view.ShowConversationByDate == true)
        {
            Outlook.Selection selection =
                Application.ActiveExplorer().Selection;
            Debug.WriteLine("Selection.Count = " + selection.Count);
            // Call GetSelection to create a Selection object
            // that contains ConversationHeader objects.
            Outlook.Selection convHeaders =
                selection.GetSelection(
                Outlook.OlSelectionContents.olConversationHeaders)
                as Outlook.Selection;
            Debug.WriteLine("Selection.Count (ConversationHeaders) = " 
                + convHeaders.Count);
            if (convHeaders.Count >= 1)
            {
                foreach (Outlook.ConversationHeader convHeader in convHeaders)
                {
                    // Enumerate the items in the ConversationHeader.
                    Outlook.SimpleItems items = convHeader.GetItems();
                    for (int i = 1; i <= items.Count; i++)
                    {
                        // Enumerate only MailItems in this example.
                        if (items[i] is Outlook.MailItem)
                        {
                            Outlook.MailItem mail = 
                                items[i] as Outlook.MailItem;
                            Debug.WriteLine(mail.Subject 
                                + " Received:" + mail.ReceivedTime);
                        }
                    }
                }
            }
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [对话](conversations.md)

