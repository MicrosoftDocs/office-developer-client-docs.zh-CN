---
title: 获取并显示对话中的项
TOCTitle: Get and display items in a conversation
ms:assetid: 8f30a7cb-0949-46d7-bc51-2d93dbb22bf8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184625(v=office.15)
ms:contentKeyID: 55119832
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0fcfe76632c2fda742a85a571d655569dc2fcd33
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349460"
---
# <a name="get-and-display-items-in-a-conversation"></a><span data-ttu-id="d75bd-102">获取并显示对话中的项</span><span class="sxs-lookup"><span data-stu-id="d75bd-102">Get and display items in a conversation</span></span>

<span data-ttu-id="d75bd-103">此代码示例展示了如何获取并显示对话中的邮件项。</span><span class="sxs-lookup"><span data-stu-id="d75bd-103">This example shows how to get and display mail items in a conversation.</span></span>

## <a name="example"></a><span data-ttu-id="d75bd-104">示例</span><span class="sxs-lookup"><span data-stu-id="d75bd-104">Example</span></span>

<span data-ttu-id="d75bd-105">在下面的代码示例中，DemoConversation 先获取 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象，再使用 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象的 [Store](https://msdn.microsoft.com/library/bb609093\(v=office.15\)) 属性确定 **MailItem** 对象的存储。</span><span class="sxs-lookup"><span data-stu-id="d75bd-105">In the following code example, DemoConversation gets a [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object and then determines the store of the **MailItem** object by using the [Store](https://msdn.microsoft.com/library/bb609093\(v=office.15\)) property of the [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object.</span></span> <span data-ttu-id="d75bd-106">然后，DemoConversation 检查 [IsConversationEnabled](https://msdn.microsoft.com/library/ff185030\(v=office.15\)) 属性是否为 **true**；如果为 **true**，此代码示例便使用 [GetConversation()](https://msdn.microsoft.com/library/ff184974\(v=office.15\)) 方法获取 [Conversation](https://msdn.microsoft.com/library/ff184711\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d75bd-106">DemoConversation then checks whether the [IsConversationEnabled](https://msdn.microsoft.com/library/ff185030\(v=office.15\)) property is **true**; if it is **true**, the code example gets [Conversation](https://msdn.microsoft.com/library/ff184711\(v=office.15\)) object by using the [GetConversation()](https://msdn.microsoft.com/library/ff184974\(v=office.15\)) method.</span></span> <span data-ttu-id="d75bd-107">如果 **Conversation** 对象不是 null 引用，则该示例将通过使用 [GetTable()](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 方法来获取包含对话中每个项目的关联的 [Table](https://msdn.microsoft.com/library/ff185184\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d75bd-107">If the **Conversation** object is not a null reference, the example gets the associated [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object that contains each item in the conversation by using the [GetTable()](https://msdn.microsoft.com/library/ff185184\(v=office.15\)) method.</span></span> 

<span data-ttu-id="d75bd-108">然后，此代码示例枚举 **Table** 中的所有项，并对每一项调用 EnumerateConversation，以访问每一项的子节点。</span><span class="sxs-lookup"><span data-stu-id="d75bd-108">The example then enumerates each item in the **Table** and calls EnumerateConversation on each item to access the child nodes of each item.</span></span> <span data-ttu-id="d75bd-109">EnumerateConversation 获取 **Conversation** 对象，并使用 [GetChildren(Object)](https://msdn.microsoft.com/library/ff184854\(v=office.15\)) 方法获取子节点。</span><span class="sxs-lookup"><span data-stu-id="d75bd-109">EnumerateConversation takes a **Conversation** object and gets the child nodes by using the [GetChildren(Object)](https://msdn.microsoft.com/library/ff184854\(v=office.15\)) method.</span></span> <span data-ttu-id="d75bd-110">此代码示例以递归方式调用 EnumerateConversation，直到再无子节点可获取。</span><span class="sxs-lookup"><span data-stu-id="d75bd-110">EnumerateConversation is called recursively until there are no more child nodes.</span></span> <span data-ttu-id="d75bd-111">然后，此代码示例向用户显示所有对话项。</span><span class="sxs-lookup"><span data-stu-id="d75bd-111">Each conversation item is then displayed to the user.</span></span>

<span data-ttu-id="d75bd-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d75bd-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d75bd-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d75bd-113">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d75bd-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d75bd-114">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
void DemoConversation()
{
    object selectedItem = 
        Application.ActiveExplorer().Selection[1];
    // For this example, you will work only with 
    //MailItem. Other item types such as
    //MeetingItem and PostItem can participate 
    //in Conversation.
    if (selectedItem is Outlook.MailItem)
    {
        // Cast selectedItem to MailItem.
        Outlook.MailItem mailItem =
            selectedItem as Outlook.MailItem; ;
        // Determine store of mailItem.
        Outlook.Folder folder = mailItem.Parent
            as Outlook.Folder;
        Outlook.Store store = folder.Store;
        if (store.IsConversationEnabled == true)
        {
            // Obtain a Conversation object.
            Outlook.Conversation conv =
                mailItem.GetConversation();
            // Check for null Conversation.
            if (conv != null)
            {
                // Obtain Table that contains rows 
                // for each item in Conversation.
                Outlook.Table table = conv.GetTable();
                Debug.WriteLine("Conversation Items Count: " +
                    table.GetRowCount().ToString());
                Debug.WriteLine("Conversation Items from Table:");
                while (!table.EndOfTable)
                {
                    Outlook.Row nextRow = table.GetNextRow();
                    Debug.WriteLine(nextRow["Subject"]
                        + " Modified: "
                        + nextRow["LastModificationTime"]);
                }
                Debug.WriteLine("Conversation Items from Root:");
                // Obtain root items and enumerate Conversation.
                Outlook.SimpleItems simpleItems 
                    = conv.GetRootItems();
                foreach (object item in simpleItems)
                {
                    // In this example, enumerate only MailItem type.
                    // Other types such as PostItem or MeetingItem
                    // can appear in Conversation.
                    if (item is Outlook.MailItem)
                    {
                        Outlook.MailItem mail = item
                            as Outlook.MailItem;
                        Outlook.Folder inFolder =
                            mail.Parent as Outlook.Folder;
                        string msg = mail.Subject
                            + " in folder " + inFolder.Name;
                        Debug.WriteLine(msg);
                    }
                    // Call EnumerateConversation 
                    // to access child nodes of root items.
                    EnumerateConversation(item, conv);
                }
            }
        }
    }
}

void EnumerateConversation(object item,
    Outlook.Conversation conversation)
{
    Outlook.SimpleItems items =
        conversation.GetChildren(item);
    if (items.Count > 0)
    {
        foreach (object myItem in items)
        {
            // In this example, enumerate only MailItem type.
            // Other types such as PostItem or MeetingItem
            // can appear in Conversation.
            if (myItem is Outlook.MailItem)
            {
                Outlook.MailItem mailItem =
                    myItem as Outlook.MailItem;
                Outlook.Folder inFolder =
                    mailItem.Parent as Outlook.Folder;
                string msg = mailItem.Subject
                    + " in folder " + inFolder.Name;
                Debug.WriteLine(msg);
            }
            // Continue recursion.
            EnumerateConversation(myItem, conversation);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d75bd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d75bd-115">See also</span></span>

- [<span data-ttu-id="d75bd-116">对话</span><span class="sxs-lookup"><span data-stu-id="d75bd-116">Conversations</span></span>](conversations.md)

