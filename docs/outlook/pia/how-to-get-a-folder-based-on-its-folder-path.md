---
title: 根据文件夹路径获取文件夹
TOCTitle: Get a folder based on its folder path
ms:assetid: 613f2209-667c-48f0-82cf-86e3c9a24cb4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184612(v=office.15)
ms:contentKeyID: 55119858
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: b418cda3f689182cb7133af22e0f2fdc6ba834c2
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407140"
---
# <a name="get-a-folder-based-on-its-folder-path"></a><span data-ttu-id="b7f15-102">根据文件夹路径获取文件夹</span><span class="sxs-lookup"><span data-stu-id="b7f15-102">Get a folder based on its folder path</span></span>

<span data-ttu-id="b7f15-103">此示例先获取文件夹路径，再获取关联的文件夹。</span><span class="sxs-lookup"><span data-stu-id="b7f15-103">This example takes a folder path and obtains the associated folder.</span></span>

## <a name="example"></a><span data-ttu-id="b7f15-104">示例</span><span class="sxs-lookup"><span data-stu-id="b7f15-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b7f15-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="b7f15-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="b7f15-106">在下面的代码示例中，GetKeyContacts 方法使用 [GetRootFolder()](https://msdn.microsoft.com/library/bb645807\(v=office.15\)) 属性，以获取 Contacts\\Key Contacts 文件夹的文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="b7f15-106">In the following code example, the  [](https://msdn.microsoft.com/library/bb645807\(v=office.15\)) method uses the \\ property to obtain the folder path of the Contacts\Key Contacts folder.</span></span> <span data-ttu-id="b7f15-107">然后，它将 [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) 属性用作参数，以调用 GetFolder 方法。</span><span class="sxs-lookup"><span data-stu-id="b7f15-107">The   method is then called by using the FolderPath property as the argument.</span></span> <span data-ttu-id="b7f15-108">如果 GetFolder 返回文件夹，系统便会显示消息，指明已找到“主要联系人”文件夹。</span><span class="sxs-lookup"><span data-stu-id="b7f15-108">If   returns a folder, a message will appear saying the Key Contacts are found.</span></span> <span data-ttu-id="b7f15-109">GetFolder 方法需要使用文件夹路径，并返回正确的 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="b7f15-109">The   method takes in a path to a folder and returns the correct Folder object.</span></span> <span data-ttu-id="b7f15-110">完成此操作首先需要将 **FolderPath** 属性拆分到 string 数组中，然后使用该数组从 **FolderPath** 属性的顶部开始查找正确的 **Folder** 对象。</span><span class="sxs-lookup"><span data-stu-id="b7f15-110">This is done by first splitting the **FolderPath** property into a string array and then using the array to find the correct **Folder** object starting from the top of the **FolderPath** property.</span></span> <span data-ttu-id="b7f15-111">如果找不到指定文件夹，GetFolder 返回空引用。</span><span class="sxs-lookup"><span data-stu-id="b7f15-111">If the specified folder is not found,   returns a null reference.</span></span>

<span data-ttu-id="b7f15-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b7f15-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b7f15-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b7f15-113">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b7f15-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b7f15-114">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetKeyContacts()
{
    string folderPath =
        Application.Session.
        DefaultStore.GetRootFolder().FolderPath
        + @"\Contacts\Key Contacts";
    Outlook.Folder folder = GetFolder(folderPath);
    if (folder != null)
    {
        //Work with folder here
        Debug.WriteLine("Found Key Contacts");
    }
}

// Returns Folder object based on folder path
private Outlook.Folder GetFolder(string folderPath)
{
    Outlook.Folder folder;
    string backslash = @"\";
    try
    {
        if (folderPath.StartsWith(@"\\"))
        {
            folderPath = folderPath.Remove(0, 2);
        }
        String[] folders =
            folderPath.Split(backslash.ToCharArray());
        folder =
            Application.Session.Folders[folders[0]]
            as Outlook.Folder;
        if (folder != null)
        {
            for (int i = 1; i <= folders.GetUpperBound(0); i++)
            {
                Outlook.Folders subFolders = folder.Folders;
                folder = subFolders[folders[i]]
                    as Outlook.Folder;
                if (folder == null)
                {
                    return null;
                }
            }
        }
        return folder;
    }
    catch { return null; }
}        
```

## <a name="see-also"></a><span data-ttu-id="b7f15-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7f15-115">See also</span></span>

- [<span data-ttu-id="b7f15-116">文件夹</span><span class="sxs-lookup"><span data-stu-id="b7f15-116">Folders</span></span>](folders.md)

