---
title: 显示有效资源管理器中的选定项
TOCTitle: Display selected items in the active Explorer
ms:assetid: 31bb217b-8b45-4b50-942e-b6c2a7f13c83
ms:mtpsurl: https://msdn.microsoft.com/library/Dn292517(v=office.15)
ms:contentKeyID: 55119844
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: d2599aff01afc7cc02797210a260befdfb72be33
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405502"
---
# <a name="display-selected-items-in-the-active-explorer"></a><span data-ttu-id="b03a6-102">显示有效资源管理器中的选定项</span><span class="sxs-lookup"><span data-stu-id="b03a6-102">Display selected items in the active Explorer</span></span>

<span data-ttu-id="b03a6-103">此代码示例展示了如何使用 OutlookItem 帮助程序类，便捷地显示有效资源管理器窗口中的所有选定项。</span><span class="sxs-lookup"><span data-stu-id="b03a6-103">This example shows how to use the OutlookItem helper class to conveniently display all the items selected in the active Explorer window.</span></span>

## <a name="example"></a><span data-ttu-id="b03a6-104">示例</span><span class="sxs-lookup"><span data-stu-id="b03a6-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="b03a6-105">下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。</span><span class="sxs-lookup"><span data-stu-id="b03a6-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="b03a6-106">[Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) 对象包含有效 Outlook 资源管理器中的一组当前选定 Outlook 项。</span><span class="sxs-lookup"><span data-stu-id="b03a6-106">The [Selection](https://msdn.microsoft.com/library/bb612099\(v=office.15\)) object contains the set of Outlook items currently selected in the active Outlook explorer.</span></span> <span data-ttu-id="b03a6-107">[ActiveExplorer()](https://msdn.microsoft.com/library/bb647410\(v=office.15\)) 表示的有效资源管理器和一组选定项都未指明选定项的类型。</span><span class="sxs-lookup"><span data-stu-id="b03a6-107">Neither the active explorer, represented by [ActiveExplorer()](https://msdn.microsoft.com/library/bb647410\(v=office.15\)), nor the set of selected items indicates the type of the items that are selected.</span></span> <span data-ttu-id="b03a6-108">通常情况下，必须先标识项类型，然后调用相应类型的专用 **Display** 方法。</span><span class="sxs-lookup"><span data-stu-id="b03a6-108">Normally, you would have to first identify the item type and then call the specific **Display** method for that type.</span></span> <span data-ttu-id="b03a6-109">因为 **Display** 方法对所有 Outlook 项对象都是通用的，且 OutlookItem 帮助程序类包含此方法，所以可利用帮助程序类，具体方法是声明 OutlookItem 对象 myItem 的实例，并使用 myItem.Display 显示所有选定项。</span><span class="sxs-lookup"><span data-stu-id="b03a6-109">Because the **Display** method is common to all Outlook items objects and the OutlookItem helper class includes this method, you can take advantage of the helper class, by declaring an instance of the OutlookItem object, myItem, and using myItem.Display to display each item in the selection.</span></span> <span data-ttu-id="b03a6-110">若要了解如何实现 OutlookItem 帮助程序类，可访问[创建用于访问常见 Outlook 项成员的帮助程序类](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)。</span><span class="sxs-lookup"><span data-stu-id="b03a6-110">You can see the implementation of the OutlookItem helper class in [Create a Helper Class to Access Common Outlook Item Members](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)</span></span>

<span data-ttu-id="b03a6-111">如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。</span><span class="sxs-lookup"><span data-stu-id="b03a6-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="b03a6-112">不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。</span><span class="sxs-lookup"><span data-stu-id="b03a6-112">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="b03a6-113">下面的代码行展示了如何在 C\# 中执行导入和分配操作。</span><span class="sxs-lookup"><span data-stu-id="b03a6-113">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DisplaySelectedItems()
{
    Outlook.Selection selection =
        Application.ActiveExplorer().Selection;
    for (int i = 1; i <= selection.Count; i++)
    {
        OutlookItem myItem = new OutlookItem(selection[i]);
        myItem.Display();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="b03a6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b03a6-114">See also</span></span>

- [<span data-ttu-id="b03a6-115">创建用于访问常见 Outlook 项成员的帮助程序类员</span><span class="sxs-lookup"><span data-stu-id="b03a6-115">Create a Helper class to access common Outlook item members</span></span>](how-to-create-a-helper-class-to-access-common-outlook-item-members.md)
- [<span data-ttu-id="b03a6-116">常规 Outlook 项</span><span class="sxs-lookup"><span data-stu-id="b03a6-116">General Outlook items</span></span>](general-outlook-items.md)

