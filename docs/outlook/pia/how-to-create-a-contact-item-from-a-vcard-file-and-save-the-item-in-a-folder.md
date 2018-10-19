---
title: 通过 vCard 文件创建联系人项，并将项保存到文件夹中
TOCTitle: Create a Contact item from a vCard file and save the item in a folder
ms:assetid: b207b584-ffcf-4ac5-ab1f-4f91d43000e1
ms:mtpsurl: https://msdn.microsoft.com/library/Bb646856(v=office.15)
ms:contentKeyID: 55119826
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 667278b290e32bc5115a468b1c038d6aa63a5aff
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407392"
---
# <a name="create-a-contact-item-from-a-vcard-file-and-save-the-item-in-a-folder"></a><span data-ttu-id="b7423-102">通过 vCard 文件创建联系人项，并将项保存到文件夹中</span><span class="sxs-lookup"><span data-stu-id="b7423-102">Create a Contact item from a vCard file and save the item in a folder</span></span>

<span data-ttu-id="b7423-103">此代码示例将所有 vCard 文件导入文件系统文件夹中，并将联系人保存到 *targetFolder* 参数指定的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b7423-103">This example imports all the vCard files in a file system folder and saves the contacts into the folder specified by the  *targetFolder* parameter.</span></span>

## <a name="example"></a><span data-ttu-id="b7423-104">示例</span><span class="sxs-lookup"><span data-stu-id="b7423-104">Example</span></span>

<span data-ttu-id="b7423-p101">该示例使用 [OpenSharedItem](https://msdn.microsoft.com/library/bb645399\(v=office.15\)) 方法。 **OpenSharedItem** 方法打开存储为 Outlook 邮件格式 (.msg) 文件、iCalendar 约会 (.ics) 文件或 vCard (.vcf) 文件的邮件。确保将返回的对象转换为适当的项目类型并调用相应的 **Save** 方法来使项目持久。默认情况下， **OpenSharedItem** 返回的项目保存在特定项目类型的默认文件夹中。可使用相应的 **Move** 方法将项目移动到不同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b7423-p101">This example uses the [OpenSharedItem](https://msdn.microsoft.com/library/bb645399\(v=office.15\)) method. The **OpenSharedItem** method opens messages stored as Outlook message format (.msg) files, iCalendar appointment (.ics) files, or vCard (.vcf) files. Be sure to cast the returned object to the appropriate item type and call the corresponding **Save** method to persist the item. By default, the item returned by **OpenSharedItem** is saved in the default folder for the specific item type. You can use the corresponding **Move** method to move the item to a different folder.</span></span>

<span data-ttu-id="b7423-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b7423-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b7423-111">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b7423-111">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b7423-112">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b7423-112">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub ImportContacts( _
    ByVal path As String, ByVal targetFolder As Outlook.Folder)
    Dim contact As Outlook.ContactItem
    Dim moveContact As Outlook.ContactItem
    If (Directory.Exists(path)) Then
        Dim files As String() = Directory.GetFiles(path, "*.vcf")
        For Each file As String In files
            contact = CType(Application.Session.OpenSharedItem(file), _
                Outlook.ContactItem)
            If (targetFolder Is _
                CType(Application.Session.GetDefaultFolder( _
                    Outlook.OlDefaultFolders.olFolderContacts) _
                    , Outlook.Folder)) Then
                contact.Save()
            Else
                moveContact = CType(contact.Move(targetFolder), _
                    Outlook.ContactItem)
                moveContact.Save()
            End If
        Next
    End If
End Sub
```


```csharp
private void ImportContacts(string path, Outlook.Folder targetFolder)
{
    Outlook.ContactItem contact;
    Outlook.ContactItem moveContact;
    if (Directory.Exists(path))
    {
        string[] files = Directory.GetFiles(path, "*.vcf");
        foreach (string file in files)
        {
            contact = Application.Session.OpenSharedItem(file)
                as Outlook.ContactItem;
            if (targetFolder ==
                Application.Session.GetDefaultFolder(
                Outlook.OlDefaultFolders.olFolderContacts)
                as Outlook.Folder)
            {
                contact.Save();
            }
            else
            {
                moveContact = contact.Move(targetFolder)
                    as Outlook.ContactItem;
                moveContact.Save();
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b7423-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7423-113">See also</span></span>

- [<span data-ttu-id="b7423-114">联系人</span><span class="sxs-lookup"><span data-stu-id="b7423-114">Contacts</span></span>](contacts.md)

