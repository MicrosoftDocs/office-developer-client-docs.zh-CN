---
title: 选择文件夹并显示文件夹信息
TOCTitle: Select a folder and display folder information
ms:assetid: 737b19bc-1efd-4ddb-86d0-72b3ab8eaf8c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184616(v=office.15)
ms:contentKeyID: 55119859
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 17131ba769b5f8d1719011474dc2c06bf1084ca3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406475"
---
# <a name="select-a-folder-and-display-folder-information"></a><span data-ttu-id="9c7a6-102">选择文件夹并显示文件夹信息</span><span class="sxs-lookup"><span data-stu-id="9c7a6-102">Select a folder and display folder information</span></span>

<span data-ttu-id="9c7a6-103">此代码示例展示了如何以编程方式显示用户从指定文件夹列表中选择的文件夹的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-103">This example shows how to programmatically display information about a folder that a user selects from a specified folder list.</span></span>

## <a name="example"></a><span data-ttu-id="9c7a6-104">示例</span><span class="sxs-lookup"><span data-stu-id="9c7a6-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="9c7a6-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="9c7a6-106">在下面的代码示例中，ShowFolderInfo 使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [PickFolder()](https://msdn.microsoft.com/library/bb623484\(v=office.15\)) 方法，向用户显示“选择文件夹”\*\*\*\* 对话框，并等待用户选择文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-106">In the following code example, ShowFolderInfo uses the [PickFolder()](https://msdn.microsoft.com/library/bb623484\(v=office.15\)) method of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object to display a **Select Folder** dialog box to the user, and waits for the user to select a folder.</span></span> <span data-ttu-id="9c7a6-107">在用户选择文件夹后，此代码示例便会显示文件夹的 [EntryID](https://msdn.microsoft.com/library/bb646192\(v=office.15\))、[StoreID](https://msdn.microsoft.com/library/bb612609\(v=office.15\))、[UnReadItemCount](https://msdn.microsoft.com/library/bb610138\(v=office.15\))、[DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\))、[CurrentView](https://msdn.microsoft.com/library/bb612411\(v=office.15\))、[Name](https://msdn.microsoft.com/library/bb623727\(v=office.15\)) 和 [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-107">Once the user selects a folder, its [EntryID](https://msdn.microsoft.com/library/bb646192\(v=office.15\)), [StoreID](https://msdn.microsoft.com/library/bb612609\(v=office.15\)), [UnReadItemCount](https://msdn.microsoft.com/library/bb610138\(v=office.15\)), [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)), [CurrentView](https://msdn.microsoft.com/library/bb612411\(v=office.15\)), [Name](https://msdn.microsoft.com/library/bb623727\(v=office.15\)), and [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) properties are displayed.</span></span> <span data-ttu-id="9c7a6-108">然后，此代码示例调用 [GetFolderFromID](https://msdn.microsoft.com/library/bb647784\(v=office.15\)) 方法，以新建 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象并显示文件夹。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-108">The example then calls the [GetFolderFromID](https://msdn.microsoft.com/library/bb647784\(v=office.15\)) method to create a new [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object and display the folder.</span></span>

<span data-ttu-id="9c7a6-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="9c7a6-110">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-110">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="9c7a6-111">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="9c7a6-111">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ShowFolderInfo()
{
    Outlook.Folder folder =
        Application.Session.PickFolder()
        as Outlook.Folder;
    if (folder != null)
    {
        StringBuilder sb = new StringBuilder();
        sb.AppendLine("Folder EntryID:");
        sb.AppendLine(folder.EntryID);
        sb.AppendLine();
        sb.AppendLine("Folder StoreID:");
        sb.AppendLine(folder.StoreID);
        sb.AppendLine();
        sb.AppendLine("Unread Item Count: "
            + folder.UnReadItemCount);
        sb.AppendLine("Default MessageClass: "
            + folder.DefaultMessageClass);
        sb.AppendLine("Current View: "
            + folder.CurrentView.Name);
        sb.AppendLine("Folder Path: "
            + folder.FolderPath);
        MessageBox.Show(sb.ToString(),
            "Folder Information",
            MessageBoxButtons.OK,
            MessageBoxIcon.Information);
        Outlook.Folder folderFromID =
            Application.Session.GetFolderFromID(
            folder.EntryID, folder.StoreID)
            as Outlook.Folder;
        folderFromID.Display();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9c7a6-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c7a6-112">See also</span></span>

- [<span data-ttu-id="9c7a6-113">文件夹</span><span class="sxs-lookup"><span data-stu-id="9c7a6-113">Folders</span></span>](folders.md)

