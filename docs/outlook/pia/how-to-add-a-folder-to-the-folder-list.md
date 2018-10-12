---
title: 将文件夹添加到文件夹列表
TOCTitle: Add a folder to the folder list
ms:assetid: f636a190-d966-4421-9977-0ead2bff5eee
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184655(v=office.15)
ms:contentKeyID: 55119850
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: dc8ead207261cfd4835e230981d923211771de7b
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405523"
---
# <a name="add-a-folder-to-the-folder-list"></a><span data-ttu-id="8186e-102">将文件夹添加到文件夹列表</span><span class="sxs-lookup"><span data-stu-id="8186e-102">Add a folder to the folder list</span></span>

<span data-ttu-id="8186e-103">此代码示例展示了如何通过使用 [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) 方法，将文件夹添加到 Outlook 文件夹列表。</span><span class="sxs-lookup"><span data-stu-id="8186e-103">This example shows how to use the [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) method to add a folder to the Outlook folder list.</span></span>

## <a name="example"></a><span data-ttu-id="8186e-104">示例</span><span class="sxs-lookup"><span data-stu-id="8186e-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="8186e-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="8186e-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>


<span data-ttu-id="8186e-106">在下面的代码示例中，**AddMyNewFolder** 调用 [Folders](https://msdn.microsoft.com/library/bb612071\(v=office.15\)) 集合的 **Add** 方法，将表示“我的新文件夹”文件夹的 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象添加到 Outlook 文件夹列表中的 **Inbox** 内。</span><span class="sxs-lookup"><span data-stu-id="8186e-106">In the following code example, **AddMyNewFolder** calls the **Add** method of the [T:Microsoft.Office.Interop.Outlook.Folders](https://msdn.microsoft.com/library/bb612071\(v=office.15\)) collection to add a [T:Microsoft.Office.Interop.Outlook.Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object that represents a folder called “My New Folder” to the **Inbox** in the Outlook folder list. “My New Folder” is then displayed.</span></span> <span data-ttu-id="8186e-107">此时，“我的新文件夹”随即显示。</span><span class="sxs-lookup"><span data-stu-id="8186e-107">“My New Folder” is then displayed.</span></span>

<span data-ttu-id="8186e-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="8186e-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="8186e-109">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="8186e-109">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="8186e-110">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="8186e-110">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AddMyNewFolder()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderInbox)
        as Outlook.Folder;
    Outlook.Folders folders = folder.Folders;
    try
    {
        Outlook.Folder newFolder = folders.Add(
            "My New Folder", Type.Missing)
            as Outlook.Folder;
        newFolder.Display();
    }
    catch
    {
        MessageBox.Show(
            "Could not add 'My New Folder'",
            "Add Folder",
            MessageBoxButtons.OK,
            MessageBoxIcon.Error);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="8186e-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8186e-111">See also</span></span>

- [<span data-ttu-id="8186e-112">文件夹</span><span class="sxs-lookup"><span data-stu-id="8186e-112">Folders</span></span>](folders.md)

