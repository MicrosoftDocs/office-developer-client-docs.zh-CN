---
title: 在“选择姓名”对话框中显示与“联系人”文件夹对应的通讯簿
TOCTitle: Display in the Select Names dialog box the address book corresponding to a Contacts folder
ms:assetid: 6cbfc843-51b5-4841-bbb1-14b93a35ba78
ms:mtpsurl: https://msdn.microsoft.com/library/Bb610437(v=office.15)
ms:contentKeyID: 55119799
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 3be678b13738fead1509f3854c7b23bd0cfc8528
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356397"
---
# <a name="display-in-the-select-names-dialog-box-the-address-book-corresponding-to-a-contacts-folder"></a><span data-ttu-id="4fe88-102">在“选择姓名”对话框中显示与“联系人”文件夹对应的通讯簿</span><span class="sxs-lookup"><span data-stu-id="4fe88-102">Display in the Select Names dialog box the address book corresponding to a Contacts folder</span></span>

<span data-ttu-id="4fe88-103">该示例演示如何获得对应于默认“联系人”文件夹的通讯簿，然后在“选择姓名”\*\*\*\* 对话框中显示该通讯簿。</span><span class="sxs-lookup"><span data-stu-id="4fe88-103">This example shows how to obtain the address book that corresponds to the default Contacts folder, and then displays the address book in the **Select Names** dialog box.</span></span>

## <a name="example"></a><span data-ttu-id="4fe88-104">示例</span><span class="sxs-lookup"><span data-stu-id="4fe88-104">Example</span></span>

<span data-ttu-id="4fe88-105">Outlook 中的所有通讯簿都由 [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 对象的 [AddressLists](https://msdn.microsoft.com/library/bb624048\(v=office.15\)) 属性表示为集合。</span><span class="sxs-lookup"><span data-stu-id="4fe88-105">All address books in Outlook are represented as a collection by the [AddressLists](https://msdn.microsoft.com/library/bb624048\(v=office.15\)) property of the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span> <span data-ttu-id="4fe88-106">此代码示例使用 [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) 对象的 [GetContactsFolder](https://msdn.microsoft.com/library/bb609225\(v=office.15\)) 方法，查找与每个地址列表对应的“联系人”文件夹。</span><span class="sxs-lookup"><span data-stu-id="4fe88-106">The code sample uses the [GetContactsFolder](https://msdn.microsoft.com/library/bb609225\(v=office.15\)) method of the [AddressList](https://msdn.microsoft.com/library/bb623538\(v=office.15\)) object to find the contact folder that corresponds to each address list.</span></span> <span data-ttu-id="4fe88-107">每个 Outlook 文件夹都有一个条目 ID。</span><span class="sxs-lookup"><span data-stu-id="4fe88-107">Each Outlook folder has an Entry ID.</span></span> <span data-ttu-id="4fe88-108">比较默认“联系人”文件夹的条目 ID 与“联系人”文件夹的条目 ID，以生成与默认“联系人”文件夹对应的地址列表。</span><span class="sxs-lookup"><span data-stu-id="4fe88-108">Compare the Entry ID of the default Contacts folder with the Entry ID of a Contacts folder to produce the AddressList that corresponds to the default Contacts folder.</span></span>

<span data-ttu-id="4fe88-109">在“选择姓名”\*\*\*\* 对话框中显示与默认“联系人”文件夹对应的地址列表前，此代码示例先将它设置为 [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) 对象的 [InitialAddressList](https://msdn.microsoft.com/library/bb646633\(v=office.15\)) 属性值。</span><span class="sxs-lookup"><span data-stu-id="4fe88-109">Before displaying the address list corresponding to the default Contacts folder in the **Select Names** dialog box, the code sample sets it as the value of the [InitialAddressList](https://msdn.microsoft.com/library/bb646633\(v=office.15\)) property of the [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) object.</span></span>

<span data-ttu-id="4fe88-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="4fe88-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="4fe88-111">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="4fe88-111">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="4fe88-112">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="4fe88-112">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub ShowContactsFolderAsInitialAddressList()
    Dim addrLists As Outlook.AddressLists
    Dim contactsFolder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderContacts), _
        Outlook.Folder)
    addrLists = Application.Session.AddressLists
    For Each addrList As Outlook.AddressList In addrLists
        Dim testFolder As Outlook.Folder = _
        CType(addrList.GetContactsFolder(), Outlook.Folder)
        If Not (testFolder Is Nothing) Then
            ' Test to determine if Folder returned
            ' by GetContactsFolder has same EntryID
            ' as default Contacts folder.
            If (Application.Session.CompareEntryIDs( _
                contactsFolder.EntryID, testFolder.EntryID)) Then
                Dim snd As Outlook.SelectNamesDialog = _
                    Application.Session.GetSelectNamesDialog()
                snd.InitialAddressList = addrList
                snd.Display()
            End If
        End If
    Next
End Sub
```


```csharp
private void ShowContactsFolderAsInitialAddressList()
{
    Outlook.AddressLists addrLists;
    Outlook.Folder contactsFolder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts)
        as Outlook.Folder;
    addrLists = Application.Session.AddressLists;
    foreach (Outlook.AddressList addrList in addrLists)
    {
        Outlook.Folder testFolder =
            addrList.GetContactsFolder() as Outlook.Folder;
        if (testFolder != null)
        {
            // Test to determine if Folder returned
            // by GetContactsFolder has same EntryID
            // as default Contacts folder.
            if (Application.Session.CompareEntryIDs(
                contactsFolder.EntryID, testFolder.EntryID))
            {
                Outlook.SelectNamesDialog snd =
                    Application.
                    Session.GetSelectNamesDialog();
                snd.InitialAddressList = addrList;
                snd.Display();
             }
         }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="4fe88-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fe88-113">See also</span></span>

- [<span data-ttu-id="4fe88-114">通讯簿</span><span class="sxs-lookup"><span data-stu-id="4fe88-114">Address book</span></span>](address-book.md)

