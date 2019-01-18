---
title: 修改电子名片的布局
TOCTitle: Modify the layout of an electronic business card
ms:assetid: f387c4a7-59c5-4b6a-b33a-1bfa7d499bbf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184653(v=office.15)
ms:contentKeyID: 55119838
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7f85324b31ae865c69e2c40806d9654a0b443f4b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722737"
---
# <a name="modify-the-layout-of-an-electronic-business-card"></a><span data-ttu-id="c4f2a-102">修改电子名片的布局</span><span class="sxs-lookup"><span data-stu-id="c4f2a-102">Modify the layout of an electronic business card</span></span>

<span data-ttu-id="c4f2a-103">此代码示例展示了如何使用 [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) 接口的 [BusinessCardLayoutXml](https://msdn.microsoft.com/library/bb624276\(v=office.15\)) 属性，修改电子名片的布局。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-103">This example shows how to modify the layout of an electronic business card by using the [BusinessCardLayoutXml](https://msdn.microsoft.com/library/bb624276\(v=office.15\)) property of the [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) interface.</span></span>

## <a name="example"></a><span data-ttu-id="c4f2a-104">示例</span><span class="sxs-lookup"><span data-stu-id="c4f2a-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="c4f2a-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="c4f2a-106">电子名片提供可捕获联系人具体信息的联系人视图。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-106">An electronic business card provides a contact view that captures specific information from that contact.</span></span> <span data-ttu-id="c4f2a-107">**ContactItem** 接口提供与电子名片相关的特定成员。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-107">The **ContactItem** interface provides specific members that pertain to electronic business cards.</span></span> <span data-ttu-id="c4f2a-108">这些成员包括 **BusinessCardLayoutXml**、[BusinessCardType](https://msdn.microsoft.com/library/bb612276\(v=office.15\))、[AddBusinessCardLogoPicture(String)](https://msdn.microsoft.com/library/bb646681\(v=office.15\))、[ForwardAsBusinessCard()](https://msdn.microsoft.com/library/bb646342\(v=office.15\))、[ResetBusinessCard()](https://msdn.microsoft.com/library/bb644057\(v=office.15\))、[SaveBusinessCardImage(String)](https://msdn.microsoft.com/library/bb623060\(v=office.15\)) 和 [ShowBusinessCardEditor()](https://msdn.microsoft.com/library/bb646685\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-108">These members are **BusinessCardLayoutXml**, [BusinessCardType](https://msdn.microsoft.com/library/bb612276\(v=office.15\)), [AddBusinessCardLogoPicture(String)](https://msdn.microsoft.com/library/bb646681\(v=office.15\)), [ForwardAsBusinessCard()](https://msdn.microsoft.com/library/bb646342\(v=office.15\)), [ResetBusinessCard()](https://msdn.microsoft.com/library/bb644057\(v=office.15\)), [SaveBusinessCardImage(String)](https://msdn.microsoft.com/library/bb623060\(v=office.15\)), and [ShowBusinessCardEditor()](https://msdn.microsoft.com/library/bb646685\(v=office.15\)).</span></span>

<span data-ttu-id="c4f2a-109">在下面的代码示例中，BusinessCardLayoutExample 先获取指定 **ContactItem** 对象，以修改电子名片的布局。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-109">In the following code example, BusinessCardLayoutExample modifies the layout of an electronic business card by first obtaining a specified **ContactItem** object.</span></span> <span data-ttu-id="c4f2a-110">在此代码示例中，**ContactItem** 是 [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) 属性值等于“Melissa MacBeth”的联系人。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-110">In this case, the **ContactItem** is a contact with the value of the [Subject](https://msdn.microsoft.com/library/bb624088\(v=office.15\)) property equal to “Melissa MacBeth”.</span></span> <span data-ttu-id="c4f2a-111">接下来，BusinessCardLayoutExample 创建 XML 文档类 [XmlDocument](https://msdn.microsoft.com/en-us/library/6kza7w4k)，然后使用 **ContactItem** 对象的 **BusinessCardLayoutXML** 值，以字符串形式获取这个类的布局属性。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-111">Next, BusinessCardLayoutExample creates an XML document class [XmlDocument](https://msdn.microsoft.com/en-us/library/6kza7w4k), and then gets the layout attribute of this class in a string by using the **BusinessCardLayoutXML** value for the **ContactItem** object.</span></span> <span data-ttu-id="c4f2a-112">然后，名片布局从左对齐更改为右对齐。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-112">The card layout is then changed from left-aligned to right-aligned.</span></span>

<span data-ttu-id="c4f2a-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="c4f2a-114">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-114">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="c4f2a-115">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="c4f2a-115">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c4f2a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f2a-116">See also</span></span>

- [<span data-ttu-id="c4f2a-117">电子名片</span><span class="sxs-lookup"><span data-stu-id="c4f2a-117">Electronic business cards</span></span>](electronic-business-cards.md)

