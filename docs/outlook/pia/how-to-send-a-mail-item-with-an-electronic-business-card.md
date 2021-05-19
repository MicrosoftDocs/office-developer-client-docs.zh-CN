---
title: 发送包含电子名片的邮件项
TOCTitle: Send a mail item with an electronic business card
ms:assetid: f8aae7f2-85fc-4ed0-9f59-282ede702357
ms:mtpsurl: https://msdn.microsoft.com/library/Bb624312(v=office.15)
ms:contentKeyID: 55119839
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 25809fc0d1726c9f56be417ae53fadecc831d62f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331148"
---
# <a name="send-a-mail-item-with-an-electronic-business-card"></a><span data-ttu-id="bde18-102">发送包含电子名片的邮件项</span><span class="sxs-lookup"><span data-stu-id="bde18-102">Send a mail item with an electronic business card</span></span>

<span data-ttu-id="bde18-103">此代码示例创建邮件项、查找电子名片，并将找到的电子名片插入邮件项中。</span><span class="sxs-lookup"><span data-stu-id="bde18-103">This example creates a mail item, looks for an electronic business card, and if it finds one, inserts the electronic business card into the mail item.</span></span>

## <a name="example"></a><span data-ttu-id="bde18-104">示例</span><span class="sxs-lookup"><span data-stu-id="bde18-104">Example</span></span>

<span data-ttu-id="bde18-105">若要插入电子名片，可以对 [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) 对象调用 [AddBusinessCard](https://msdn.microsoft.com/library/bb647034\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="bde18-105">To insert an electronic business card, you can call [AddBusinessCard](https://msdn.microsoft.com/library/bb647034\(v=office.15\)) on the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object.</span></span> <span data-ttu-id="bde18-106">此方法需要使用表示电子邮件地址的字符串，并尝试在默认“联系人”文件夹中查找具有相应地址的 [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\))。</span><span class="sxs-lookup"><span data-stu-id="bde18-106">This method takes a string representing an email address and attempts to find a [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) with that address in the default Contacts folder.</span></span> <span data-ttu-id="bde18-107">一个 **ContactItem** 最多可以有三个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bde18-107">A **ContactItem** can have as many as three email addresses.</span></span> <span data-ttu-id="bde18-108">如果找到联系人，此代码示例便会调用 **AddBusinessCard** 方法，然后向用户显示邮件。</span><span class="sxs-lookup"><span data-stu-id="bde18-108">If the contact is found, the example calls the **AddBusinessCard** method, and then displays the message to the user.</span></span>

<span data-ttu-id="bde18-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="bde18-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="bde18-110">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="bde18-110">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="bde18-111">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="bde18-111">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub AddBusinessCard(ByVal eMailAddress As String)
    Dim mail As Outlook.MailItem = CType(Application.CreateItem( _
        Outlook.OlItemType.olMailItem), Outlook.MailItem)
    mail.BodyFormat = Outlook.OlBodyFormat.olFormatHTML
    Dim contact As Outlook.ContactItem = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderContacts).Items.Find( _
        "[Email1Address]='" & eMailAddress & "'" & " OR " & _
        "[Email2Address]='" & eMailAddress & "'" + " OR " & _
        "[Email3Address]='" & eMailAddress & "'") _
        , Outlook.ContactItem)
    If (contact Is Nothing) Then
        Return
    End If
    mail.AddBusinessCard(contact)
    mail.Display(False)
End Sub
```


```csharp
private void AddBusinessCard(string eMailAddress)
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.BodyFormat = Outlook.OlBodyFormat.olFormatHTML;
    Outlook.ContactItem contact = Application.Session.
        GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts).Items.Find(
        "[Email1Address]='" + eMailAddress + "'" + " OR " +
        "[Email2Address]='" + eMailAddress + "'" + " OR " +
        "[Email3Address]='" + eMailAddress + "'")
        as Outlook.ContactItem;
    if (contact == null)
    {
        return;
    }
    mail.AddBusinessCard(contact);
    mail.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="bde18-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bde18-112">See also</span></span>

- [<span data-ttu-id="bde18-113">电子名片</span><span class="sxs-lookup"><span data-stu-id="bde18-113">Electronic business cards</span></span>](electronic-business-cards.md)

