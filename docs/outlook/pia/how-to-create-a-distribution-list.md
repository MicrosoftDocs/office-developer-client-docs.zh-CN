---
title: 创建通讯组列表
TOCTitle: Create a distribution list
ms:assetid: c1fdbf3d-9669-4721-aabf-e8a332b82e0e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184637(v=office.15)
ms:contentKeyID: 55119841
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 19b282a3b3e756814aa2add07cda4be7609206ac
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407133"
---
# <a name="create-a-distribution-list"></a>创建通讯组列表

此代码示例展示了如何创建通讯组列表，并向用户显示它。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。


在下面的代码示例中，CreateDistributionList 调用 [CreateItem(OlItemType)](https://msdn.microsoft.com/library/bb610587\(v=office.15\)) 方法来创建 [DistListItem](https://msdn.microsoft.com/library/bb645382\(v=office.15\)) 对象，以创建通讯组列表。 接下来，它创建 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象，并调用 [GetTable(Object, Object)](https://msdn.microsoft.com/library/bb612189\(v=office.15\)) 方法，以在默认“联系人”文件夹中查找 [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) 属性值为“Top Customer”且 [Email1Address](https://msdn.microsoft.com/library/bb609902\(v=office.15\)) 属性值非空的所有联系人。 当所有联系人都被确定后，**Email1Address** 姓名便会作为列添加到 **Table** 中。 然后，CreateDistributionList 使用 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象中的 [CreateRecipient(String)](https://msdn.microsoft.com/library/bb609962\(v=office.15\)) 方法，以创建 [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\)) 对象。 最后，CreateDistributionList 向用户显示“Top Customers”通讯组列表。

> [!NOTE] 
> 必须向 [DistListItem](https://msdn.microsoft.com/library/bb645382\(v=office.15\)) 对象的 [AddMember(Recipient)](https://msdn.microsoft.com/library/bb612290(v=office.15)) 方法传递已解析的 **Recipient** 对象作为参数。 若要解析 **Recipient** 对象，请使用 [Resolve()](https://msdn.microsoft.com/library/bb624165(v=office.15)) 方法。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [Exchange 用户](exchange-users.md)

