---
title: Databases 集合 (DAO)
TOCTitle: Databases Collection
ms:assetid: 988ae6f5-ec15-cd1c-191d-f295624425f4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197944(v=office.15)
ms:contentKeyID: 48546493
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: dbaa0fe7aaa50c8aec582e2f03cd2849268816b9
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715548"
---
# <a name="databases-collection-dao"></a><span data-ttu-id="f777a-102">Databases 集合 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f777a-102">Databases collection (DAO)</span></span>

<span data-ttu-id="f777a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="f777a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f777a-104">**Databases** 集合包含在 **Workspace** 对象中打开或创建的所有打开的 **Database** 对象。</span><span class="sxs-lookup"><span data-stu-id="f777a-104">A **Databases** collection contains all open **Database** objects opened or created in a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f777a-105">注解</span><span class="sxs-lookup"><span data-stu-id="f777a-105">Remarks</span></span>

<span data-ttu-id="f777a-p101">从 **Workspace** 中打开现有 **Database** 对象或创建一个新对象时，该对象会自动追加到 **Databases** 集合中。使用 [**Close**](connection-close-method-dao.md) 方法关闭 **Database** 对象时，该对象即从 **Databases** 集合中删除，但并不从磁盘中删除。关闭 **Database** 对象之前，应关闭所有打开的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="f777a-p101">When you open an existing **Database** object or create a new one from a **Workspace**, it is automatically appended to the **Databases** collection. When you close a **Database** object with the **[Close](connection-close-method-dao.md)** method, it is removed from the **Databases** collection but not deleted from disk. You should close all open **Recordset** objects before closing a **Database** object.</span></span>

<span data-ttu-id="f777a-109">在 Microsoft Access 工作区中，数据库的 **Name** 属性设置是一个指定数据库文件路径的字符串。</span><span class="sxs-lookup"><span data-stu-id="f777a-109">In a Microsoft Access workspace, the **Name** property setting of a database is a string that specifies the path of the database file.</span></span>

<span data-ttu-id="f777a-110">若要按照序号或 **Name** 属性设置来引用集合中的 **Database** 对象，可以使用下列任何一种语法形式：</span><span class="sxs-lookup"><span data-stu-id="f777a-110">To refer to a **Database** object in a collection by its ordinal number or by its **Name** property setting, use any of the following syntax forms:</span></span>

- <span data-ttu-id="f777a-111">**Databases**(0)</span><span class="sxs-lookup"><span data-stu-id="f777a-111">**Databases**(0)</span></span>

- <span data-ttu-id="f777a-112">**数据库**（"*name*"）</span><span class="sxs-lookup"><span data-stu-id="f777a-112">**Databases**("*name*")</span></span>

- <span data-ttu-id="f777a-113">**数据库**\!\[*名称*\]</span><span class="sxs-lookup"><span data-stu-id="f777a-113">**Databases**\!\[*name*\]</span></span>

> [!NOTE]
> <span data-ttu-id="f777a-p102">[!注释] 可以多次打开同一个数据源或数据库，这样会在 **Databases** 集合中创建重复的名称。应当将 **Database** 对象分配给对象变量，并通过变量名来引用它们。</span><span class="sxs-lookup"><span data-stu-id="f777a-p102">You can open the same data source or database more than once, creating duplicate names in the **Databases** collection. You should assign **Database** objects to object variables and refer to them by variable name.</span></span>

## <a name="example"></a><span data-ttu-id="f777a-116">示例</span><span class="sxs-lookup"><span data-stu-id="f777a-116">Example</span></span>

<span data-ttu-id="f777a-p103">以下示例创建一个新的 **Database** 对象并打开默认 **Workspace** 对象中的一个现有 **Database** 对象。然后，该示例枚举 **Database** 集合以及每个 **Database** 对象的 **Properties** 集合。</span><span class="sxs-lookup"><span data-stu-id="f777a-p103">This example creates a new **Database** object and opens an existing **Database** object in the default **Workspace** object. Then it enumerates the **Database** collection and the **Properties** collection of each **Database** object.</span></span>

```vb 
Sub DatabaseObjectX() 
 
 Dim wrkAcc As Workspace 
 Dim dbsNorthwind As Database 
 Dim dbsNew As Database 
 Dim dbsLoop As Database 
 Dim prpLoop As Property 
 
 Set wrkAcc = CreateWorkspace("AccWorkspace", "admin", _ 
 "", dbUseJet) 
 
 ' Make sure there isn't already a file with the name of 
 ' the new database. 
 If Dir("NewDB.mdb") <> "" Then Kill "NewDB.mdb" 
 
 ' Create a new database with the specified 
 ' collating order. 
 Set dbsNew = wrkAcc.CreateDatabase("NewDB.mdb", _ 
 dbLangGeneral) 
 Set dbsNorthwind = wrkAcc.OpenDatabase("Northwind.mdb") 
 
 ' Enumerate the Databases collection. 
 For Each dbsLoop In wrkAcc.Databases 
 With dbsLoop 
 Debug.Print "Properties of " & .Name 
 ' Enumerate the Properties collection of each 
 ' Database object. 
 For Each prpLoop In .Properties 
 If prpLoop <> "" Then Debug.Print " " & _ 
 prpLoop.Name & " = " & prpLoop 
 Next prpLoop 
 End With 
 Next dbsLoop 
 
 dbsNew.Close 
 dbsNorthwind.Close 
 wrkAcc.Close 
 
End Sub 
 
```

<br/>

<span data-ttu-id="f777a-119">以下示例使用 **CreateDatabase** 创建一个新的加密 **Database** 对象。</span><span class="sxs-lookup"><span data-stu-id="f777a-119">This example uses **CreateDatabase** to create a new, encrypted **Database** object.</span></span>

```vb
    Sub CreateDatabaseX() 
     
     Dim wrkDefault As Workspace 
     Dim dbsNew As DATABASE 
     Dim prpLoop As Property 
     
     ' Get default Workspace. 
     Set wrkDefault = DBEngine.Workspaces(0) 
     
     ' Make sure there isn't already a file with the name of 
     ' the new database. 
     If Dir("NewDB.mdb") <> "" Then Kill "NewDB.mdb" 
     
     ' Create a new encrypted database with the specified 
     ' collating order. 
     Set dbsNew = wrkDefault.CreateDatabase("NewDB.mdb", _ 
     dbLangGeneral, dbEncrypt) 
     
     With dbsNew 
     Debug.Print "Properties of " & .Name 
     ' Enumerate the Properties collection of the new 
     ' Database object. 
     For Each prpLoop In .Properties 
     If prpLoop <> "" Then Debug.Print " " & _ 
     prpLoop.Name & " = " & prpLoop 
     Next prpLoop 
     End With 
     
     dbsNew.Close 
     
    End Sub
```
