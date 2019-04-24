---
title: 创建通讯组列表
TOCTitle: Create a distribution list
ms:assetid: c1fdbf3d-9669-4721-aabf-e8a332b82e0e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184637(v=office.15)
ms:contentKeyID: 55119841
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f37338209ea468d0143dfd1063c3c57216bc13ea
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359652"
---
# <a name="create-a-distribution-list"></a><span data-ttu-id="a28e4-102">创建通讯组列表</span><span class="sxs-lookup"><span data-stu-id="a28e4-102">Create a distribution list</span></span>

<span data-ttu-id="a28e4-103">此代码示例展示了如何创建通讯组列表，并向用户显示它。</span><span class="sxs-lookup"><span data-stu-id="a28e4-103">This example shows how to create a distribution list and display it to the user.</span></span>

## <a name="example"></a><span data-ttu-id="a28e4-104">示例</span><span class="sxs-lookup"><span data-stu-id="a28e4-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="a28e4-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="a28e4-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>


<span data-ttu-id="a28e4-106">在下面的代码示例中，CreateDistributionList 调用 [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) 方法来创建 [DistListItem](https://msdn.microsoft.com/library/bb645382\(v=office.15\)) 对象，以创建通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a28e4-106">In the following code example, CreateDistributionList creates a distribution list by calling the [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) method to create a [DistListItem](https://msdn.microsoft.com/library/bb645382\(v=office.15\)) object.</span></span> <span data-ttu-id="a28e4-107">接下来，它创建 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象，并调用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612189\(v=office.15\)) 方法，以在默认“联系人”文件夹中查找 [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) 属性值为“Top Customer”且 [Email1Address](https://msdn.microsoft.com/library/bb609902\(v=office.15\)) 属性值非空的所有联系人。</span><span class="sxs-lookup"><span data-stu-id="a28e4-107">Next it creates a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, and calls the [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612189\(v=office.15\)) method to find all contacts in the default Contacts folder for which the [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) property value is “Top Customer” and the [Email1Address](https://msdn.microsoft.com/library/bb609902\(v=office.15\)) property value is not empty.</span></span> <span data-ttu-id="a28e4-108">当所有联系人都被确定后，**Email1Address** 姓名便会作为列添加到 **Table** 中。</span><span class="sxs-lookup"><span data-stu-id="a28e4-108">Once all contacts are identified, the **Email1Address** name is added as a column to the **Table**.</span></span> <span data-ttu-id="a28e4-109">然后，CreateDistributionList 使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象中的 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 方法，以创建 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="a28e4-109">CreateDistributionList then creates a [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) object by using the [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) method from the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span> <span data-ttu-id="a28e4-110">最后，CreateDistributionList 向用户显示“Top Customers”通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="a28e4-110">CreateDistributionList finally displays the “Top Customers” distribution list to the user.</span></span>

> [!NOTE] 
> <span data-ttu-id="a28e4-111">必须向 [DistListItem](https://msdn.microsoft.com/library/bb645382(v=office.15)) 对象的 [AddMember(Recipient)](https://msdn.microsoft.com/library/bb612290(v=office.15)) 方法传递已解析的 **Recipient** 对象作为参数。</span><span class="sxs-lookup"><span data-stu-id="a28e4-111">You must pass a resolved **Recipient** object as a parameter to the [AddMember(Recipient)](https://msdn.microsoft.com/library/bb612290(v=office.15)) method of the [DistListItem](https://msdn.microsoft.com/library/bb645382(v=office.15)) object.</span></span> <span data-ttu-id="a28e4-112">若要解析 **Recipient** 对象，请使用 [Resolve()](https://msdn.microsoft.com/library/bb624165(v=office.15)) 方法。</span><span class="sxs-lookup"><span data-stu-id="a28e4-112">To resolve a **Recipient** object, use the [Resolve()](https://msdn.microsoft.com/library/bb624165(v=office.15)) method.</span></span>

<span data-ttu-id="a28e4-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="a28e4-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="a28e4-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，而且这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="a28e4-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="a28e4-115">下面几行代码展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="a28e4-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateDistributionList()
{
    Outlook.DistListItem distList = Application.CreateItem(
        Outlook.OlItemType.olDistributionListItem)
        as Outlook.DistListItem;
    distList.Subject = "Top Customers";
    //Find top customer category in Contacts folder
    string filter = "[Categories] = 'Top Customer'"
        + " AND [Email1Address] <> ''";
    Outlook.Table table =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderContacts).
        GetTable(filter, Outlook.OlTableContents.olUserItems);
    table.Columns.Add("Email1Address");
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        Outlook.Recipient recip =
            Application.Session.CreateRecipient(
            nextRow["Email1Address"].ToString());
        //Resolve the Recipient before calling AddMember
        recip.Resolve();
        distList.AddMember(recip);
    }
    distList.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="a28e4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a28e4-116">See also</span></span>

- [<span data-ttu-id="a28e4-117">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="a28e4-117">Exchange users</span></span>](exchange-users.md)

