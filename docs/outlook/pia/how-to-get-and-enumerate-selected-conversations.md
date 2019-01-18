---
title: 获取并枚举选定对话
TOCTitle: Get and enumerate selected conversations
ms:assetid: 835312ea-2b29-49a5-b128-f69cf8d4427c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184621(v=office.15)
ms:contentKeyID: 55119833
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2d71fc1d582abebc8cb00f4885ec5b5ba348228c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699371"
---
# <a name="get-and-enumerate-selected-conversations"></a><span data-ttu-id="13a62-102">获取并枚举选定对话</span><span class="sxs-lookup"><span data-stu-id="13a62-102">Get and enumerate selected conversations</span></span>

<span data-ttu-id="13a62-103">此代码示例使用 [GetSelection(OlSelectionContents)](https://msdn.microsoft.com/library/ff185002\(v=office.15\)) 方法获取并枚举选定对话。</span><span class="sxs-lookup"><span data-stu-id="13a62-103">This example obtains and enumerates selected conversations by using the [GetSelection(OlSelectionContents)](https://msdn.microsoft.com/library/ff185002\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="13a62-104">示例</span><span class="sxs-lookup"><span data-stu-id="13a62-104">Example</span></span>

<span data-ttu-id="13a62-p101">可以将 Microsoft Outlook 设置为按会话显示收件箱中的项目。如果用户在收件箱中进行选择，您可以通过编程方式获取此选择内容，包括会话标题和会话项。此主题中的代码示例演示如何在收件箱中获取选择内容，以及如何枚举选择内容中每个会话中的邮件项。</span><span class="sxs-lookup"><span data-stu-id="13a62-p101">Microsoft Outlook can be set to display items in the Inbox by conversation. If a user makes a selection in the Inbox, you can obtain the selection programmatically, including conversation headers and conversation items. The code example in this topic shows how to obtain a selection in the Inbox and enumerate the mail items in each conversation in the selection.</span></span>

<span data-ttu-id="13a62-108">此代码示例包含方法 DemoConversationHeadersFromSelection。</span><span class="sxs-lookup"><span data-stu-id="13a62-108">The example contains one method, DemoConversationHeadersFromSelection.</span></span> <span data-ttu-id="13a62-109">该方法将当前视图设置为收件箱，然后检查当前视图是否为按日期排序来显示会话的表视图。</span><span class="sxs-lookup"><span data-stu-id="13a62-109">The method sets the current view to the Inbox, and then checks whether the current view is a table view that displays conversations sorted by date.</span></span> <span data-ttu-id="13a62-110">为了获取选定内容（包括任何选定 [ConversationHeader](https://msdn.microsoft.com/library/ff184727\(v=office.15\)) 对象），DemoConversationHeadersFromSelection 使用 [Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) 对象的 **GetSelection** 方法，同时将 [olConversationHeaders](https://msdn.microsoft.com/library/ff184867\(v=office.15\)) 常数指定为参数。</span><span class="sxs-lookup"><span data-stu-id="13a62-110">To obtain a selection, including any selected [ConversationHeader](https://msdn.microsoft.com/library/ff184727\(v=office.15\)) objects, DemoConversationHeadersFromSelection uses the **GetSelection** method of the [Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) object, specifying the [olConversationHeaders](https://msdn.microsoft.com/library/ff184867\(v=office.15\)) constant as an argument.</span></span> <span data-ttu-id="13a62-111">如果选定内容为对话标题，DemoConversationHeadersFromSelection 先使用 [SimpleItems](https://msdn.microsoft.com/library/ff184992\(v=office.15\)) 对象来枚举每个选定对话中的项，再显示属于 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象的对话项的主题。</span><span class="sxs-lookup"><span data-stu-id="13a62-111">If conversation headers are selected, DemoConversationHeadersFromSelection uses the [SimpleItems](https://msdn.microsoft.com/library/ff184992\(v=office.15\)) object to enumerate items in each selected conversation, and then displays the subject of those conversation items that are [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) objects.</span></span>

<span data-ttu-id="13a62-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="13a62-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="13a62-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="13a62-113">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="13a62-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="13a62-114">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="13a62-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13a62-115">See also</span></span>

- [<span data-ttu-id="13a62-116">对话</span><span class="sxs-lookup"><span data-stu-id="13a62-116">Conversations</span></span>](conversations.md)

