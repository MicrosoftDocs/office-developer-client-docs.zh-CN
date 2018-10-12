---
title: 确保文件夹级查询支持自定义项属性
TOCTitle: Ensure that custom item properties are supported in folder-level queries
ms:assetid: 02cf14c6-ee1b-4e04-a865-32adaac13f9b
ms:mtpsurl: https://msdn.microsoft.com/library/Bb608929(v=office.15)
ms:contentKeyID: 55119863
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 659919de8eeb17e675ed67f3b777f67b04f13b54
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406937"
---
# <a name="ensure-that-custom-item-properties-are-supported-in-folder-level-queries"></a><span data-ttu-id="b2ffe-102">确保文件夹级查询支持自定义项属性</span><span class="sxs-lookup"><span data-stu-id="b2ffe-102">Ensure that custom item properties are supported in folder-level queries</span></span>

<span data-ttu-id="b2ffe-103">该示例演示如何确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-103">This example shows how to ensure that when you add a custom property to an item type, you also add the property to the folder so that you can query on that custom property at the folder level.</span></span>

## <a name="example"></a><span data-ttu-id="b2ffe-104">示例</span><span class="sxs-lookup"><span data-stu-id="b2ffe-104">Example</span></span>

<span data-ttu-id="b2ffe-105">该代码示例演示如何使用 [UserDefinedProperties](https://msdn.microsoft.com/library/bb643868\(v=office.15\)) 对象和 [UserDefinedProperty](https://msdn.microsoft.com/library/bb646064\(v=office.15\)) 对象确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-105">This code sample shows how to use the [UserDefinedProperties](https://msdn.microsoft.com/library/bb643868\(v=office.15\)) object and the [UserDefinedProperty](https://msdn.microsoft.com/library/bb646064\(v=office.15\)) object to ensure that when you add a custom property to an item type, you also add the property to the folder so that you can query on that custom property at the folder level.</span></span>

<span data-ttu-id="b2ffe-106">通过对 [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) 集合使用 [Add](https://msdn.microsoft.com/library/bb611522\(v=office.15\)) 方法向项添加自定义属性时，可将 *AddToFolderFields* 参数指定为 **True**，从而将相应属性添加到文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-106">When you use the [Add](https://msdn.microsoft.com/library/bb611522\(v=office.15\)) method on the [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) collection to add a custom property to an item, you can specify the  *AddToFolderFields* parameter as **True** to add the property to the folder.</span></span> <span data-ttu-id="b2ffe-107">但是，由于开发人员错误或用户操作（如通过 Outlook 字段选择器删除自定义属性或将项目移动到其他文件夹），自定义属性可能无法添加到所需文件夹。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-107">However, the custom property might not get added to the desired folderbecause of developer error or a user action, such as removing the custom property through the Outlook Field Chooser or moving the item to another folder.</span></span> <span data-ttu-id="b2ffe-108">因此，使用该自定义属性的 [Items](https://msdn.microsoft.com/library/bb646289\(v=office.15\)) 对象的 [Find](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) 方法和 [Restrict](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 方法将失败。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-108">Consequently, the [Find](https://msdn.microsoft.com/library/bb646289\(v=office.15\)) method and the [Restrict](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) method of the [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) object that uses that custom property will fail.</span></span> <span data-ttu-id="b2ffe-109">通过使用 **UserDefinedProperties** 对象，可以测试文件夹中是否存在您的自定义属性，如果这些属性不存在或已被删除，则添加这些自定义属性。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-109">By using the **UserDefinedProperties** object, you can test whether your custom properties exist in the folder, and add the custom properties if they do not exist or if they have been removed.</span></span>

<span data-ttu-id="b2ffe-p102">若要在文件夹中保留由 **UserDefinedProperty** 对象表示的自定义属性，必须在项目中使用同名来保存自定义属性。在文件夹的 **UserDefinedProperty** 对象中存储值没有意义。必须将项目的 **UserProperties** 集合设置为访问您要设置的 [UserProperty](https://msdn.microsoft.com/library/bb623119\(v=office.15\)) 对象，然后对 **UserProperty** 对象设置值。务必要对项目调用 **Save** 方法，以保存更改。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-p102">To persist a custom property represented by a **UserDefinedProperty** object in a folder, you must save the custom property with the same name in the item. Storing a value in the **UserDefinedProperty** object for the folder has no effect. You must se the item's **UserProperties** collection to access the [UserProperty](https://msdn.microsoft.com/library/bb623119\(v=office.15\)) object that you want to set, and then set the value on the **UserProperty** object. Be sure to call the **Save** method on the item to persist your changes.</span></span>

<span data-ttu-id="b2ffe-114">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-114">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b2ffe-115">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-115">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b2ffe-116">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b2ffe-116">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub DemoUserDefinedProperty()
    Dim folder As Outlook.Folder = _
        CType(Application.ActiveExplorer().CurrentFolder(), _
        Outlook.Folder)
    Dim post As Outlook.PostItem = CType( _
        folder.Items.Add("IPM.Post"), Outlook.PostItem)
    ' Add UserProperty to PostItem
    post.UserProperties.Add("ColorID", _
        Outlook.OlUserPropertyType.olText, False)
    post.UserProperties("ColorID").Value = "Green"
    post.Subject = "UserProperty Example"
    post.Save()
    Dim findPost As Outlook.PostItem
    Try
        ' Items.Find will fail unless custom property
        ' is defined in the folder
        findPost = _
            CType(folder.Items.Find("[ColorID] = 'Green'"), _
            Outlook.PostItem)
        Catch ex As Exception
            Debug.WriteLine(ex.Message)
        End Try
        ' Add ColorID field to the folder
        folder.UserDefinedProperties.Add("ColorID", _
            Outlook.OlUserPropertyType.olText)
        ' Now the find works ok
        Dim findPostOK As Outlook.PostItem
        Try
            findPostOK = _
                CType(folder.Items.Find("[ColorID] = 'Green'"), _
                Outlook.PostItem)
            If Not (findPostOK Is Nothing) Then
                Debug.WriteLine("Found PostItem")
            End If
            ' Cleanup by deleting PostItem and ColorID
            findPostOK.Delete()
            Dim userProperty As Outlook.UserDefinedProperty = _
                folder.UserDefinedProperties("ColorID")
            userProperty.Delete()
        Catch ex As Exception
            Debug.WriteLine(ex.Message)
        End Try
End Sub
```


```csharp
private void DemoUserDefinedProperty()
{
    Outlook.Folder folder =
        Application.ActiveExplorer().CurrentFolder
        as Outlook.Folder;
    Outlook.PostItem post = folder.Items.Add("IPM.Post")
        as Outlook.PostItem;
    // Add UserProperty to PostItem
    post.UserProperties.Add("ColorID",
        Outlook.OlUserPropertyType.olText,
        false, Type.Missing);
    post.UserProperties["ColorID"].Value = "Green";
    post.Subject = "UserProperty Example";
    post.Save();
    Outlook.PostItem findPost;
    try
    {
        // Items.Find will fail unless custom property
        // is defined in the folder
        findPost =
            folder.Items.Find("[ColorID] = 'Green'")
            as Outlook.PostItem;
    }
    catch (Exception ex)
    {
        Debug.WriteLine(ex.Message);
    }
     // Add ColorID field to the folder
    folder.UserDefinedProperties.Add("ColorID",
        Outlook.OlUserPropertyType.olText,
        Type.Missing, Type.Missing);
    // Now the find works ok
    Outlook.PostItem findPostOK;
    try
    {
        findPostOK =
            folder.Items.Find("[ColorID] = 'Green'")
            as Outlook.PostItem;
        if (findPostOK != null)
        {
            Debug.WriteLine("Found PostItem");
        }
        // Cleanup by deleting PostItem and ColorID
        findPostOK.Delete();
        Outlook.UserDefinedProperty userProperty =
            folder.UserDefinedProperties["ColorID"];
        userProperty.Delete();
    }
    catch (Exception ex)
    {
        Debug.WriteLine(ex.Message);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b2ffe-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2ffe-117">See also</span></span>

- [<span data-ttu-id="b2ffe-118">文件夹</span><span class="sxs-lookup"><span data-stu-id="b2ffe-118">Folders</span></span>](folders.md)

