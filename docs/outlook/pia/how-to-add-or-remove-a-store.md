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
# <a name="add-or-remove-a-store"></a><span data-ttu-id="209d2-102">添加或删除存储</span><span class="sxs-lookup"><span data-stu-id="209d2-102">Add or remove a store</span></span>

<span data-ttu-id="209d2-103">此代码示例展示了如何在给定配置文件中添加和删除存储。</span><span class="sxs-lookup"><span data-stu-id="209d2-103">This example shows how to add and remove a store in a given profile.</span></span>

## <a name="example"></a><span data-ttu-id="209d2-104">示例</span><span class="sxs-lookup"><span data-stu-id="209d2-104">Example</span></span>

<span data-ttu-id="209d2-105">该代码示例演示如何在指定的配置文件中，通过分别调用 [NameSpace](https://msdn.microsoft.com/library/bb623442\(v=office.15\)) 对象上的 [AddStoreEx](https://msdn.microsoft.com/library/bb610524\(v=office.15\)) 方法和 [RemoveStore](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) 方法来添加和移除存储。</span><span class="sxs-lookup"><span data-stu-id="209d2-105">This code sample shows how to add and remove a store in a specified profile, by calling the [AddStoreEx](https://msdn.microsoft.com/library/bb623442\(v=office.15\)) method and the [RemoveStore](https://msdn.microsoft.com/library/bb610524\(v=office.15\)) method respectively on the [NameSpace](https://msdn.microsoft.com/library/bb645857\(v=office.15\)) object.</span></span>

<span data-ttu-id="209d2-106">在 Outlook 中，只能以编程方式添加或删除 PST 存储。</span><span class="sxs-lookup"><span data-stu-id="209d2-106">In Outlook, you can add or remove a PST store only programmatically.</span></span> <span data-ttu-id="209d2-107">下面的代码示例添加 Unicode 存储，并将 .pst 文件置于用户 .pst 文件的默认位置上：Documents and Settings\\\<UserName\>\\Local Settings\\Application Data\\Microsoft\\Outlook。</span><span class="sxs-lookup"><span data-stu-id="209d2-107">The following code sample adds a Unicode store and places the .pst file in the default location for user .pst files: Documents and Settings\\\<UserName\>\\Local Settings\\Application Data\\Microsoft\\Outlook.</span></span> <span data-ttu-id="209d2-108">此代码示例使用 Environment.SpecialFolder.LocalApplicationData，检索“本地设置”文件夹下“应用程序数据”文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="209d2-108">The code sample uses Environment.SpecialFolder.LocalApplicationData to retrieve the path to the Application Data folder under the Local Settings folder.</span></span> <span data-ttu-id="209d2-109">添加存储后，此代码示例便会删除存储。</span><span class="sxs-lookup"><span data-stu-id="209d2-109">Once the store has been added, the code sample removes the store.</span></span> <span data-ttu-id="209d2-110">因为 **RemoveStore** 方法要求 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象移除 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象，所以它枚举 [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) 集合来查找刚才根据 **Store** 对象的 [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) 属性添加的 **Store** 对象。</span><span class="sxs-lookup"><span data-stu-id="209d2-110">Because the **RemoveStore** method requires a [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) object to remove the [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) object, it enumerates the [Stores](https://msdn.microsoft.com/library/bb622944\(v=office.15\)) collection to find the **Store** object that has just been added based on the [FilePath](https://msdn.microsoft.com/library/bb646113\(v=office.15\)) property of the **Store** object.</span></span>

<span data-ttu-id="209d2-p102">**RemoveStore** 仅从当前配置文件中删除存储，不会从文件系统中删除 .pst 文件。</span><span class="sxs-lookup"><span data-stu-id="209d2-p102">**RemoveStore** only removes the store from the current profile. It does not delete the .pst file from the file system.</span></span>

<span data-ttu-id="209d2-113">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="209d2-113">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="209d2-114">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="209d2-114">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="209d2-115">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="209d2-115">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="209d2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="209d2-116">See also</span></span>

- [<span data-ttu-id="209d2-117">存储</span><span class="sxs-lookup"><span data-stu-id="209d2-117">Stores</span></span>](stores.md)

