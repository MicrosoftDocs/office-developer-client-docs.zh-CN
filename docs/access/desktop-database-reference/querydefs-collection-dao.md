---
title: QueryDefs 集合 (DAO)
TOCTitle: QueryDefs Collection
ms:assetid: 6178c3a6-8301-16bf-4657-0fb113de0a36
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194892(v=office.15)
ms:contentKeyID: 48545215
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 3543d882e0584c35c88a5475032d9fe5505f516c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303232"
---
# <a name="querydefs-collection-dao"></a><span data-ttu-id="666f5-102">QueryDefs 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="666f5-102">QueryDefs collection (DAO)</span></span>

<span data-ttu-id="666f5-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="666f5-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="666f5-104">**QueryDefs** 集合包含 Microsoft Access 数据库引擎数据库中的 **Database** 对象的所有 **QueryDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="666f5-104">A **QueryDefs** collection contains all **QueryDef** objects of a **Database** object in a Microsoft Access database engine database.</span></span>

## <a name="remarks"></a><span data-ttu-id="666f5-105">说明</span><span class="sxs-lookup"><span data-stu-id="666f5-105">Remarks</span></span>

<span data-ttu-id="666f5-106">要新建 **QueryDef** 对象，请使用 **CreateQueryDef** 方法。</span><span class="sxs-lookup"><span data-stu-id="666f5-106">To create a new **QueryDef** object, use the **CreateQueryDef** method.</span></span> <span data-ttu-id="666f5-107">在 Microsoft Access 工作区中，如果为  name 参数提供了字符串，或者将新的 **QueryDef** 对象的 **Name** 属性显式设置为非零长度字符串，那么将创建一个会自动追加到 **QueryDefs** 集合并保存到磁盘的永久 **QueryDef**。</span><span class="sxs-lookup"><span data-stu-id="666f5-107">In a Microsoft Access workspace, if you supply a string for the  name argument or if you explicitly set the **Name** property of the new **QueryDef** object to a non-zero-length string, you will create a permanent **QueryDef** that will automatically be appended to the **QueryDefs** collection and saved to disk.</span></span> <span data-ttu-id="666f5-108">提供零长度字符串作为  name 参数或将 **Name** 属性显式设置为零长度字符串将导致生成临时的 **QueryDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="666f5-108">Supplying a zero-length string as the  name argument or explicitly setting the **Name** property to a zero-length string will result in a temporary **QueryDef** object.</span></span>

<span data-ttu-id="666f5-109">若要按照序号或 **Name** 属性设置来引用集合中的 **QueryDef** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="666f5-109">To refer to a **QueryDef** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="666f5-110">**QueryDefs**(0)</span><span class="sxs-lookup"><span data-stu-id="666f5-110">**QueryDefs**(0)</span></span>

<span data-ttu-id="666f5-111">**QueryDefs**("name")</span><span class="sxs-lookup"><span data-stu-id="666f5-111">**QueryDefs**("name")</span></span>

<span data-ttu-id="666f5-112">**QueryDefs**\!\[name\]</span><span class="sxs-lookup"><span data-stu-id="666f5-112">**QueryDefs**\!\[name\]</span></span>

<span data-ttu-id="666f5-113">仅可以按照分配给临时 **QueryDef** 对象的对象变量引用这些对象。</span><span class="sxs-lookup"><span data-stu-id="666f5-113">You can refer to temporary **QueryDef** objects only by the object variables that you have assigned to them.</span></span>

## <a name="example"></a><span data-ttu-id="666f5-114">示例</span><span class="sxs-lookup"><span data-stu-id="666f5-114">Example</span></span>

<span data-ttu-id="666f5-p102">以下示例创建一个新的 **QueryDef** 对象，并将其追加到 Northwind **Database** 对象的 **QueryDefs** 集合。然后，该示例枚举 **QueryDefs** 集合和新 **QueryDef** 的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="666f5-p102">This example creates a new **QueryDef** object and appends it to the **QueryDefs** collection of the Northwind **Database** object. It then enumerates the **QueryDefs** collection and the **Properties** collection of the new **QueryDef**.</span></span>

```vb
    Sub QueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfNew As QueryDef 
       Dim qdfLoop As QueryDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new QueryDef object. Because it has a  
       ' name, it is automatically appended to the  
       ' QueryDefs collection. 
       Set qdfNew = dbsNorthwind.CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
     
       With dbsNorthwind 
          Debug.Print .QueryDefs.Count & _ 
             " QueryDefs in " & .Name 
     
          ' Enumerate QueryDefs collection. 
          For Each qdfLoop In .QueryDefs 
             Debug.Print "  " & qdfLoop.Name 
          Next qdfLoop 
     
          With qdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new  
             ' QueryDef object. 
             For Each prpLoop In .Properties 
                On Error Resume Next 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
                On Error Goto 0 
             Next prpLoop 
          End With 
     
          ' Delete new QueryDef because this is a  
          ' demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="666f5-p103">以下示例使用 **CreateQueryDef** 方法创建并执行临时和永久的 **QueryDef**。若要使该过程运行，需要使用 GetrstTemp 函数。</span><span class="sxs-lookup"><span data-stu-id="666f5-p103">This example uses the **CreateQueryDef** method to create and execute both a temporary and a permanent **QueryDef**. The GetrstTemp function is required for this procedure to run.</span></span>

```vb
    Sub CreateQueryDefX() 
     
       Dim dbsNorthwind As Database 
       Dim qdfTemp As QueryDef 
       Dim qdfNew As QueryDef 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       With dbsNorthwind 
          ' Create temporary QueryDef. 
          Set qdfTemp = .CreateQueryDef("", _ 
             "SELECT * FROM Employees") 
          ' Open Recordset and print report. 
          GetrstTemp qdfTemp 
          ' Create permanent QueryDef. 
          Set qdfNew = .CreateQueryDef("NewQueryDef", _ 
             "SELECT * FROM Categories") 
          ' Open Recordset and print report. 
          GetrstTemp qdfNew 
          ' Delete new QueryDef because this is a demonstration. 
          .QueryDefs.Delete qdfNew.Name 
          .Close 
       End With 
     
    End Sub 
     
    Function GetrstTemp(qdfTemp As QueryDef) 
     
       Dim rstTemp As Recordset 
     
       With qdfTemp 
          Debug.Print .Name 
          Debug.Print "  " & .SQL 
          ' Open Recordset from QueryDef. 
          Set rstTemp = .OpenRecordset(dbOpenSnapshot) 
     
          With rstTemp 
             ' Populate Recordset and print number of records. 
             .MoveLast 
             Debug.Print "  Number of records = " & _ 
                .RecordCount 
             Debug.Print 
             .Close 
          End With 
     
       End With 
     
    End Function 
```

<br/>

以下示例演示如何执行参数查询。 <span data-ttu-id="666f5-120">参数集合用于在执行查询前设置 myActionQuery 查询的 Organization 参数。</span><span class="sxs-lookup"><span data-stu-id="666f5-120">The Parameters collection is used to set the Organization parameter of the myActionQuery query before the query is executed.</span></span>

<span data-ttu-id="666f5-121">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="666f5-121">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Public Sub ExecParameterQuery()
    
        Dim dbs As DAO.Database
        Dim qdf As DAO.QueryDef
    
        Set dbs = CurrentDb
        Set qdf = dbs.QueryDefs("myActionQuery")
    
        'Set the value of the QueryDef's parameter
        qdf.Parameters("Organization").Value = "Microsoft"
    
        'Execute the query
        qdf.Execute dbFailOnError
    
        'Clean up
        qdf.Close
        Set qdf = Nothing
        Set dbs = Nothing
    
    End Sub
```

<br/>

<span data-ttu-id="666f5-122">以下示例说明如何打开基于参数查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="666f5-122">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

```vb
    Dim dbs As DAO.Database
    Dim qdf As DAO.QueryDef
    Dim rst As DAO.Recordset
    
    Set dbs = CurrentDb
    
    'Get the parameter query
    Set qfd = dbs.QueryDefs("qryMyParameterQuery")
    
    'Supply the parameter value
    qdf.Parameters("EnterStartDate") = Date
    qdf.Parameters("EnterEndDate") = Date + 7
    
    'Open a Recordset based on the parameter query
    Set rst = qdf.OpenRecordset()
```

