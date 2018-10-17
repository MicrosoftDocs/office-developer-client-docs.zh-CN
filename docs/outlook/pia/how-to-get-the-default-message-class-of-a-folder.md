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
# <a name="get-the-default-message-class-of-a-folder"></a><span data-ttu-id="fc04a-102">获取文件夹的默认邮件类别</span><span class="sxs-lookup"><span data-stu-id="fc04a-102">Get the default message class of a folder</span></span>

<span data-ttu-id="fc04a-103">此代码示例展示了如何使用 [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) 属性获取文件夹的默认邮件类别。</span><span class="sxs-lookup"><span data-stu-id="fc04a-103">This example shows how to use the [DefaultMessageClass](https://msdn.microsoft.com/library/bb646541\(v=office.15\)) property to obtain the default message class of a folder.</span></span>

## <a name="example"></a><span data-ttu-id="fc04a-104">示例</span><span class="sxs-lookup"><span data-stu-id="fc04a-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="fc04a-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="fc04a-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="fc04a-106">若要获取文件夹的默认邮件类别，请使用 [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) 对象的 **DefaultMessageClass** 属性。</span><span class="sxs-lookup"><span data-stu-id="fc04a-106">To obtain the default message class for a folder, use the **DefaultMessageClass** property of the [MAPIFolder](https://msdn.microsoft.com/library/bb624369\(v=office.15\)) object.</span></span> <span data-ttu-id="fc04a-107">例如，如果 [Folder](https://msdn.microsoft.com/library/bb645774\(v=office.15\)) 对象包含 **DefaultMessageClass** 的 IPM.Contact，意味着它代表“联系人”文件夹。</span><span class="sxs-lookup"><span data-stu-id="fc04a-107">For example, a Folder object that has a DefaultMessageClass of   means that it represents a Contact folder.</span></span> <span data-ttu-id="fc04a-108">但是，如果该文件夹以自定义窗体或替换窗体作为默认窗体，则必须使用 [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) 对象来确定默认窗体的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="fc04a-108">However, if the folder has a custom form or a replacement form as a default form, you must use the [PropertyAccessor](https://msdn.microsoft.com/library/bb646034\(v=office.15\)) object to determine the message class of the default form.</span></span> <span data-ttu-id="fc04a-109">**DefaultMessageClass** 属性不返回文件夹的默认表单的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="fc04a-109">The **DefaultMessageClass** property does not return the message class of the default form for the folder.</span></span>

<span data-ttu-id="fc04a-110">在下面的代码示例中，GetDefaultMessageClass 过程使用 **PropertyAccessor** 确定文件夹的默认表单。</span><span class="sxs-lookup"><span data-stu-id="fc04a-110">In the following code example, the   procedure uses the PropertyAccessor to determine the default form of a folder.</span></span> <span data-ttu-id="fc04a-111">如果找不到文件夹属性 **PR\_DEF\_POST\_MSGCLASS** [(PidTagDefaultPostMessageClass)](https://msdn.microsoft.com/library/cc815305\(v=office.15\))，且 Outlook 引发错误，**try…catch** 块便会返回 **Folder** 的 **DefaultMessageClass** 属性。</span><span class="sxs-lookup"><span data-stu-id="fc04a-111">If the folder property PR_DEF_POST_MSGCLASS (PidTagDefaultPostMessageClass) is not found and Outlook raises an error, the try…catch block returns the DefaultMessageClass property for the Folder.</span></span>

<span data-ttu-id="fc04a-112">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="fc04a-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="fc04a-113">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="fc04a-113">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="fc04a-114">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="fc04a-114">The following line of code shows how to do the import and assignment in C#.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="fc04a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc04a-115">See also</span></span>

- [<span data-ttu-id="fc04a-116">文件夹</span><span class="sxs-lookup"><span data-stu-id="fc04a-116">Folders</span></span>](folders.md)

