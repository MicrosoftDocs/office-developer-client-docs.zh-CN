---
title: 获取与文件夹关联的帐户
TOCTitle: Get the account for a folder
ms:assetid: 3706be15-f746-4d0d-9ffe-d6f46b2004dc
ms:contentKeyID: 55119793
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8f56f866e71b1080d5b7a6a33fb17e3e71ab9199
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708093"
---
# <a name="get-the-account-for-a-folder"></a><span data-ttu-id="8c642-102">获取与文件夹关联的帐户</span><span class="sxs-lookup"><span data-stu-id="8c642-102">Get the account for a folder</span></span>

<span data-ttu-id="8c642-103">此代码示例获取当前会话中与文件夹关联的帐户。</span><span class="sxs-lookup"><span data-stu-id="8c642-103">This example gets the account that is associated with a folder in the current session.</span></span>

## <a name="example"></a><span data-ttu-id="8c642-104">示例</span><span class="sxs-lookup"><span data-stu-id="8c642-104">Example</span></span>

<span data-ttu-id="8c642-105">在下面的代码示例中，DisplayAccountForCurrentFolder 函数调用 GetAccountForFolder 函数，以标识默认传递存储中托管有当前文件夹的帐户，再显示文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="8c642-105">In the following code example, the DisplayAccountForCurrentFolder function calls the GetAccountForFolder function to identify the account whose default delivery store hosts the current folder, and then displays the name of the folder.</span></span> <span data-ttu-id="8c642-106">GetAccountForFolder 将当前文件夹的存储（通过 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获取）与会话的 [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) 集合中定义的每个帐户的默认传递存储（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获取）进行匹配。</span><span class="sxs-lookup"><span data-stu-id="8c642-106">GetAccountForFolder matches the store of the current folder (obtained from the [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) property) with the default delivery store of each account (obtained with the [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) property) that is defined in the [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) collection for the session.</span></span> <span data-ttu-id="8c642-107">如果找到匹配项，GetAccountForFolder 便会返回 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象；否则，便会返回空引用。</span><span class="sxs-lookup"><span data-stu-id="8c642-107">GetAccountForFolder returns the [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object if a match is found; otherwise, it returns a null reference.</span></span>

<span data-ttu-id="8c642-p102">在配置文件中定义了多个帐户的 Microsoft Outlook 会话中，活动的资源管理器中显示的文件夹不一定位于该会话的默认存储区中；而是可能位于与多个帐户关联的多个存储区之一中。本主题演示如何标识其默认传送存储区与承载文件夹的存储区为同一存储区的帐户。</span><span class="sxs-lookup"><span data-stu-id="8c642-p102">In a Microsoft Outlook session that has multiple accounts defined in the profile, the folder that is displayed in the active explorer does not necessarily reside on the default store for that session; instead, it can reside on one of the multiple stores associated with the multiple accounts. This topic shows how to identify the account whose default delivery store is the same store that hosts the folder.</span></span>

<span data-ttu-id="8c642-110">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="8c642-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="8c642-111">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="8c642-111">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="8c642-112">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="8c642-112">The following line of code shows how to do the import and assignment in C\#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void DisplayAccountForCurrentFolder()
{
    Outlook.Folder myFolder = Application.ActiveExplorer().CurrentFolder 
        as Outlook.Folder;
    string msg = "Account for Current Folder:" + "\n" +
        GetAccountForFolder(myFolder).DisplayName;
    MessageBox.Show(msg,
        "GetAccountForFolder",
        MessageBoxButtons.OK,
        MessageBoxIcon.Information);
}

Outlook.Account GetAccountForFolder(Outlook.Folder folder)
{
    // Obtain the store on which the folder resides.
    Outlook.Store store = folder.Store;

    // Enumerate the accounts defined for the session.
    foreach (Outlook.Account account in Application.Session.Accounts)
    {
        // Match the DefaultStore.StoreID of the account
        // with the Store.StoreID for the currect folder.
        if (account.DeliveryStore.StoreID  == store.StoreID)
        {
            // Return the account whose default delivery store
            // matches the store of the given folder.
            return account;
        }
     }
     // No account matches, so return null.
     return null;
}
```

## <a name="see-also"></a><span data-ttu-id="8c642-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c642-113">See also</span></span>

- [<span data-ttu-id="8c642-114">帐户</span><span class="sxs-lookup"><span data-stu-id="8c642-114">Accounts</span></span>](accounts.md)

