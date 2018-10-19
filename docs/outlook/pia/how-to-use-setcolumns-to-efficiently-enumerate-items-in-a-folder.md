---
title: 使用 SetColumns 高效枚举文件夹中的项
TOCTitle: Use SetColumns to efficiently enumerate items in a folder
ms:assetid: cd7c7758-8a9c-4f1c-a49c-9305d75be341
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184641(v=office.15)
ms:contentKeyID: 55119921
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 2e75a0cb06420f5072805cdf03ad8f7925670e67
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407469"
---
# <a name="use-setcolumns-to-efficiently-enumerate-items-in-a-folder"></a>使用 SetColumns 高效枚举文件夹中的项

本示例演示如何提高使用 [SetColumns(String)](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 方法枚举 [Items](https://msdn.microsoft.com/library/bb610268\(v=office.15\)) 集合以缓存集合中每个项目的特定属性时的性能。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要枚举集合中的项目，需使用 **SetColumns** 方法来缓存 **Items** 集合上的属性。 **SetColumns** 采用一个表示属性名称的逗号分隔的字符串参数。在枚举了集合中的所有项目之后，调用 [ResetColumns()](https://msdn.microsoft.com/library/bb624355\(v=office.15\)) 方法以清除属性缓存。

在下面的代码示例中，EnumerateContactsWithSetColumns 使用 **SetColumns** 方法，以缓存“联系人”文件夹中项的 [FileAs](https://msdn.microsoft.com/library/bb647792\(v=office.15\))、[CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)) 和 [JobTitle](https://msdn.microsoft.com/library/bb609294\(v=office.15\)) 属性。 请注意，必须要测试限制中是否有空字符串或空引用。

请注意，Outlook 文件夹可能会包含不同类型的项。 此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)一文中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.Class 属性，以验证文件夹中的筛选后项子集中每一项的邮件类别，再假设项为联系人项。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void EnumerateContactsWithSetColumns()
{
    // Obtain Contacts folder
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts)
        as Outlook.Folder;
    string filter = "Not([CompanyName] Is Null)" +
        " AND Not([JobTitle] Is Null)";
    Outlook.Items items = folder.Items.Restrict(filter);
    items.SetColumns("FileAs, CompanyName, JobTitle");
    for (int i = 1; i <= items.Count; i++)
    {
        // Create an instance of OutlookItem
        OutlookItem myItem = new OutlookItem(items[i]);
        if (myItem.Class == Outlook.OlObjectClass.olContact)
        {
            // Use InnerObject to return ContactItem
            Outlook.ContactItem contact =
                myItem.InnerObject as Outlook.ContactItem;
            StringBuilder sb = new StringBuilder();
            sb.AppendLine(contact.FileAs);
            sb.AppendLine(contact.CompanyName);
            sb.AppendLine(contact.JobTitle);
            sb.AppendLine();
            Debug.WriteLine(sb.ToString());
        }
    }
    items.ResetColumns();
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

