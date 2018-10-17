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
# <a name="get-a-folder-based-on-its-folder-path"></a>根据文件夹路径获取文件夹

此示例先获取文件夹路径，再获取关联的文件夹。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

在下面的代码示例中，GetKeyContacts 方法使用 [GetRootFolder()](https://msdn.microsoft.com/library/bb645807\(v=office.15\)) 属性，以获取 Contacts\\Key Contacts 文件夹的文件夹路径。 然后，它将 [FolderPath](https://msdn.microsoft.com/library/bb647409\(v=office.15\)) 属性用作参数，以调用 GetFolder 方法。 如果 GetFolder 返回文件夹，系统便会显示消息，指明已找到“主要联系人”文件夹。 GetFolder 方法需要使用文件夹路径，并返回正确的 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象。 完成此操作首先需要将 **FolderPath** 属性拆分到 string 数组中，然后使用该数组从 **FolderPath** 属性的顶部开始查找正确的 **Folder** 对象。 如果找不到指定文件夹，GetFolder 返回空引用。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [文件夹](folders.md)

