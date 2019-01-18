---
title: 添加或删除存储
TOCTitle: Add or remove a store
ms:assetid: db2930ec-ef99-4e31-86c5-820e8368e05f
ms:mtpsurl: https://msdn.microsoft.com/library/Bb612380(v=office.15)
ms:contentKeyID: 55119895
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4346f3bf1b7bba1f26a34e1562997b4d043c8d49
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723024"
---
# <a name="add-or-remove-a-store"></a>添加或删除存储

此代码示例展示了如何在给定配置文件中添加和删除存储。

## <a name="example"></a>示例

该代码示例演示如何在指定的配置文件中，通过分别调用 [NameSpace](https://msdn.microsoft.com/library/bb623442\(v=office.15\)) 对象上的 [AddStoreEx](https://msdn.microsoft.com/library/bb610524\(v=office.15\)) 方法和 [RemoveStore](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法来添加和移除存储。

在 Outlook 中，只能以编程方式添加或删除 PST 存储。 下面的代码示例添加 Unicode 存储，并将 .pst 文件置于用户 .pst 文件的默认位置上：Documents and Settings\\\<UserName\>\\Local Settings\\Application Data\\Microsoft\\Outlook。 此代码示例使用 Environment.SpecialFolder.LocalApplicationData，检索“本地设置”文件夹下“应用程序数据”文件夹的路径。 添加存储后，此代码示例便会删除存储。 因为 **RemoveStore** 方法要求 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象移除 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象，所以它枚举 [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) 集合来查找刚才根据 **Store** 对象的 [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) 属性添加的 **Store** 对象。

**RemoveStore** 仅从当前配置文件中删除存储，不会从文件系统中删除 .pst 文件。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub CreateUnicodePST()
    Dim path As String = Environment.GetFolderPath( _
        Environment.SpecialFolder.LocalApplicationData) _
        & "\Microsoft\Outlook\MyUnicodeStore.pst"
    Try
        Application.Session.AddStoreEx( _
            path, Outlook.OlStoreType.olStoreUnicode)
        Dim stores As Outlook.Stores = Application.Session.Stores
        For Each store As Outlook.Store In stores
            If store.FilePath = path Then
                Dim folder As Outlook.Folder = _
                    CType(store.GetRootFolder(), Outlook.Folder)
                ' Remove the store
                Application.Session.RemoveStore(folder)
            End If
        Next
    Catch ex As Exception
        Debug.WriteLine(ex.Message)
    End Try
End Sub
```


```csharp
private void CreateUnicodePST()
{
    string path = Environment.GetFolderPath(
        Environment.SpecialFolder.LocalApplicationData)
        + @"\Microsoft\Outlook\MyUnicodeStore.pst";
    try
    {
        Application.Session.AddStoreEx(
            path, Outlook.OlStoreType.olStoreUnicode);
        Outlook.Stores stores = Application.Session.Stores;
        foreach (Outlook.Store store in stores)
        {
            if (store.FilePath == path)
            {
               Outlook.Folder folder =
                    store.GetRootFolder() as Outlook.Folder;
               // Remove the store
               Application.Session.RemoveStore(folder);
            }
        }
    }
    catch (Exception ex)
    {
        Debug.WriteLine(ex.Message);
    }
}
```

## <a name="see-also"></a>另请参阅

- [存储](stores.md)

