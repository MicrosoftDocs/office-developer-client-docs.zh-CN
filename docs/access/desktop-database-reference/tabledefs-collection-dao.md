---
title: TableDefs 集合 (DAO)
TOCTitle: TableDefs Collection
ms:assetid: a2986b02-0437-d6ac-7bbb-c43f5225c3fc
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820997(v=office.15)
ms:contentKeyID: 48546766
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b265063d1912b81aa852505b756e58e7a643d4ae
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922942"
---
# <a name="tabledefs-collection-dao"></a><span data-ttu-id="78492-102">TableDefs 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="78492-102">TableDefs collection (DAO)</span></span>

<span data-ttu-id="78492-103">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="78492-103">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="78492-104">**TableDefs** 集合包含数据库中所有存储的 **TableDef** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="78492-104">A **TableDefs** collection contains all stored **TableDef** objects in a database (Microsoft Access workspaces only).</span></span>

## <a name="remarks"></a><span data-ttu-id="78492-105">注解</span><span class="sxs-lookup"><span data-stu-id="78492-105">Remarks</span></span>

<span data-ttu-id="78492-106">通过使用 **TableDef** 对象及其方法和属性来操作表定义。</span><span class="sxs-lookup"><span data-stu-id="78492-106">You manipulate a table definition using a **TableDef** object and its methods and properties.</span></span>

<span data-ttu-id="78492-107">**Database** 对象的默认集合为 **TableDefs** 集合。</span><span class="sxs-lookup"><span data-stu-id="78492-107">The default collection of a **Database** object is the **TableDefs** collection.</span></span>

<span data-ttu-id="78492-108">若要按照序号或 **Name** 属性设置来引用集合中的 **TableDef** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="78492-108">To refer to a **TableDef** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

<span data-ttu-id="78492-109">**TableDefs**(0)</span><span class="sxs-lookup"><span data-stu-id="78492-109">**TableDefs**(0)</span></span>

<span data-ttu-id="78492-110">**TableDefs**("name")</span><span class="sxs-lookup"><span data-stu-id="78492-110">**TableDefs**("name")</span></span>

<span data-ttu-id="78492-111">**TableDefs**\!\[名称\]</span><span class="sxs-lookup"><span data-stu-id="78492-111">**TableDefs**\!\[name\]</span></span>

<span data-ttu-id="78492-112">**链接提供** [UtterAccess](https://www.utteraccess.com)社区。</span><span class="sxs-lookup"><span data-stu-id="78492-112">**Links provided by** the [UtterAccess](https://www.utteraccess.com) community.</span></span> <span data-ttu-id="78492-113">UtterAccess 是主要的 Microsoft Access Wiki 和帮助论坛。</span><span class="sxs-lookup"><span data-stu-id="78492-113">UtterAccess is the premier Microsoft Access wiki and help forum.</span></span>

  - [<span data-ttu-id="78492-114">重新链接器多 Backends</span><span class="sxs-lookup"><span data-stu-id="78492-114">Re-Linker Multi-Backends</span></span>](https://www.utteraccess.com/wiki/index.php/re-linker_multi-backends)

  - [<span data-ttu-id="78492-115">LIVE、 测试和本地数据之间交换/重新链接</span><span class="sxs-lookup"><span data-stu-id="78492-115">Swap/Relink Between LIVE, TEST and LOCAL Data</span></span>](https://www.utteraccess.com/forum/swap-relink-live-test-t1328573.html)

## <a name="example"></a><span data-ttu-id="78492-116">示例</span><span class="sxs-lookup"><span data-stu-id="78492-116">Example</span></span>

<span data-ttu-id="78492-p102">以下示例创建一个新的 **TableDef** 对象，并将其追加到 Northwind Database 对象的 **TableDefs** 集合。然后，该示例枚举 **TableDefs** 集合和新 **TableDef** 的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="78492-p102">This example creates a new **TableDef** object and appends it to the **TableDefs** collection of the Northwind Database object. It then enumerates the **TableDefs** collection and the **Properties** collection of the new **TableDef**.</span></span>

```vb
    Sub TableDefX() 
     
       Dim dbsNorthwind As Database 
       Dim tdfNew As TableDef 
       Dim tdfLoop As TableDef 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Create new TableDef object, append Field objects  
       ' to its Fields collection, and append TableDef  
       ' object to the TableDefs collection of the  
       ' Database object. 
       Set tdfNew = dbsNorthwind.CreateTableDef("NewTableDef") 
       tdfNew.Fields.Append tdfNew.CreateField("Date", dbDate) 
       dbsNorthwind.TableDefs.Append tdfNew 
     
       With dbsNorthwind 
          Debug.Print .TableDefs.Count & _ 
             " TableDefs in " & .Name 
     
          ' Enumerate TableDefs collection. 
          For Each tdfLoop In .TableDefs 
             Debug.Print "  " & tdfLoop.Name 
          Next tdfLoop 
     
          With tdfNew 
             Debug.Print "Properties of " & .Name 
     
             ' Enumerate Properties collection of new 
             ' TableDef object, only printing properties 
             ' with non-empty values. 
             For Each prpLoop In .Properties 
                Debug.Print "  " & prpLoop.Name & " - " & _ 
                   IIf(prpLoop = "", "[empty]", prpLoop) 
             Next prpLoop 
     
          End With 
     
          ' Delete new TableDef since this is a  
          ' demonstration. 
          .TableDefs.Delete tdfNew.Name 
          .Close 
       End With 
     
    End Sub 
```

<br/>

<span data-ttu-id="78492-119">以下示例在 Northwind 数据库中创建一个新的 **TableDef** 对象。</span><span class="sxs-lookup"><span data-stu-id="78492-119">This example creates a new **TableDef** object in the Northwind database.</span></span>

```vb 
Sub CreateTableDefX() 
 
   Dim dbsNorthwind As Database 
   Dim tdfNew As TableDef 
   Dim prpLoop As Property 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
   ' Create a new TableDef object. 
   Set tdfNew = dbsNorthwind.CreateTableDef("Contacts") 
 
   With tdfNew 
      ' Create fields and append them to the new TableDef  
      ' object. This must be done before appending the  
      ' TableDef object to the TableDefs collection of the  
      ' Northwind database. 
      .Fields.Append .CreateField("FirstName", dbText) 
      .Fields.Append .CreateField("LastName", dbText) 
      .Fields.Append .CreateField("Phone", dbText) 
      .Fields.Append .CreateField("Notes", dbMemo) 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "before appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
      ' Append the new TableDef object to the Northwind  
      ' database. 
      dbsNorthwind.TableDefs.Append tdfNew 
 
      Debug.Print "Properties of new TableDef object " & _ 
         "after appending to collection:" 
 
      ' Enumerate Properties collection of new TableDef  
      ' object. 
      For Each prpLoop In .Properties 
         On Error Resume Next 
         If prpLoop <> "" Then Debug.Print "  " & _ 
           prpLoop.Name & " = " & prpLoop 
         On Error GoTo 0 
      Next prpLoop 
 
   End With 
 
   ' Delete new TableDef object since this is a  
   ' demonstration. 
   dbsNorthwind.TableDefs.Delete "Contacts" 
 
   dbsNorthwind.Close 
 
```



