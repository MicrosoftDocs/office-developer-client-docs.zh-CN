---
title: 确保文件夹级查询支持自定义项属性
TOCTitle: Ensure that custom item properties are supported in folder-level queries
ms:assetid: 02cf14c6-ee1b-4e04-a865-32adaac13f9b
ms:mtpsurl: https://msdn.microsoft.com/library/Bb608929(v=office.15)
ms:contentKeyID: 55119863
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9fcba2648988d2de3c208079d2845e2cb4c2f549
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319087"
---
# <a name="ensure-that-custom-item-properties-are-supported-in-folder-level-queries"></a>确保文件夹级查询支持自定义项属性

该示例演示如何确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。

## <a name="example"></a>示例

该代码示例演示如何使用 [UserDefinedProperties](https://msdn.microsoft.com/library/bb643868\(v=office.15\)) 对象和 [UserDefinedProperty](https://msdn.microsoft.com/library/bb646064\(v=office.15\)) 对象确保在向项目类型中添加自定义属性时，也会将该属性添加到文件夹中，以便在文件夹级别查询该自定义属性。

通过对 [UserProperties](https://msdn.microsoft.com/library/bb611428\(v=office.15\)) 集合使用 [Add](https://msdn.microsoft.com/library/bb611522\(v=office.15\)) 方法向项添加自定义属性时，可将 *AddToFolderFields* 参数指定为 **True**，从而将相应属性添加到文件夹。 但是，由于开发人员错误或用户操作（如通过 Outlook 字段选择器删除自定义属性或将项目移动到其他文件夹），自定义属性可能无法添加到所需文件夹。 因此，使用该自定义属性的 [Items](https://msdn.microsoft.com/library/bb646289\(v=office.15\)) 对象的 [Find](https://msdn.microsoft.com/library/bb612531\(v=office.15\)) 方法和 [Restrict](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 方法将失败。 通过使用 **UserDefinedProperties** 对象，可以测试文件夹中是否存在您的自定义属性，如果这些属性不存在或已被删除，则添加这些自定义属性。

若要在文件夹中保留由 **UserDefinedProperty** 对象表示的自定义属性，必须在项目中使用同名来保存自定义属性。在文件夹的 **UserDefinedProperty** 对象中存储值没有意义。必须将项目的 **UserProperties** 集合设置为访问您要设置的 [UserProperty](https://msdn.microsoft.com/library/bb623119\(v=office.15\)) 对象，然后对 **UserProperty** 对象设置值。务必要对项目调用 **Save** 方法，以保存更改。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。 下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。

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

## <a name="see-also"></a>另请参阅

- [文件夹](folders.md)

