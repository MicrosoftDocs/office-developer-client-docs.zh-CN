---
title: RefreshRecord 宏操作
TOCTitle: RefreshRecord macro action
ms:assetid: 68c90d7d-f59c-9e83-bc30-8f37cf5a3696
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195261(v=office.15)
ms:contentKeyID: 48545396
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm62122
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 5e842ed4898f98f0d3c51955c3fb66010ef02853
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026195"
---
# <a name="refreshrecord-macro-action"></a>RefreshRecord 宏操作


**适用于**： Access 2013、 Office 2013

您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。

## <a name="remarks"></a>注释

**RefreshRecord** 操作只显示对当前集合中的记录所做的更改。由于 **RefreshRecord** 操作实际上并不再次查询数据库，因此当前集合将不包括自上次再次查询数据库以来添加的记录，也不排除这段时间内删除的记录；当前集合也不排除不再满足查询或筛选条件的记录。若要再次查询数据库，请使用 **[Requery](requery-macro-action.md)** 方法。再次查询窗体的记录源时，当前记录集将准确反映该记录源中的所有数据。

此宏操作的行为取决于您在客户端数据库还是在 Web 数据库中调用该操作。

## <a name="client-database"></a>客户端数据库

在客户端数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的数据所做的更改。这些更改包括当前用户或多用户环境中的其他用户所做的更改。该操作与 **[Refresh](https://docs.microsoft.com/office/vba/api/Access.Form.Refresh)** 方法等效。

**RefreshRecord** 宏操作可在客户端数据库中执行下列操作：

1.  更新活动窗体或数据表的记录源，以反映对当前集合中的行所做的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。

2.  更新当前集合，以反映更改。 如果已被删除的记录源中的行，则会更改显示\#已删除。

3.  刷新活动或数据表，以显示任何更改的记录和任何\#已删除的记录，当前集合中的。

4.  再次查询活动窗体或数据表上的任何子窗体和子报表。

## <a name="web-database"></a>Web 数据库

在 Web 数据库中，您可以使用 **RefreshRecord** 操作更新活动窗体或数据表的基础记录源，以反映对当前集合中的记录所做的更改。这些更改包括当前用户或其他用户所做的更改。

**RefreshRecord** 宏操作可在 Web 数据库中执行下列操作：

1.  从服务器中检索对当前集合中的任何基表的更改。对于 ODBC 链接表，则从数据源中检索对当前集合中的记录所做的更改。

2.  更新当前集合，以反映更改。 如果当前集合中的该行已被删除，则会更改显示\#已删除。

3.  刷新活动窗体或数据表，以显示任何更改的记录和任何\#已删除的记录，当前集合中的。

4.  再次查询活动窗体或数据表上的任何子窗体和子报表。

