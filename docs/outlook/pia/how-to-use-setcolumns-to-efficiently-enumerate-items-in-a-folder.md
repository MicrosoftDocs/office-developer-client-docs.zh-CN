---
title: 使用 SetColumns 高效枚举文件夹中的项
TOCTitle: Use SetColumns to efficiently enumerate items in a folder
ms:assetid: cd7c7758-8a9c-4f1c-a49c-9305d75be341
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184641(v=office.15)
ms:contentKeyID: 55119921
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bdfccc6432d35b6f39564e4c87404cc57b6ea27e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338036"
---
# <a name="use-setcolumns-to-efficiently-enumerate-items-in-a-folder"></a><span data-ttu-id="2ca37-102">使用 SetColumns 高效枚举文件夹中的项</span><span class="sxs-lookup"><span data-stu-id="2ca37-102">Use SetColumns to efficiently enumerate items in a folder</span></span>

<span data-ttu-id="2ca37-103">本示例演示如何提高使用 [SetColumns(String)](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 方法枚举 [Items](https://msdn.microsoft.com/library/bb610268\(v=office.15\)) 集合以缓存集合中每个项目的特定属性时的性能。</span><span class="sxs-lookup"><span data-stu-id="2ca37-103">This example shows how to improve the performance of enumerating the [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) collection by using the [SetColumns(String)](https://msdn.microsoft.com/library/bb610268\(v=office.15\)) method to cache certain properties of each item in the collection.</span></span>

## <a name="example"></a><span data-ttu-id="2ca37-104">示例</span><span class="sxs-lookup"><span data-stu-id="2ca37-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="2ca37-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="2ca37-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="2ca37-p101">若要枚举集合中的项目，需使用 **SetColumns** 方法来缓存 **Items** 集合上的属性。 **SetColumns** 采用一个表示属性名称的逗号分隔的字符串参数。在枚举了集合中的所有项目之后，调用 [ResetColumns()](https://msdn.microsoft.com/library/bb624355\(v=office.15\)) 方法以清除属性缓存。</span><span class="sxs-lookup"><span data-stu-id="2ca37-p101">To enumerate items in a collection, use the **SetColumns** method to cache properties on the **Items** collection. **SetColumns** takes an argument that is a comma-delimited string that represents property names. Once all items in the collection have been enumerated, call the [ResetColumns()](https://msdn.microsoft.com/library/bb624355\(v=office.15\)) method to clear the property cache.</span></span>

<span data-ttu-id="2ca37-109">在下面的代码示例中，EnumerateContactsWithSetColumns 使用 **SetColumns** 方法，以缓存“联系人”文件夹中项的 [FileAs](https://msdn.microsoft.com/library/bb647792\(v=office.15\))、[CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)) 和 [JobTitle](https://msdn.microsoft.com/library/bb609294\(v=office.15\)) 属性。</span><span class="sxs-lookup"><span data-stu-id="2ca37-109">In the following code example, EnumerateContactsWithSetColumns uses the **SetColumns** method to cache the [FileAs](https://msdn.microsoft.com/library/bb647792\(v=office.15\)), [CompanyName](https://msdn.microsoft.com/library/bb610212\(v=office.15\)), and [JobTitle](https://msdn.microsoft.com/library/bb609294\(v=office.15\)) properties of items in the Contacts folder.</span></span> <span data-ttu-id="2ca37-110">请注意，必须要测试限制中是否有空字符串或空引用。</span><span class="sxs-lookup"><span data-stu-id="2ca37-110">Note that you must test for empty strings or a null reference in the restriction.</span></span>

<span data-ttu-id="2ca37-111">请注意，Outlook 文件夹可能会包含不同类型的项。</span><span class="sxs-lookup"><span data-stu-id="2ca37-111">Note that an Outlook folder can possibly contain items of different types.</span></span> <span data-ttu-id="2ca37-112">此代码示例利用[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)一文中定义的 OutlookItem 帮助程序类，便捷地调用 OutlookItem.Class 属性，以验证文件夹中的筛选后项子集中每一项的邮件类别，再假设项为联系人项。</span><span class="sxs-lookup"><span data-stu-id="2ca37-112">This code sample makes use of the OutlookItem helper class, defined in [Create a Helper Class to Access Common Outlook Item Members](how-to-create-a-helper-class-to-access-common-outlook-item-members.md), to conveniently call the OutlookItem.Class property to verify the message class of each item in the filtered subset of items in the folder, before assuming the item is a contact item.</span></span>

<span data-ttu-id="2ca37-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="2ca37-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="2ca37-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="2ca37-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="2ca37-115">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="2ca37-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2ca37-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ca37-116">See also</span></span>

- [<span data-ttu-id="2ca37-117">搜索和筛选</span><span class="sxs-lookup"><span data-stu-id="2ca37-117">Search and filter</span></span>](search-and-filter.md)

