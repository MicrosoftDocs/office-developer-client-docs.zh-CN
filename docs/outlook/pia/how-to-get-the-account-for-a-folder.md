---
title: 获取与文件夹关联的帐户
TOCTitle: Get the account for a folder
ms:assetid: 3706be15-f746-4d0d-9ffe-d6f46b2004dc
ms:contentKeyID: 55119793
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d83a145b577cbc9be68cdd694f7806da7cdad512
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407203"
---
# <a name="get-the-account-for-a-folder"></a>获取与文件夹关联的帐户

此代码示例获取当前会话中与文件夹关联的帐户。

## <a name="example"></a>示例

在下面的代码示例中，DisplayAccountForCurrentFolder 函数调用 GetAccountForFolder 函数，以标识默认传递存储中托管有当前文件夹的帐户，再显示文件夹名称。 GetAccountForFolder 将当前文件夹的存储（通过 [Store](https://msdn.microsoft.com/library/bb612742\(v=office.15\)) 属性获取）与会话的 [Accounts](https://msdn.microsoft.com/library/bb646328\(v=office.15\)) 集合中定义的每个帐户的默认传递存储（通过 [DeliveryStore](https://msdn.microsoft.com/library/ff185090\(v=office.15\)) 属性获取）进行匹配。 如果找到匹配项，GetAccountForFolder 便会返回 [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) 对象；否则，便会返回空引用。

在配置文件中定义了多个帐户的 Microsoft Outlook 会话中，活动的资源管理器中显示的文件夹不一定位于该会话的默认存储区中；而是可能位于与多个帐户关联的多个存储区之一中。本主题演示如何标识其默认传送存储区与承载文件夹的存储区为同一存储区的帐户。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [帐户](accounts.md)

