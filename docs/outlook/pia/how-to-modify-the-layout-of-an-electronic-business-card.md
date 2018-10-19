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
# <a name="modify-the-layout-of-an-electronic-business-card"></a><span data-ttu-id="10a35-102">修改电子名片的布局</span><span class="sxs-lookup"><span data-stu-id="10a35-102">Modify the layout of an electronic business card</span></span>

<span data-ttu-id="10a35-103">此代码示例展示了如何使用 [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 接口的 [BusinessCardLayoutXml](https://msdn.microsoft.com/library/bb624276\(v=office.15\)) 属性，修改电子名片的布局。</span><span class="sxs-lookup"><span data-stu-id="10a35-103">This example shows how to modify the layout of an Electronic Business Card by using the [BusinessCardLayoutXml](https://msdn.microsoft.com/library/bb624276\(v=office.15\)) property of the [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) interface.</span></span>

## <a name="example"></a><span data-ttu-id="10a35-104">示例</span><span class="sxs-lookup"><span data-stu-id="10a35-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="10a35-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="10a35-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="10a35-106">电子名片提供可捕获联系人具体信息的联系人视图。</span><span class="sxs-lookup"><span data-stu-id="10a35-106">An Electronic Business Card provides a contact view that captures specific information from that contact.</span></span> <span data-ttu-id="10a35-107">**ContactItem** 接口提供与电子名片相关的特定成员。</span><span class="sxs-lookup"><span data-stu-id="10a35-107">The **ContactItem** interface provides specific members that pertain to Electronic Business Cards.</span></span> <span data-ttu-id="10a35-108">这些成员包括 **BusinessCardLayoutXml**、[BusinessCardType](https://msdn.microsoft.com/library/bb612276\(v=office.15\))、[AddBusinessCardLogoPicture(String)](https://msdn.microsoft.com/library/bb646681\(v=office.15\))、[ForwardAsBusinessCard()](https://msdn.microsoft.com/library/bb646342\(v=office.15\))、[ResetBusinessCard()](https://msdn.microsoft.com/library/bb644057\(v=office.15\))、[SaveBusinessCardImage(String)](https://msdn.microsoft.com/library/bb623060\(v=office.15\)) 和 [ShowBusinessCardEditor()](https://msdn.microsoft.com/library/bb646685\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="10a35-108">These members are **BusinessCardLayoutXml**, [BusinessCardType](https://msdn.microsoft.com/library/bb612276\(v=office.15\)) , [AddBusinessCardLogoPicture(String)](https://msdn.microsoft.com/library/bb646681\(v=office.15\)) , [ForwardAsBusinessCard()](https://msdn.microsoft.com/library/bb646342\(v=office.15\)) , [ResetBusinessCard()](https://msdn.microsoft.com/library/bb644057\(v=office.15\)) , [SaveBusinessCardImage(String)](https://msdn.microsoft.com/library/bb623060\(v=office.15\)) , and [ShowBusinessCardEditor()](https://msdn.microsoft.com/library/bb646685\(v=office.15\)) .</span></span>

<span data-ttu-id="10a35-109">在下面的代码示例中，BusinessCardLayoutExample 先获取指定 **ContactItem** 对象，以修改电子名片的布局。</span><span class="sxs-lookup"><span data-stu-id="10a35-109">In the following code example,   modifies the layout of an Electronic Business Card by first obtaining a specified ContactItem object.</span></span> <span data-ttu-id="10a35-110">在此代码示例中，**ContactItem** 是 [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) 属性值等于“Melissa MacBeth”的联系人。</span><span class="sxs-lookup"><span data-stu-id="10a35-110">In this case, the **ContactItem** is a contact with the value of the [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) property equal to "Melissa MacBeth".</span></span> <span data-ttu-id="10a35-111">接下来，BusinessCardLayoutExample 创建 XML 文档类 [XmlDocument](https://msdn.microsoft.com/zh-CN/library/6kza7w4k)，然后使用 **ContactItem** 对象的 **BusinessCardLayoutXML** 值，以字符串形式获取这个类的布局属性。</span><span class="sxs-lookup"><span data-stu-id="10a35-111">Next,   creates an XML document class XmlDocument , and then gets the layout attribute of this class in a string by using the BusinessCardLayoutXML value for the ContactItem object.</span></span> <span data-ttu-id="10a35-112">然后，名片布局从左对齐更改为右对齐。</span><span class="sxs-lookup"><span data-stu-id="10a35-112">The card layout is then changed from left-aligned to right-aligned.</span></span>

<span data-ttu-id="10a35-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="10a35-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="10a35-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="10a35-114">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="10a35-115">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="10a35-115">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="10a35-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10a35-116">See also</span></span>

- [<span data-ttu-id="10a35-117">电子名片</span><span class="sxs-lookup"><span data-stu-id="10a35-117">Electronic Business Cards</span></span>](electronic-business-cards.md)

