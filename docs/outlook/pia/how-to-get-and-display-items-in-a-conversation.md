---
title: 获取并显示对话中的项
TOCTitle: Get and display items in a conversation
ms:assetid: 8f30a7cb-0949-46d7-bc51-2d93dbb22bf8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184625(v=office.15)
ms:contentKeyID: 55119832
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: dd48437e0b2092d905cf870451b59aea9ef66c5d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407441"
---
# <a name="get-and-display-items-in-a-conversation"></a>获取并显示对话中的项

此代码示例展示了如何获取并显示对话中的邮件项。

## <a name="example"></a>示例

在下面的代码示例中，DemoConversation 先获取 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象，再使用 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象的 [Store](https://msdn.microsoft.com/library/bb609093\(v=office.15\)) 属性确定 **MailItem** 对象的存储。 然后，DemoConversation 检查 [IsConversationEnabled](https://msdn.microsoft.com/library/ff185030\(v=office.15\)) 属性是否为 **true**；如果为 **true**，此代码示例便使用 [GetConversation()](https://msdn.microsoft.com/library/ff184974\(v=office.15\)) 方法获取 [Conversation](https://msdn.microsoft.com/library/ff184711\(v=office.15\)) 对象。 如果 **Conversation** 对象不是 null 引用，则该示例将通过使用 [GetTable()](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 方法来获取包含对话中每个项目的关联的 [Table](https://msdn.microsoft.com/library/ff185184\(v=office.15\)) 对象。 

然后，此代码示例枚举 **Table** 中的所有项，并对每一项调用 EnumerateConversation，以访问每一项的子节点。 EnumerateConversation 获取 **Conversation** 对象，并使用 [GetChildren(Object)](https://msdn.microsoft.com/library/ff184854\(v=office.15\)) 方法获取子节点。 此代码示例以递归方式调用 EnumerateConversation，直到再无子节点可获取。 然后，此代码示例向用户显示所有对话项。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [对话](conversations.md)

