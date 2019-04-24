---
title: 枚举文件夹
TOCTitle: Enumerate folders
ms:assetid: 564730f9-3da3-4eff-b207-64ac4fec632d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184607(v=office.15)
ms:contentKeyID: 55119855
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0fe79f78ba1aab1e54df0b0bc88fa0c55c73e187
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357398"
---
# <a name="enumerate-folders"></a><span data-ttu-id="395a8-102">枚举文件夹</span><span class="sxs-lookup"><span data-stu-id="395a8-102">Enumerate folders</span></span>

<span data-ttu-id="395a8-103">此代码示例展示了如何通过循环访问文件夹集合来枚举文件夹。</span><span class="sxs-lookup"><span data-stu-id="395a8-103">This example shows how to enumerate folders by iterating through a collection of folders.</span></span>

## <a name="example"></a><span data-ttu-id="395a8-104">示例</span><span class="sxs-lookup"><span data-stu-id="395a8-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="395a8-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="395a8-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="395a8-106">在下面的代码示例中，EnumerateFoldersInDefaultStore 先使用 [GetRootFolder()](https://msdn.microsoft.com/library/bb645807\(v=office.15\)) 方法来获取默认存储的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="395a8-106">In the following code example, the EnumerateFoldersInDefaultStore method first obtains the root folder for the default store by using the [GetRootFolder()](https://msdn.microsoft.com/library/bb645807\(v=office.15\)) method.</span></span> <span data-ttu-id="395a8-107">然后，它对根文件夹调用 EnumerateFolders 方法。</span><span class="sxs-lookup"><span data-stu-id="395a8-107">It then calls the EnumerateFolders method on the root folder.</span></span> <span data-ttu-id="395a8-108">EnumerateFolders 需要使用根文件夹，并浏览根文件夹所表示的默认存储的文件夹。</span><span class="sxs-lookup"><span data-stu-id="395a8-108">EnumerateFolders takes in a root folder and walks through the folders of the default store that the root folder represents.</span></span> <span data-ttu-id="395a8-109">EnumerateFolders 先使用 [Folders](https://msdn.microsoft.com/library/bb646854\(v=office.15\)) 属性来获取根 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="395a8-109">EnumerateFolders first uses the [Folders](https://msdn.microsoft.com/library/bb646854\(v=office.15\)) property to obtain the subfolders of the root [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object.</span></span> <span data-ttu-id="395a8-110">然后，此代码示例递归调用 EnumerateFolders，以枚举层次结构中的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="395a8-110">EnumerateFolders is then called recursively to enumerate all the folders in a hierarchy.</span></span> <span data-ttu-id="395a8-111">最后，EnumerateFolders 将每个 **Folder** 的 [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) 属性写入 [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) 集合的跟踪侦听器中。</span><span class="sxs-lookup"><span data-stu-id="395a8-111">Finally, EnumerateFolders writes the [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) property of each **Folder** to the trace listeners in the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="395a8-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="395a8-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="395a8-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="395a8-113">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="395a8-114">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="395a8-114">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void EnumerateFoldersInDefaultStore()
{
    Outlook.Folder root =
        Application.Session.
        DefaultStore.GetRootFolder() as Outlook.Folder;
    EnumerateFolders(root);
}

// Uses recursion to enumerate Outlook subfolders.
private void EnumerateFolders(Outlook.Folder folder)
{
    Outlook.Folders childFolders =
        folder.Folders;
    if (childFolders.Count > 0)
    {
        foreach (Outlook.Folder childFolder in childFolders)
        {
            // Write the folder path.
            Debug.WriteLine(childFolder.FolderPath);
            // Call EnumerateFolders using childFolder.
            EnumerateFolders(childFolder);
        }
    }
}               
```

## <a name="see-also"></a><span data-ttu-id="395a8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="395a8-115">See also</span></span>

- [<span data-ttu-id="395a8-116">文件夹</span><span class="sxs-lookup"><span data-stu-id="395a8-116">Folders</span></span>](folders.md)

