---
title: 使用邮件模板创建邮件项
TOCTitle: Create a mail item by using a message template
ms:assetid: 7d1ffc3b-d1a7-46d1-adb9-ac41e67f626a
ms:mtpsurl: https://msdn.microsoft.com/library/Bb623026(v=office.15)
ms:contentKeyID: 55119862
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 074a3eb7b83e4556b41549d18b81c97b96db1e6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407098"
---
# <a name="create-a-mail-item-by-using-a-message-template"></a><span data-ttu-id="f47fd-102">使用邮件模板创建邮件项</span><span class="sxs-lookup"><span data-stu-id="f47fd-102">Create a mail item by using a message template</span></span>

<span data-ttu-id="f47fd-103">此示例使用 [CreateItemFromTemplate](https://msdn.microsoft.com/library/bb611329\(v=office.15\)) 方法创建邮件项。</span><span class="sxs-lookup"><span data-stu-id="f47fd-103">This example creates a mail item by using the [CreateItemFromTemplate](https://msdn.microsoft.com/library/bb611329\(v=office.15\)) method.</span></span>

## <a name="example"></a><span data-ttu-id="f47fd-104">示例</span><span class="sxs-lookup"><span data-stu-id="f47fd-104">Example</span></span>

<span data-ttu-id="f47fd-105">该代码示例打开 Ivy.oft 模板文件，分配一个主题，然后将邮件存入"草稿"文件夹。</span><span class="sxs-lookup"><span data-stu-id="f47fd-105">This code sample opens the Ivy.oft template file, assigns a subject, and then saves the message to the Drafts folder.</span></span>

<span data-ttu-id="f47fd-p101">如果您在磁盘上存储了一个希望用作邮件模板的 Outlook 窗体模板文件 (.oft)，则 **CreateItemFromTemplate** 方法很有用。此模板文件可以包含您希望包括在邮件中的具有预设格式的文本、信纸或图像。但是，如果模板文件包含的代码位于窗体之后，则窗体代码将不运行。</span><span class="sxs-lookup"><span data-stu-id="f47fd-p101">The **CreateItemFromTemplate** method is useful if you have an Outlook form template file (.oft) stored on disk that you want to use as a message template. The template file can contain preformatted text, stationery, or images that you want to include in the message. However, if the template file contains code behind the form, the form code will not run.</span></span>

<span data-ttu-id="f47fd-109">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="f47fd-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="f47fd-110">不得将 **Imports** 或 **using** 语句直接添加到此代码示例中的函数前面，这两个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="f47fd-110">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="f47fd-111">下面几段代码行展示了如何在 Visual Basic 和 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="f47fd-111">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub CreateItemFromTemplate()
    Dim folder As Outlook.Folder = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderDrafts), Outlook.Folder)
    Dim mail As Outlook.MailItem = _
        CType(Application.CreateItemFromTemplate( _
        "c:\ivy.oft", folder), Outlook.MailItem)
    mail.Subject = "Congratulations"
    mail.Save()
End Sub
```


```csharp
private void CreateItemFromTemplate()
{
    Outlook.Folder folder =
        Application.Session.GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderDrafts) as Outlook.Folder;
    Outlook.MailItem mail =
        Application.CreateItemFromTemplate(
        @"c:\ivy.oft", folder) as Outlook.MailItem;
    mail.Subject = "Congratulations";
    mail.Save();
}
```

## <a name="see-also"></a><span data-ttu-id="f47fd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f47fd-112">See also</span></span>

- [<span data-ttu-id="f47fd-113">邮件</span><span class="sxs-lookup"><span data-stu-id="f47fd-113">Mail</span></span>](mail.md)

