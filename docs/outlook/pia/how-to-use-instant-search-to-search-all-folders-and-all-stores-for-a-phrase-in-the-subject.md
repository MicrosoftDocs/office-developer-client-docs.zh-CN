---
title: 使用“即时搜索”在所有文件夹和所有存储中搜索主题包含某短语的项
TOCTitle: Use instant search to search all folders and all stores for a phrase in the subject
ms:assetid: d3152bfa-6e7d-4b68-8c7e-e2e155a92b49
ms:mtpsurl: https://msdn.microsoft.com/library/Ff424478(v=office.15)
ms:contentKeyID: 55119923
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 3e6e8199df6c04ba5a78ed5611aaaf016a71226d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407014"
---
# <a name="use-instant-search-to-search-all-folders-and-all-stores-for-a-phrase-in-the-subject"></a>使用“即时搜索”在所有文件夹和所有存储中搜索主题包含某短语的项

本示例使用"即时搜索"在所有文件夹和所有存储区中搜索主题中的某个短语，并在资源管理器窗口中显示相应项目。

## <a name="example"></a>示例

> [!NOTE] 
> 下面的代码示例摘录自 [Microsoft Office Outlook 2007 应用程序编程](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)。

“即时搜索”是一项 Microsoft Outlook 功能，便于用户通过发出根据内容返回结果的查询来执行搜索。 您的查询一经处理后，即会在各种对象中返回结果，包括 [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) 对象、 [Items](https://msdn.microsoft.com/library/bb645287\(v=office.15\)) 集合和 [Search](https://msdn.microsoft.com/library/bb612611\(v=office.15\)) 对象。 您可以使用 Microsoft Windows 桌面搜索提供的高级查询语法 (AQS)，来编写使用即时搜索的代码。 AQS 是 Outlook 支持的三种查询语言之一。 它的功能很强大，但仅限于 [Explorer](https://msdn.microsoft.com/library/bb623678\(v=office.15\)) 对象的 [Search(String, OlSearchScope)](https://msdn.microsoft.com/library/bb610561\(v=office.15\)) 方法。 无法使用 AQS 限制 **Table** 或 **Item** 对象。 此外，AQS 查询返回的结果只能显示在 Outlook 用户界面中。 下表列出了 Outlook 支持的三种查询语言；不过，本主题介绍的是仅使用 AQS。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>查询语言</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AQS</p></td>
<td><p>AQS 由 Windows 桌面搜索使用，是针对 Outlook 中的即时搜索功能的查询语言。</p></td>
</tr>
<tr class="even">
<td><p>DASL</p></td>
<td><p>DAV 搜索和定位 (DASL) 查询语言基于 Outlook 中 DASL 的 Microsoft Exchange 实现。DASL 可用于在 <b>Table</b> 对象中返回结果。 </p></td>
</tr>
<tr class="odd">
<td><p>Jet</p></td>
<td><p>Jet 查询语言为 Outlook 提供简单的查询语言，它基于 Microsoft Jet Expression 服务。Jet 用于为 <b>Items</b> 集合和 <b>Table</b> 对象的 <b>Restrict</b> 方法创建筛选器字符串。</p></td>
</tr>
</tbody>
</table>


在下面的代码示例中，DemoInstantSearch 获取所有存储中的全部邮件文件夹，这些存储已使用 [Store](https://msdn.microsoft.com/library/bb609139\(v=office.15\)) 对象的 [IsInstantSearchEnabled](https://msdn.microsoft.com/library/bb609793\(v=office.15\)) 属性启用索引。 然后，它使用 **Explorer** 对象的 **Search** 方法，筛选出主题中包含确切短语“Office 2007”的上月收到的所有项。 最后，搜索结果显示在独立资源管理器窗口中。

如果使用 Visual Studio 测试此代码示例，必须先添加对 Microsoft Outlook 15.0 对象库组件的引用，并在导入 **Microsoft.Office.Interop.Outlook** 命名空间时指定 Outlook 变量。 不得将 **using** 语句直接添加到此代码示例中的函数前面，这个语句必须后跟公共类声明。 下面的代码行展示了如何在 C\# 中执行导入和分配操作。

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void DemoInstantSearch()
{
    if (Application.Session.DefaultStore.IsInstantSearchEnabled)
    {
        Outlook.Explorer explorer = Application.Explorers.Add(
            Application.Session.GetDefaultFolder(
            Outlook.OlDefaultFolders.olFolderInbox)
            as Outlook.Folder,
            Outlook.OlFolderDisplayMode.olFolderDisplayNormal);
        string filter = "subject:" +
            "\"" + "Office 2007" + "\"" +
            " received:(last month)";
        explorer.Search(filter,
            Outlook.OlSearchScope.olSearchScopeAllFolders);
        explorer.Display();
    }
}
```

## <a name="see-also"></a>另请参阅

- [搜索和筛选](search-and-filter.md)

