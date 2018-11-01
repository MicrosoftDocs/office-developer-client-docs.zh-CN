---
title: 获取 Exchange 通讯组列表的成员
TOCTitle: Get members of an Exchange distribution list
ms:assetid: 75b38e40-772c-400b-8df9-e3e385b87f9c
ms:mtpsurl: https://msdn.microsoft.com/library/Bb645998(v=office.15)
ms:contentKeyID: 55119837
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 730ef62b6bff9cbfc2bf4aaae51116d2fe026131
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406559"
---
# <a name="get-members-of-an-exchange-distribution-list"></a><span data-ttu-id="2d8a5-102">获取 Exchange 通讯组列表的成员</span><span class="sxs-lookup"><span data-stu-id="2d8a5-102">Get members of an Exchange distribution list</span></span>

<span data-ttu-id="2d8a5-103">此代码示例提示用户从“选择姓名”\*\*\*\* 对话框中选择 Exchange 通讯组列表，然后展开选定通讯组列表以显示其中成员。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-103">This example prompts the user to select an Exchange distribution list from the Select Names dialog box and expands the distribution list to display its members.</span></span>

## <a name="example"></a><span data-ttu-id="2d8a5-104">示例</span><span class="sxs-lookup"><span data-stu-id="2d8a5-104">Example</span></span>

<span data-ttu-id="2d8a5-p101">该代码示例调用 [ExchangeDistributionList](https://msdn.microsoft.com/library/bb647622\(v=office.15\)) 对象的 [GetExchangeDistributionListMembers](https://msdn.microsoft.com/library/bb624320\(v=office.15\)) 方法以获取包含列表中所有成员的 [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) 集合。因为通讯组列表可以嵌套在另一个通讯组列表中，所以返回的 **AddressEntries** 集合可以代表任何类型的 Exchange [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-p101">This code sample calls the [GetExchangeDistributionListMembers](https://msdn.microsoft.com/library/bb647622\(v=office.15\)) method of the [ExchangeDistributionList](https://msdn.microsoft.com/library/bb624320\(v=office.15\)) object to get an [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) collection that contains all the members of the list. Because distribution lists can be nested inside another distribution list, the returned **AddressEntries** collection can represent any type of Exchange [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object.</span></span>


> [!NOTE]
> <span data-ttu-id="2d8a5-p102">[!注释] 展开通讯组列表会增加 Exchange 服务器的运行负担，因此请慎用 **GetExchangeDistributionListMembers** 方法。当您的代码展开大量通讯组列表时，代码的运行速度将变慢。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-p102">Expanding distribution lists can create a performance burden on an Exchange server, so use the **GetExchangeDistributionListMembers** method cautiously. Expect that your code will be slow when it expands large distribution lists.</span></span>

<span data-ttu-id="2d8a5-109">用户必须连接到 Exchange 服务器并处于联机状态，才能获取通讯组列表的成员。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-109">To obtain the members of a distribution list, the user must be connected to an Exchange server and online.</span></span>

<span data-ttu-id="2d8a5-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="2d8a5-111">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-111">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="2d8a5-112">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="2d8a5-112">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub GetDistributionListMembers()
    Dim snd As Outlook.SelectNamesDialog = _
        Application.Session.GetSelectNamesDialog()
    Dim addrLists As Outlook.AddressLists = _
        Application.Session.AddressLists
    For Each addrList As Outlook.AddressList In addrLists
        If addrList.Name = "All Groups" Then
            snd.InitialAddressList = addrList
            Exit For
        End If
    Next
    snd.NumberOfRecipientSelectors = _
        Outlook.OlRecipientSelectors.olShowTo
    snd.ToLabel = "D/L"
    snd.ShowOnlyInitialAddressList = True
    snd.AllowMultipleSelection = False
    snd.Display()
    If (snd.Recipients.Count > 0) Then
        Dim addrEntry As Outlook.AddressEntry = _
            snd.Recipients(1).AddressEntry
        If (addrEntry.AddressEntryUserType = _
            Outlook.OlAddressEntryUserType. _
            olExchangeDistributionListAddressEntry) Then
            Dim exchDL As Outlook.ExchangeDistributionList = _
                addrEntry.GetExchangeDistributionList()
            Dim addrEntries As Outlook.AddressEntries = _
                exchDL.GetExchangeDistributionListMembers()
            If Not (addrEntries Is Nothing) Then
                For Each exchDLMember As _
                    Outlook.AddressEntry In addrEntries
                    Debug.WriteLine(exchDLMember.Name)
                Next
            End If
         End If
    End If
End Sub
```


```csharp
private void GetDistributionListMembers()
{
    Outlook.SelectNamesDialog snd =
        Application.Session.GetSelectNamesDialog();
    Outlook.AddressLists addrLists =
        Application.Session.AddressLists;
    foreach (Outlook.AddressList addrList in addrLists)
    {
        if (addrList.Name == "All Groups")
        {
            snd.InitialAddressList = addrList;
            break;
        }
    }
    snd.NumberOfRecipientSelectors =
        Outlook.OlRecipientSelectors.olShowTo;
    snd.ToLabel = "D/L";
    snd.ShowOnlyInitialAddressList = true;
    snd.AllowMultipleSelection = false;
    snd.Display();
    if (snd.Recipients.Count > 0)
    {
        Outlook.AddressEntry addrEntry =
            snd.Recipients[1].AddressEntry;
        if (addrEntry.AddressEntryUserType ==
            Outlook.OlAddressEntryUserType.
            olExchangeDistributionListAddressEntry)
        {
            Outlook.ExchangeDistributionList exchDL =
                addrEntry.GetExchangeDistributionList();
            Outlook.AddressEntries addrEntries =
                exchDL.GetExchangeDistributionListMembers();
            if (addrEntries != null)
                foreach (Outlook.AddressEntry exchDLMember
                    in addrEntries)
                {
                    Debug.WriteLine(exchDLMember.Name);
                }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2d8a5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d8a5-113">See also</span></span>

- [<span data-ttu-id="2d8a5-114">Exchange 用户</span><span class="sxs-lookup"><span data-stu-id="2d8a5-114">Exchange Users</span></span>](exchange-users.md)
