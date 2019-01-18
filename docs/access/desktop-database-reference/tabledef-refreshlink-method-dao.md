---
title: TableDef.RefreshLink 方法 (DAO)
TOCTitle: RefreshLink Method
ms:assetid: 9f0059c6-3b7b-57e3-7527-ef674ad9417d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198349(v=office.15)
ms:contentKeyID: 48546674
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052980
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ba9375da16cebd7db7a29fe20fca6f8b395a73a2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716465"
---
# <a name="tabledefrefreshlink-method-dao"></a><span data-ttu-id="dd7f3-102">TableDef.RefreshLink 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="dd7f3-102">TableDef.RefreshLink method (DAO)</span></span>

<span data-ttu-id="dd7f3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd7f3-103">**Applies to**: Access 2013, Office 2013</span></span>
 
<span data-ttu-id="dd7f3-104">更新链接表的连接信息（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-104">Updates the connection information for a linked table (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="dd7f3-105">语法</span><span class="sxs-lookup"><span data-stu-id="dd7f3-105">Syntax</span></span>

<span data-ttu-id="dd7f3-106">*表达式*。RefreshLink</span><span class="sxs-lookup"><span data-stu-id="dd7f3-106">*expression* .RefreshLink</span></span>

<span data-ttu-id="dd7f3-107">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-107">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd7f3-108">注解</span><span class="sxs-lookup"><span data-stu-id="dd7f3-108">Remarks</span></span>

<span data-ttu-id="dd7f3-p101">要更改链接表的连接信息，请重置相应 [TableDef](connection-connect-property-dao.md) 对象的 \*\*\*\*Connect\*\*\*\* 属性，然后使用 **RefreshLink** 方法更新信息。使用 **RefreshLink** 方法不会更改链接表的属性和 **[Relation](relation-object-dao.md)** 对象。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-p101">To change the connection information for a linked table, reset the **[Connect](connection-connect-property-dao.md)** property of the corresponding **TableDef** object and then use the **RefreshLink** method to update the information. Using **RefreshLink** method doesn't change the linked table's properties and **[Relation](relation-object-dao.md)** objects.</span></span>

<span data-ttu-id="dd7f3-111">要使此连接信息存在于与代表链接表的 **TableDef** 对象关联的所有集合中，必须对每个集合使用 **[Refresh](tabledefs-refresh-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-111">For this connection information to exist in all collections associated with the **TableDef** object that represents the linked table, you must use the **[Refresh](tabledefs-refresh-method-dao.md)** method on each collection.</span></span>

## <a name="example"></a><span data-ttu-id="dd7f3-112">示例</span><span class="sxs-lookup"><span data-stu-id="dd7f3-112">Example</span></span>

<span data-ttu-id="dd7f3-p102">以下示例在链接表的连接由一个数据源更改为另一个数据源后，使用 **RefreshLink** 方法刷新该链接表中的数据。若要使该过程运行，需要使用 RefreshLinkOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="dd7f3-p102">This example uses the **RefreshLink** method to refresh the data in a linked table after its connection has been changed from one data source to another. The RefreshLinkOutput procedure is required for this procedure to run.</span></span>

```vb 
Sub RefreshLinkX() 
 
 Dim dbsCurrent As Database 
 Dim tdfLinked As TableDef 
 
 ' Open a database to which a linked table can be 
 ' appended. 
 Set dbsCurrent = OpenDatabase("DB1.mdb") 
 
 ' Create a linked table that points to a Microsoft 
 ' SQL Server database. 
 Set tdfLinked = _ 
 dbsCurrent.CreateTableDef("AuthorsTable") 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 tdfLinked.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=Publishers" 
 tdfLinked.SourceTableName = "authors" 
 dbsCurrent.TableDefs.Append tdfLinked 
 
 ' Display contents of linked table. 
 Debug.Print _ 
 "Data from linked table connected to first source:" 
 RefreshLinkOutput dbsCurrent 
 
 ' Change connection information for linked table and 
 ' refresh the connection in order to make the new data 
 ' available. 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 tdfLinked.Connect = _ 
 "ODBC;DATABASE=pubs;DSN=NewPublishers" 
 tdfLinked.RefreshLink 
 
 ' Display contents of linked table. 
 Debug.Print _ 
 "Data from linked table connected to second source:" 
 RefreshLinkOutput dbsCurrent 
 
 ' Delete linked table because this is a demonstration. 
 dbsCurrent.TableDefs.Delete tdfLinked.Name 
 
 dbsCurrent.Close 
 
End Sub 
 
Sub RefreshLinkOutput(dbsTemp As Database) 
 
 Dim rstRemote As Recordset 
 Dim intCount As Integer 
 
 ' Open linked table. 
 Set rstRemote = _ 
 dbsTemp.OpenRecordset("AuthorsTable") 
 
 intCount = 0 
 
 ' Enumerate Recordset object, but stop at 50 records. 
 With rstRemote 
 Do While Not .EOF And intCount < 50 
 Debug.Print , .Fields(0), .Fields(1) 
 intCount = intCount + 1 
 .MoveNext 
 Loop 
 If Not .EOF Then Debug.Print , "[more records]" 
 .Close 
 End With 
 
End Sub 
 
```

