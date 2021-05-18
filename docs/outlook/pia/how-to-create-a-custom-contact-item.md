---
title: 创建自定义联系人项
TOCTitle: Create a custom Contact item
ms:assetid: 24b2a104-a0a7-469b-9676-a07cab613f59
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184596(v=office.15)
ms:contentKeyID: 55119831
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4261fffef0934e01cbfbcc7068377cc392af178c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361052"
---
# <a name="create-a-custom-contact-item"></a>创建自定义联系人项

此代码示例展示了如何创建自定义联系人项，并设置预定义属性和用户定义的属性。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

[ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 对象表示“联系人”文件夹中的联系人，内置有 [FirstName](https://msdn.microsoft.com/library/bb652965\(v=office.15\)) 和 [LastName](https://msdn.microsoft.com/library/bb609750\(v=office.15\)) 等超过 100 个属性。 有时，内置属性不足，需要添加自定义属性，为此可使用 [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) 集合。

在下面的代码示例中，CreateCustomItem 先创建自定义 **ContactItem** 对象并命名为“鞋店”，再调用 [Add(String, Object)](https://msdn.microsoft.com/library/bb645065\(v=office.15\)) 方法，将对象添加到“鞋店”文件夹中。 首先，CreateCustomItem 使用 [GetDefaultFolder(OlDefaultFolders)](https://msdn.microsoft.com/library/bb646473\(v=office.15\)) 方法，以获取“鞋店”文件夹。 “鞋店”文件夹是默认“联系人”文件夹的子文件夹。 然后，CreateCustomItem 设置 **FirstName** 和 **LastName** 属性，并使用 **UserProperties** 集合创建用户定义的属性（“鞋码”）。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void CreateCustomItem()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts).Folders[
        "Shoe Store"] as Outlook.Folder;
    Outlook.ContactItem contact =
        folder.Items.Add(
        "IPM.Contact.Shoe Store") as Outlook.ContactItem;
    contact.FirstName = "Michael";
    contact.LastName = "Affronti";
    contact.UserProperties["Shoe Size"].Value = "9";
    contact.Save();
}
```

## <a name="see-also"></a>另请参阅

- [联系人](contacts.md)

