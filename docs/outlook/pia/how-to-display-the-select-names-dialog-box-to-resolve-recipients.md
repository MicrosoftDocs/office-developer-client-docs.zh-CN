---
title: 显示“选择姓名”对话框以解析收件人
TOCTitle: Display the Select Names dialog box to resolve recipients
ms:assetid: 841dd4cd-6d69-46d5-8c83-e28c95b631a9
ms:mtpsurl: https://msdn.microsoft.com/library/Bb646055(v=office.15)
ms:contentKeyID: 55119876
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f92891188e7c317465ce70fede1dedca7f6344fe
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723038"
---
# <a name="display-the-select-names-dialog-box-to-resolve-recipients"></a><span data-ttu-id="d6ebf-102">显示“选择姓名”对话框以解析收件人</span><span class="sxs-lookup"><span data-stu-id="d6ebf-102">Display the Select Names dialog box to resolve recipients</span></span>

<span data-ttu-id="d6ebf-103">该示例尝试解析 *recips* 参数所提供的收件人，并为每个因不明确而无法解析的收件人显示 Outlook“选择姓名”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-103">This example attempts to resolve the recipients provided by the *recips* parameter, and displays the Outlook **Select Names** dialog box for each recipient that is ambiguous and cannot be resolved.</span></span>

## <a name="example"></a><span data-ttu-id="d6ebf-104">示例</span><span class="sxs-lookup"><span data-stu-id="d6ebf-104">Example</span></span>

<span data-ttu-id="d6ebf-105">此代码示例调用 [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) 对象，以调出显示 Outlook 通讯簿的“选择姓名”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-105">This code sample calls the [SelectNamesDialog](https://msdn.microsoft.com/library/bb609866\(v=office.15\)) object to display the **Select Names** dialog box which shows the Outlook address book.</span></span> <span data-ttu-id="d6ebf-106">通过此对话框，用户可以从通讯簿中选择姓名。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-106">Through this dialog box, the user can select a name from the address book.</span></span> <span data-ttu-id="d6ebf-107">如果姓名无法解析，此代码示例便会从 recips 中删除相应收件人。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-107">If the name is not resolved, the recipient will be removed from recips.</span></span> <span data-ttu-id="d6ebf-108">如果姓名已解析，此代码示例便会向 recips 返回相应收件人的 [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) 对象。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-108">If the name is resolved, then the code sample will return the [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object of the recipient to recips.</span></span>

<span data-ttu-id="d6ebf-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="d6ebf-110">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-110">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="d6ebf-111">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="d6ebf-111">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub ResolveRecipients(ByVal recips As Outlook.Recipients)
    If recips Is Nothing Then
        Throw New ArgumentNullException()
    End If
    If recips.ResolveAll() Then
        Return
    Else
        For i As Integer = recips.Count To 1 Step -1
            If Not (recips(i).Resolve()) Then
                Dim snd As Outlook.SelectNamesDialog = _
                    Application.Session.GetSelectNamesDialog()
                snd.Recipients.Add(recips(i).Name)
                snd.NumberOfRecipientSelectors = _
                    Outlook.OlRecipientSelectors.olShowTo
                snd.AllowMultipleSelection = False
                snd.Display()
                If Not (snd.Recipients.ResolveAll()) Then
                    recips.Remove(i)
                Else
                    recips.Remove(i)
                    recips.Add(snd.Recipients(1).Address)
                End If
                snd = Nothing
            End If
        Next
    End If
End Sub
```


```csharp
private void ResolveRecipients(Outlook.Recipients recips)
{
    if (recips == null)
    {
        throw new ArgumentNullException();
    }
    if (recips.ResolveAll())
    {
        return;
    }
    else
    {
        for (int i = recips.Count; i > 0; i--)
        {
            if (!recips[i].Resolve())
            {
                Outlook.SelectNamesDialog snd =
                    Application.Session.
                    GetSelectNamesDialog();
                snd.Recipients.Add(recips[i].Name);
                snd.NumberOfRecipientSelectors =
                    Outlook.OlRecipientSelectors.olShowTo;
                snd.AllowMultipleSelection = false;
                snd.Display();
                if (!snd.Recipients.ResolveAll())
                {
                    recips.Remove(i);
                }
                else
                {
                    recips.Remove(i);
                    recips.Add(snd.Recipients[1].Address);
                }
                snd = null;
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="d6ebf-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6ebf-112">See also</span></span>

- [<span data-ttu-id="d6ebf-113">收件人</span><span class="sxs-lookup"><span data-stu-id="d6ebf-113">Recipients</span></span>](recipients.md)

