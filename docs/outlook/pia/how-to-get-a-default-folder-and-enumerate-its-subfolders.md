---
title: 获取默认文件夹并枚举它的子文件夹
TOCTitle: Get a default folder and enumerate its subfolders
ms:assetid: 587e8392-cb03-442c-9058-1282f36dabdb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184610(v=office.15)
ms:contentKeyID: 55119857
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 934b5f823127fde9fbbd3a49f41cedb791277e7e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407399"
---
# <a name="get-a-default-folder-and-enumerate-its-subfolders"></a><span data-ttu-id="e750a-102">获取默认文件夹并枚举它的子文件夹</span><span class="sxs-lookup"><span data-stu-id="e750a-102">Get a default folder and enumerate its subfolders</span></span>

<span data-ttu-id="e750a-103">此代码示例展示了如何获取用户默认存储中的默认文件夹，并枚举它的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="e750a-103">This example shows how to obtain a default folder in the user’s default store and enumerate its subfolders.</span></span>

## <a name="example"></a><span data-ttu-id="e750a-104">示例</span><span class="sxs-lookup"><span data-stu-id="e750a-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="e750a-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="e750a-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="e750a-106">在下面的代码示例中，GetRSSFeeds 使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [GetDefaultFolder(OlDefaultFolders)](https://msdn.microsoft.com/library/bb646473\(v=office.15\)) 方法，获取用户的 RSS 源根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e750a-106">In the following code example,   uses the GetDefaultFolder(OlDefaultFolders) method of the NameSpace object to obtain the user's RSS Feeds root folder.</span></span> <span data-ttu-id="e750a-107">然后，GetRSSFeeds 显示消息框，其中包含 RSS 源文件夹中所有 RSS 源的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="e750a-107"> then displays a message box that contains the folder names for all RSS feeds in the RSS Feeds folder.</span></span>

<span data-ttu-id="e750a-108">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="e750a-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="e750a-109">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="e750a-109">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="e750a-110">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="e750a-110">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetRSSFeeds()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderRssFeeds)
        as Outlook.Folder;
    if (folder != null)
    {
        if (folder.Folders.Count > 0)
        {
            StringBuilder sb = new StringBuilder();
            foreach (Outlook.Folder subfolder
                in folder.Folders)
            {
                sb.AppendLine(subfolder.Name);
            }
            MessageBox.Show(sb.ToString(),
                "RSS Feeds",
                MessageBoxButtons.OK,
                MessageBoxIcon.Information);
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e750a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e750a-111">See also</span></span>

- [<span data-ttu-id="e750a-112"></span><span class="sxs-lookup"><span data-stu-id="e750a-112">Folders</span></span>](folders.md)

