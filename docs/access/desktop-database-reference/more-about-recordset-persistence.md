---
title: 关于记录集持久化的详细信息
TOCTitle: More About Recordset Persistence
ms:assetid: f3248de7-6eef-1dd0-ff96-557b411789e7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250232(v=office.15)
ms:contentKeyID: 48548666
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 05287befde90319ad2844effef8ef2d47e1241b7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467721"
---
# <a name="more-about-recordset-persistence"></a><span data-ttu-id="585e9-102">关于记录集持久化的详细信息</span><span class="sxs-lookup"><span data-stu-id="585e9-102">More About Recordset Persistence</span></span>


<span data-ttu-id="585e9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="585e9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="585e9-104">ADO 记录集对象支持使用其 **Save** 方法将 [Recordset](save-method-ado.md) 对象的内容存储在文件中。</span><span class="sxs-lookup"><span data-stu-id="585e9-104">The ADO Recordset object supports storing a **Recordset** object's contents in a file using its [Save](save-method-ado.md) method.</span></span> <span data-ttu-id="585e9-105">在本地驱动器上，网络服务器，或在网站上的 URL，可能存在的永久存储的文件。</span><span class="sxs-lookup"><span data-stu-id="585e9-105">The persistently stored file may exist on a local drive, network server, or as a URL on a website.</span></span> <span data-ttu-id="585e9-106">随后，可以用 **Recordset** 对象的 [Open](open-method-ado-recordset.md) 方法或 [Connection](connection-object-ado.md) 对象的 [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) 方法还原该文件。</span><span class="sxs-lookup"><span data-stu-id="585e9-106">Later, the file can be restored with either the **Recordset** object's [Open](open-method-ado-recordset.md) method or the [Connection](connection-object-ado.md) object's [Execute](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) method.</span></span>

<span data-ttu-id="585e9-107">此外，[GetString](getstring-method-ado.md) 方法可以将 **Recordset** 对象转换为以指定的字符分隔的列和行的形式。</span><span class="sxs-lookup"><span data-stu-id="585e9-107">In addition, the [GetString](getstring-method-ado.md) method converts a **Recordset** object to a form in which the columns and rows are delimited with characters you specify.</span></span>

<span data-ttu-id="585e9-p102">若要持久化 **Recordset** ，请首先将它转换为可以存储在文件中的形式。可以用专用的 Advanced Data TableGram (ADTG) 格式或开放的可扩展标记语言 (XML) 格式来存储 **Recordset** 对象。下面显示了 ADTG 示例。有关 XML 持久化的详细信息，请参阅 [用 XML 格式持久化记录](persisting-records-in-xml-format.md)。</span><span class="sxs-lookup"><span data-stu-id="585e9-p102">To persist a **Recordset**, begin by converting it to a form that can be stored in a file. **Recordset** objects can be stored in the proprietary Advanced Data TableGram (ADTG) format or the open Extensible Markup Language (XML) format. ADTG examples are shown below. For more information about XML persistence, see [Persisting Records in XML format](persisting-records-in-xml-format.md).</span></span>

<span data-ttu-id="585e9-p103">应当将任何挂起的更改保存在持久化文件中。这将允许您发出返回 **Recordset** 对象的查询，编辑 **Recordset** ，保存记录集和挂起的更改、随后还原 **Recordset** ，然后用保存的挂起更改来更新数据源。</span><span class="sxs-lookup"><span data-stu-id="585e9-p103">Save any pending changes in the persisted file. Doing this allows you to issue a query that returns a **Recordset** object, edits the **Recordset**, saves it and the pending changes, later restores the **Recordset**, and then updates the data source with the saved pending changes.</span></span>

<span data-ttu-id="585e9-114">有关永久存储 **Stream** 对象的信息，请参阅第 10 章中的 [流和持久化](streams-and-persistence.md)。</span><span class="sxs-lookup"><span data-stu-id="585e9-114">For information about persistently storing **Stream** objects, see [Streams and Persistence](streams-and-persistence.md) in Chapter 10.</span></span>

<span data-ttu-id="585e9-115">有关 **Recordset** 持久化的示例，请参阅 [XML Recordset 持久化方案](xml-recordset-persistence-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="585e9-115">For an example of **Recordset** persistence, see the [XML Recordset Persistence Scenario](xml-recordset-persistence-scenario.md).</span></span>

## <a name="example"></a><span data-ttu-id="585e9-116">示例</span><span class="sxs-lookup"><span data-stu-id="585e9-116">Example</span></span>

<span data-ttu-id="585e9-117">**保存记录集：**</span><span class="sxs-lookup"><span data-stu-id="585e9-117">**Save a Recordset:**</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Save "c:\yourFile.adtg", adPersistADTG 
```

<span data-ttu-id="585e9-118">**用 Recordset.Open 打开持久化文件：**</span><span class="sxs-lookup"><span data-stu-id="585e9-118">**Open a persisted file with Recordset.Open:**</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "c:\yourFile.adtg", "Provider='MSPersist'",,,adCmdFile
```

<span data-ttu-id="585e9-119">或者，如果 **Recordset** 没有活动连接，则可以接受所有默认值，只需编码如下：</span><span class="sxs-lookup"><span data-stu-id="585e9-119">Optionally, if the **Recordset** does not have an active connection, you can accept all the defaults and simply code the following:</span></span>

```vb 
 
Dim rs as New ADODB.Recordset 
rs.Open "c:\yourFile.adtg" 
```

<span data-ttu-id="585e9-120">**使用 Connection.Execute 打开持久化文件：**</span><span class="sxs-lookup"><span data-stu-id="585e9-120">**Open a persisted file with Connection.Execute:**</span></span>

```vb 
 
Dim conn as New ADODB.Connection 
Dim rs as ADODB.Recordset 
conn.Open "Provider='MSPersist'" 
Set rs = conn.execute("c:\yourFile.adtg") 
```

<span data-ttu-id="585e9-121">**使用 RDS.DataControl 打开持久化文件：**</span><span class="sxs-lookup"><span data-stu-id="585e9-121">**Open a persisted file with RDS.DataControl:**</span></span>

<span data-ttu-id="585e9-122">这种情况下，不设置 **Server** 属性。</span><span class="sxs-lookup"><span data-stu-id="585e9-122">In this case, the **Server** property is not set.</span></span>

```vb 
 
Dim dc as New RDS.DataControl 
dc.Connection = "Provider='MSPersist'" 
dc.SQL = "c:\yourFile.adtg" 
dc.Refresh
```
