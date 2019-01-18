---
title: 访问在文件夹中存储为隐藏消息的解决方案专用数据
TOCTitle: Access solution-specific data stored as a hidden message in a folder
ms:assetid: bacf0562-1026-4c3b-87b0-4eaad5033592
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623414(v=office.15)
ms:contentKeyID: 55119861
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e4a0a686327bb43b07773b149831107f51fcb4fa
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708142"
---
# <a name="access-solution-specific-data-stored-as-a-hidden-message-in-a-folder"></a><span data-ttu-id="314f8-102">访问在文件夹中存储为隐藏消息的解决方案专用数据</span><span class="sxs-lookup"><span data-stu-id="314f8-102">Access solution-specific data stored as a hidden message in a folder</span></span>

<span data-ttu-id="314f8-103">该示例演示如何使用 [StorageItem](https://msdn.microsoft.com/library/bb623436\(v=office.15\)) 对象来检索文件夹中存储为特定邮件类别的隐藏邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="314f8-103">This example shows how to use the [StorageItem](https://msdn.microsoft.com/library/bb623436\(v=office.15\)) object to retrieve data that is stored as a hidden message of a specific message class in a folder.</span></span>

## <a name="example"></a><span data-ttu-id="314f8-104">示例</span><span class="sxs-lookup"><span data-stu-id="314f8-104">Example</span></span>

<span data-ttu-id="314f8-p101">**StorageItem** 对象通常用于隐藏无法以编程方式显示的解决方案特定数据。在 Exchange 环境中， **StorageItem** 对象用于漫游解决方案设置并确保这些设置可联机和脱机使用。可以将自定义邮件类别分配给 **StorageItem** 对象，或按主题识别对象。</span><span class="sxs-lookup"><span data-stu-id="314f8-p101">The **StorageItem** object is typically used to hide solution-specific data that cannot be displayed programmatically. In an Exchange environment, the **StorageItem** object is used to roam solution settings and ensure that these settings are available online and offline. You can assign a custom message class to the **StorageItem** object, or identify the object by subject.</span></span>

<span data-ttu-id="314f8-108">下面的代码示例检索"日历"文件夹中存储为邮件类别等于 IPM.Configuration.WorkHours 的隐藏邮件的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="314f8-108">The following code sample retrieves the XML data that is stored as a hidden message in the Calendar folder with the message class equal to IPM.Configuration.WorkHours.</span></span>

<span data-ttu-id="314f8-p102">[PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象返回 XML 作为包含 XML 的字节流而非字符串表示形式的对象。该代码示例使用 **System.Text.Encoding.Ascii.GetString** 将字节流转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="314f8-p102">The [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object returns the XML as an object that contains a byte stream rather than a string representation of the XML. The code sample uses **System.Text.Encoding.Ascii.GetString** to convert the byte stream to a string.</span></span>

<span data-ttu-id="314f8-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="314f8-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="314f8-112">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="314f8-112">The **Imports** or **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="314f8-113">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="314f8-113">The following lines of code show how to do the import and assignment in Visual Basic and C\#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Function GetWorkHoursXML() As String
    Try
        Dim storage As Outlook.StorageItem = _
            Application.Session.GetDefaultFolder( _
            Outlook.OlDefaultFolders.olFolderCalendar).GetStorage( _
            "IPM.Configuration.WorkHours", _
            Outlook.OlStorageIdentifierType.olIdentifyByMessageClass)
        Dim pa As Outlook.PropertyAccessor = storage.PropertyAccessor
        ' PropertyAccessor will return a byte array for this property
        Dim rawXmlBytes As Byte() = CType(pa.GetProperty( _
            "https://schemas.microsoft.com/mapi/proptag/0x7C080102"), _
            Byte())
        ' Use Encoding to convert the array to a string
        Return System.Text.Encoding.ASCII.GetString(rawXmlBytes)
    Catch
        Return String.Empty
    End Try
End Function
```

```csharp
private string GetWorkHoursXML()
{
    try
    {
        Outlook.StorageItem storage =
            Application.Session.GetDefaultFolder(
            Outlook.OlDefaultFolders.olFolderCalendar).GetStorage(
            "IPM.Configuration.WorkHours",
            Outlook.OlStorageIdentifierType.olIdentifyByMessageClass);
        Outlook.PropertyAccessor pa = storage.PropertyAccessor;
        // PropertyAccessor will return a byte array for this property
        byte[] rawXmlBytes = (byte[])pa.GetProperty(
            "https://schemas.microsoft.com/mapi/proptag/0x7C080102");
        // Use Encoding to convert the array to a string
        return System.Text.Encoding.ASCII.GetString(rawXmlBytes);
    }
    catch
    {
        return string.Empty;
    }
}
```


## <a name="see-also"></a><span data-ttu-id="314f8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="314f8-114">See also</span></span>

- [<span data-ttu-id="314f8-115">文件夹</span><span class="sxs-lookup"><span data-stu-id="314f8-115">Folders</span></span>](folders.md)

