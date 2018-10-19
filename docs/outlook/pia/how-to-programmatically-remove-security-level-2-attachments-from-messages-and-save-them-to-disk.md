---
title: 以编程方式删除邮件的安全级别 2 附件，并将它们保存到磁盘中
TOCTitle: Programmatically remove security level 2 attachments from messages and save them to disk
ms:assetid: fb63e505-a243-40a5-919d-e4fe914af3f9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184657(v=office.15)
ms:contentKeyID: 55119822
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 3646ff17a6200a6b46b7796537a40e7bdab40781
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406594"
---
# <a name="programmatically-remove-security-level-2-attachments-from-messages-and-save-them-to-disk"></a>以编程方式删除邮件的安全级别 2 附件，并将它们保存到磁盘中

此代码示例展示了如何删除电子邮件的安全级别 2 附件，并将它们保存到磁盘中以供打开。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

Outlook 保护用户免遭恶意代码的危害，这些代码通过具有特定文件扩展名（如 .exe 或 .bat）的电子邮件附件进行传输。 这些特定附件默认会被拦截，并被标识为级别 1 附件。 级别 2 附件包含恶意代码的可能性较小，但用户无法直接从电子邮件中打开级别 2 附件。 必须先将级别 2 附件保存到磁盘中。

使用 [Attachment](https://msdn.microsoft.com/library/bb609285\(v=office.15\)) 对象的 [SaveAsFile(String)](https://msdn.microsoft.com/library/bb624311\(v=office.15\)) 方法，可以将附件保存到磁盘中。 在下面的代码示例中，RemoveAttachmentsAndSaveToDisk 先从文件夹内的邮件项中删除所有大于指定大小的级别 2 附件。 具体是通过枚举 [Attachments](https://msdn.microsoft.com/library/bb646211\(v=office.15\)) 集合中每个 **Attachment** 对象的 [Type](https://msdn.microsoft.com/library/bb609277\(v=office.15\)) 属性，并删除等于 [olByValue](https://msdn.microsoft.com/library/bb623448\(v=office.15\)) 的附件。 然后，RemoveAttachmentsAndSaveToDisk 使用 **SaveAsFile** 方法保存已删除的附件。

> [!NOTE] 
> Outlook 中的集合是线性的。 使用 [Index](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachment.index?view=outlook-pia) 运算符引用 **Attachments**[1] 至 **Attachments**[n]，其中 n 表示 [Count](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachments.count?view=outlook-pia) 属性的值。
> 
> 不能使用 **foreach** 语句来移除集合中的项目。而是应使用 **Index** 运算符来获取集合中的第一个项目，并删除该项目。然后使用 **while** 语句来确定您何时删除了集合中适当数目的项目。这将确保您循环访问了集合中正确数目的项目。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void RemoveAttachmentsAndSaveToDisk(string path,
    Outlook.Folder folder, int size)
{
    Outlook.Items attachItems;
    Outlook.Attachment attachment;
    Outlook.Attachments attachments;
    int byValueCount;
    int removeCount;
    bool saveMessage;
    try
    {
        // The restriction will find all items that
        // have attachments and MessageClass = IPM.Note.
        string filter = "@SQL=" + "\""
            + "urn:schemas:httpmail:hasattachment"
            + "\"" + " = True" + " AND " + "\""
            + "https://schemas.microsoft.com/mapi/proptag/0x001A001E"
            + "\"" + " = 'IPM.Note'";
        attachItems = folder.Items.Restrict(filter);
        foreach (Outlook.MailItem mail in attachItems)
        {
            saveMessage = false;
            byValueCount = 0;
            attachments = mail.Attachments;
            // Obtain the count of ByValue attachments.
            foreach (Outlook.Attachment attach in attachments)
            {
                if (attach.Size > size
                    & attach.Type ==
                    Outlook.OlAttachmentType.olByValue)
                {
                    byValueCount = byValueCount + 1;
                }
            }
            if (byValueCount > 0)
            {
                // removeCount is number of attachments to remove.
                removeCount = attachments.Count - byValueCount;
                while (mail.Attachments.Count != removeCount)
                {
                    // Use indexer to obtain 
                    // first attachment in collection.
                    attachment = mail.Attachments[1];
                    // You can refine this code to save 
                    // separate copies of attachments 
                    // with the same name.
                    attachment.SaveAsFile(path + @"\"
                        + attachment.FileName);
                    attachment.Delete();
                    if (saveMessage != true)
                    {
                        saveMessage = true;
                    }
                }
                if (saveMessage)
                {
                    mail.Save();
                }
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

- [附件](attachments.md)

