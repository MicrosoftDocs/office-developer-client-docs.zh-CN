---
title: 修改电子名片的布局
TOCTitle: Modify the layout of an electronic business card
ms:assetid: f387c4a7-59c5-4b6a-b33a-1bfa7d499bbf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184653(v=office.15)
ms:contentKeyID: 55119838
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 0b95621df2e021f52587d5a40d0de43e5505b80c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406433"
---
# <a name="modify-the-layout-of-an-electronic-business-card"></a>修改电子名片的布局

此代码示例展示了如何使用 [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 接口的 [BusinessCardLayoutXml](https://msdn.microsoft.com/library/bb624276\(v=office.15\)) 属性，修改电子名片的布局。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

电子名片提供可捕获联系人具体信息的联系人视图。 **ContactItem** 接口提供与电子名片相关的特定成员。 这些成员包括 **BusinessCardLayoutXml**、[BusinessCardType](https://msdn.microsoft.com/library/bb612276\(v=office.15\))、[AddBusinessCardLogoPicture(String)](https://msdn.microsoft.com/library/bb646681\(v=office.15\))、[ForwardAsBusinessCard()](https://msdn.microsoft.com/library/bb646342\(v=office.15\))、[ResetBusinessCard()](https://msdn.microsoft.com/library/bb644057\(v=office.15\))、[SaveBusinessCardImage(String)](https://msdn.microsoft.com/library/bb623060\(v=office.15\)) 和 [ShowBusinessCardEditor()](https://msdn.microsoft.com/library/bb646685\(v=office.15\))。

在下面的代码示例中，BusinessCardLayoutExample 先获取指定 **ContactItem** 对象，以修改电子名片的布局。 在此代码示例中，**ContactItem** 是 [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) 属性值等于“Melissa MacBeth”的联系人。 接下来，BusinessCardLayoutExample 创建 XML 文档类 [XmlDocument](https://msdn.microsoft.com/zh-CN/library/6kza7w4k)，然后使用 **ContactItem** 对象的 **BusinessCardLayoutXML** 值，以字符串形式获取这个类的布局属性。 然后，名片布局从左对齐更改为右对齐。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void BusinessCardLayoutExample()
{
    Outlook.ContactItem contact =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts).Items.Find(
        "[Subject] = Melissa MacBeth'")
        as Outlook.ContactItem;
    if (contact != null)
    {
        XmlDocument doc = new XmlDocument();
        doc.LoadXml(contact.BusinessCardLayoutXml);
        XmlElement root = doc.DocumentElement;
        string layoutValue = root.GetAttribute("layout");
        if (layoutValue == "left")
        {
            root.SetAttribute("layout", "right");
            contact.BusinessCardLayoutXml = doc.OuterXml;
            contact.Save();
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- [电子名片](electronic-business-cards.md)

