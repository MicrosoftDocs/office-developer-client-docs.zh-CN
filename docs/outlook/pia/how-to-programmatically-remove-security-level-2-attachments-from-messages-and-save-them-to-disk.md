---
title: 以编程方式删除邮件的安全级别 2 附件，并将它们保存到磁盘中
TOCTitle: Programmatically remove security level 2 attachments from messages and save them to disk
ms:assetid: fb63e505-a243-40a5-919d-e4fe914af3f9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184657(v=office.15)
ms:contentKeyID: 55119822
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 135f07f4bd3bdc36cee8547106b955b967150df8
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28706931"
---
# <a name="programmatically-remove-security-level-2-attachments-from-messages-and-save-them-to-disk"></a><span data-ttu-id="f7a27-102">以编程方式删除邮件的安全级别 2 附件，并将它们保存到磁盘中</span><span class="sxs-lookup"><span data-stu-id="f7a27-102">Programmatically remove security level 2 attachments from messages and save them to disk</span></span>

<span data-ttu-id="f7a27-103">此代码示例展示了如何删除电子邮件的安全级别 2 附件，并将它们保存到磁盘中以供打开。</span><span class="sxs-lookup"><span data-stu-id="f7a27-103">This example shows how to remove security level 2 attachments from email messages and save them to a disk, from where they can be opened.</span></span>

## <a name="example"></a><span data-ttu-id="f7a27-104">示例</span><span class="sxs-lookup"><span data-stu-id="f7a27-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="f7a27-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="f7a27-105">The following code example is an excerpt from [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span></span>

<span data-ttu-id="f7a27-106">Outlook 保护用户免遭恶意代码的危害，这些代码通过具有特定文件扩展名（如 .exe 或 .bat）的电子邮件附件进行传输。</span><span class="sxs-lookup"><span data-stu-id="f7a27-106">Outlook protects users from malicious code transported via email attachments that have certain file extensions such as .exe or .bat.</span></span> <span data-ttu-id="f7a27-107">这些特定附件默认会被拦截，并被标识为级别 1 附件。</span><span class="sxs-lookup"><span data-stu-id="f7a27-107">Those particular attachments are blocked by default and identified as Level 1 attachments.</span></span> <span data-ttu-id="f7a27-108">级别 2 附件包含恶意代码的可能性较小，但用户无法直接从电子邮件中打开级别 2 附件。</span><span class="sxs-lookup"><span data-stu-id="f7a27-108">Level 2 attachments have a lesser chance of containing malicious code, but users cannot open a Level 2 attachment directly from an email message.</span></span> <span data-ttu-id="f7a27-109">必须先将级别 2 附件保存到磁盘中。</span><span class="sxs-lookup"><span data-stu-id="f7a27-109">A Level 2 attachment must first be saved to a disk.</span></span>

<span data-ttu-id="f7a27-110">使用 [Attachment](https://msdn.microsoft.com/library/bb609285\(v=office.15\)) 对象的 [SaveAsFile(String)](https://msdn.microsoft.com/library/bb624311\(v=office.15\)) 方法，可以将附件保存到磁盘中。</span><span class="sxs-lookup"><span data-stu-id="f7a27-110">By using the [SaveAsFile(String)](https://msdn.microsoft.com/library/bb624311\(v=office.15\)) method in the [Attachment](https://msdn.microsoft.com/library/bb609285\(v=office.15\)) object, you can save attachments to a disk.</span></span> <span data-ttu-id="f7a27-111">在下面的代码示例中，RemoveAttachmentsAndSaveToDisk 先从文件夹内的邮件项中删除所有大于指定大小的级别 2 附件。</span><span class="sxs-lookup"><span data-stu-id="f7a27-111">In the following code example, RemoveAttachmentsAndSaveToDisk first removes from mail items in a folder all Level 2 attachments that are greater than a specified size.</span></span> <span data-ttu-id="f7a27-112">具体是通过枚举 [Attachments](https://msdn.microsoft.com/library/bb646211\(v=office.15\)) 集合中每个 **Attachment** 对象的 [Type](https://msdn.microsoft.com/library/bb609277\(v=office.15\)) 属性，并删除等于 [olByValue](https://msdn.microsoft.com/library/bb623448\(v=office.15\)) 的附件。</span><span class="sxs-lookup"><span data-stu-id="f7a27-112">This is done by enumerating the [Type](https://msdn.microsoft.com/library/bb609277\(v=office.15\)) property of each **Attachment** object in the [Attachments](https://msdn.microsoft.com/library/bb646211\(v=office.15\)) collection and removing the ones that are equal to [olByValue](https://msdn.microsoft.com/library/bb623448\(v=office.15\)).</span></span> <span data-ttu-id="f7a27-113">然后，RemoveAttachmentsAndSaveToDisk 使用 **SaveAsFile** 方法保存已删除的附件。</span><span class="sxs-lookup"><span data-stu-id="f7a27-113">RemoveAttachmentsAndSaveToDisk then saves the removed attachment by using the **SaveAsFile** method.</span></span>

> [!NOTE] 
> <span data-ttu-id="f7a27-114">Outlook 中的集合是线性的。</span><span class="sxs-lookup"><span data-stu-id="f7a27-114">Collections in Outlook are linear.</span></span> <span data-ttu-id="f7a27-115">使用 [Index](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachment.index?view=outlook-pia) 运算符引用 **Attachments**[1] 至 **Attachments**[n]，其中 n 表示 [Count](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachments.count?view=outlook-pia) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f7a27-115">Use the [Index](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachment.index?view=outlook-pia) operator to reference **Attachments**[1] to **Attachments**[n], where n represents the value of the [Count](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.attachments.count?view=outlook-pia) property.</span></span>
> 
> <span data-ttu-id="f7a27-p104">不能使用 **foreach** 语句来移除集合中的项目。而是应使用 **Index** 运算符来获取集合中的第一个项目，并删除该项目。然后使用 **while** 语句来确定您何时删除了集合中适当数目的项目。这将确保您循环访问了集合中正确数目的项目。</span><span class="sxs-lookup"><span data-stu-id="f7a27-p104">You cannot use a **foreach** statement to remove items in a collection. Instead, use an **Index** operator to obtain the first item in the collection, and then delete the item. Then use a **while** statement to determine when you have deleted the appropriate number of items in the collection. This will ensure that you have iterated over the correct number of items in the collection.</span></span>

<span data-ttu-id="f7a27-120">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="f7a27-120">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the Outlook variable when you import the **Microsoft.Office.Interop.Outlook** namespace.</span></span> <span data-ttu-id="f7a27-121">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="f7a27-121">The **using** statement must not occur directly before the functions in the code example but must be added before the public Class declaration.</span></span> <span data-ttu-id="f7a27-122">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="f7a27-122">The following line of code shows how to do the import and assignment in C\#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f7a27-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7a27-123">See also</span></span>

- [<span data-ttu-id="f7a27-124">附件</span><span class="sxs-lookup"><span data-stu-id="f7a27-124">Attachments</span></span>](attachments.md)

