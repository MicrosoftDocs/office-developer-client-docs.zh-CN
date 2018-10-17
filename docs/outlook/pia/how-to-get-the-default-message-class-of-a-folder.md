---
title: 获取文件夹的默认邮件类别
TOCTitle: Get the default message class of a folder
ms:assetid: 1c5faefd-b180-4114-a955-3fc524210317
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184594(v=office.15)
ms:contentKeyID: 55119860
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: c03e0737a3dd2e74f39d90ffbac31bb134d16348
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407217"
---
# <a name="get-the-default-message-class-of-a-folder"></a>获取文件夹的默认邮件类别

此代码示例展示了如何使用 [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) 属性获取文件夹的默认邮件类别。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

若要获取文件夹的默认邮件类别，请使用 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的 **DefaultMessageClass** 属性。 例如，如果 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象包含 **DefaultMessageClass** 的 IPM.Contact，意味着它代表“联系人”文件夹。 但是，如果该文件夹以自定义窗体或替换窗体作为默认窗体，则必须使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象来确定默认窗体的邮件类别。 **DefaultMessageClass** 属性不返回文件夹的默认表单的邮件类别。

在下面的代码示例中，GetDefaultMessageClass 过程使用 **PropertyAccessor** 确定文件夹的默认表单。 如果找不到文件夹属性 **PR\_DEF\_POST\_MSGCLASS** [(PidTagDefaultPostMessageClass)](https://msdn.microsoft.com/library/cc815305\(v=office.15\))，且 Outlook 引发错误，**try…catch** 块便会返回 **Folder** 的 **DefaultMessageClass** 属性。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private string GetDefaultMessageClass(Outlook.Folder folder)
{
    if (folder == null)
        throw new ArgumentNullException();
    try
    {
        const string PR_DEF_POST_MSGCLASS =
            @"https://schemas.microsoft.com/mapi/proptag/0x36E5001E";
        string messageClass =
            folder.PropertyAccessor.GetProperty(
            PR_DEF_POST_MSGCLASS).ToString();
        return messageClass;
    }
    catch
    {
        return folder.DefaultMessageClass;
    }
}
```

## <a name="see-also"></a>另请参阅

- [文件夹](folders.md)

