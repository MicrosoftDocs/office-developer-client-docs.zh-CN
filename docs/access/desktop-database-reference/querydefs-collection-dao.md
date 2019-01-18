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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705979"
---
# <a name="querydefs-collection-dao"></a><span data-ttu-id="46c55-102">QueryDefs 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="46c55-102">QueryDefs collection (DAO)</span></span>

<span data-ttu-id="46c55-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="46c55-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="46c55-104">**QueryDefs** 集合包含 Microsoft Access 数据库引擎数据库中 **Database** 对象的所有 **QueryDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="46c55-104">A **QueryDefs** collection contains all **QueryDef** objects of a **Database** object in a Microsoft Access database engine database.</span></span>

## <a name="remarks"></a><span data-ttu-id="46c55-105">注解</span><span class="sxs-lookup"><span data-stu-id="46c55-105">Remarks</span></span>

<span data-ttu-id="46c55-106">若要创建新的 **QueryDef** 对象，请使用 **CreateQueryDef** 方法。</span><span class="sxs-lookup"><span data-stu-id="46c55-106">To create a new **QueryDef** object, use the **CreateQueryDef** method.</span></span> <span data-ttu-id="46c55-107">在 Microsoft Access 工作区中，如果您提供名称参数的字符串或明确将新的**QueryDef**对象的**Name**属性设置为非 – 零长度字符串，您将创建自动将永久**QueryDef**追加到**QueryDefs**集合并保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="46c55-107">In a Microsoft Access workspace, if you supply a string for the name argument or if you explicitly set the **Name** property of the new **QueryDef** object to a non–zero-length string, you will create a permanent **QueryDef** that will automatically be appended to the **QueryDefs** collection and saved to disk.</span></span> <span data-ttu-id="46c55-108">提供一个零长度字符串作为名称参数或明确将**名称**属性设置为零长度字符串将导致临时**QueryDef**对象。</span><span class="sxs-lookup"><span data-stu-id="46c55-108">Supplying a zero-length string as the name argument or explicitly setting the **Name** property to a zero-length string will result in a temporary **QueryDef** object.</span></span>

<span data-ttu-id="46c55-109">若要按照序号或 **Name** 属性设置来引用集合中的 **QueryDef** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="46c55-109">To refer to a **QueryDef** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="46c55-110">**QueryDefs**(0)</span><span class="sxs-lookup"><span data-stu-id="46c55-110">**QueryDefs**(0)</span></span>

<span data-ttu-id="46c55-111">**QueryDefs**("name")</span><span class="sxs-lookup"><span data-stu-id="46c55-111">**QueryDefs**("name")</span></span>

<span data-ttu-id="46c55-112">**QueryDefs**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="46c55-112">**QueryDefs**\!\[name\]</span></span>

<span data-ttu-id="46c55-113">只能按分配给临时 **QueryDef** 对象的对象变量来引用这些临时对象。</span><span class="sxs-lookup"><span data-stu-id="46c55-113">You can refer to temporary **QueryDef** objects only by the object variables that you have assigned to them.</span></span>

## <a name="example"></a><span data-ttu-id="46c55-114">示例</span><span class="sxs-lookup"><span data-stu-id="46c55-114">Example</span></span>

<span data-ttu-id="46c55-p102">以下示例创建一个新的 **QueryDef** 对象，并将其追加到 Northwind **Database** 对象的 **QueryDefs** 集合。然后，该示例枚举 **QueryDefs** 集合和新 **QueryDef** 的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="46c55-p102">This example creates a new **QueryDef** object and appends it to the **QueryDefs** collection of the Northwind **Database** object. It then enumerates the **QueryDefs** collection and the **Properties** collection of the new **QueryDef**.</span></span>

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

<span data-ttu-id="46c55-p103">以下示例使用 **CreateQueryDef** 方法创建并执行临时和永久的 **QueryDef**。若要使该过程运行，需要使用 GetrstTemp 函数。</span><span class="sxs-lookup"><span data-stu-id="46c55-p103">This example uses the **CreateQueryDef** method to create and execute both a temporary and a permanent **QueryDef**. The GetrstTemp function is required for this procedure to run.</span></span>

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

下面的示例演示如何执行参数查询。 <span data-ttu-id="46c55-120">Parameters 集合用于设置 myActionQuery 查询的 Organization 参数之前执行查询。</span><span class="sxs-lookup"><span data-stu-id="46c55-120">The Parameters collection is used to set the Organization parameter of the myActionQuery query before the query is executed.</span></span>

<span data-ttu-id="46c55-121">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="46c55-121">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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

<span data-ttu-id="46c55-122">以下示例说明如何打开基于参数查询的 Recordset。</span><span class="sxs-lookup"><span data-stu-id="46c55-122">The following example shows how to open a Recordset that is based on a parameter query.</span></span>

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

