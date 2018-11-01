---
title: DBEngine Object (DAO)
TOCTitle: DBEngine Object
ms:assetid: ceaeb505-615e-37ba-4633-27240ef8c5de
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834506(v=office.15)
ms:contentKeyID: 48547792
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 86c14ef0e9443965b2e80af329d4cca6023d1467
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25873627"
---
# <a name="dbengine-object-dao"></a><span data-ttu-id="bef85-102">DBEngine Object (DAO)</span><span class="sxs-lookup"><span data-stu-id="bef85-102">DBEngine Object (DAO)</span></span>

<span data-ttu-id="bef85-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bef85-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bef85-104">**DBEngine** 对象是数据访问对象 (DAO) 对象模型中的顶层对象。</span><span class="sxs-lookup"><span data-stu-id="bef85-104">The **DBEngine** object is the top level object in the DAO object model.</span></span>

## <a name="remarks"></a><span data-ttu-id="bef85-105">注解</span><span class="sxs-lookup"><span data-stu-id="bef85-105">Remarks</span></span>

<span data-ttu-id="bef85-p101">**DBEngine** 对象包含和控制 DAO 对象层次结构中的所有其他对象。不能创建额外的 **DBEngine** 对象，并且 **DBEngine** 对象不是任何集合的元素。</span><span class="sxs-lookup"><span data-stu-id="bef85-p101">The **DBEngine** object contains and controls all other objects in the hierarchy of DAO objects. You can't create additional **DBEngine** objects, and the **DBEngine** object isn't an element of any collection.</span></span>

<span data-ttu-id="bef85-108">对于任何类型的数据库或连接，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bef85-108">With any type of database or connection, you can:</span></span>

  - <span data-ttu-id="bef85-109">使用 **Version** 属性获取 DAO 版本号。</span><span class="sxs-lookup"><span data-stu-id="bef85-109">Use the **Version** property to obtain the DAO version number.</span></span>

  - <span data-ttu-id="bef85-110">使用 **LoginTimeout** 属性获取或设置开放式数据库连接 (ODBC) 登录超时时间，使用 **RegisterDatabase** 方法为 Microsoft Access 数据库引擎提供 ODBC 信息。</span><span class="sxs-lookup"><span data-stu-id="bef85-110">Use the **LoginTimeout** property to obtain or set the ODBC login timeout, and the **RegisterDatabase** method to provide ODBC information to the Microsoft Access database engine.</span></span>

  - <span data-ttu-id="bef85-111">使用 **DefaultPassword** 和 **DefaultUser** 属性为默认的 **Workspace** 对象设置用户标识和密码。</span><span class="sxs-lookup"><span data-stu-id="bef85-111">Use the **DefaultPassword** and **DefaultUser** properties to set the user identification and password for the default **Workspace** object.</span></span>

  - <span data-ttu-id="bef85-p102">使用 **CreateWorkspace** 方法创建新的 **Workspace** 对象。可使用可选参数替代 **DefaultType**、 **DefaultPassword** 和 **DefaultUser** 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="bef85-p102">Use the **CreateWorkspace** method to create a new **Workspace** object. You can use optional arguments to override the settings of the **DefaultType**, **DefaultPassword**, and **DefaultUser** properties.</span></span>

  - <span data-ttu-id="bef85-114">使用 **OpenDatabase** 方法在默认的 **Workspace** 中打开一个数据库，使用 **BeginTrans**、 **Commit** 和 **Rollback** 方法控制默认 **Workspace** 上的事务。</span><span class="sxs-lookup"><span data-stu-id="bef85-114">Use the **OpenDatabase** method to open a database in the default **Workspace**, and use the **BeginTrans**, **Commit**, and **Rollback** methods to control transactions on the default **Workspace**.</span></span>

  - <span data-ttu-id="bef85-115">使用 **Workspaces** 集合引用特定的 **Workspace** 对象。</span><span class="sxs-lookup"><span data-stu-id="bef85-115">Use the **Workspaces** collection to reference specific **Workspace** objects.</span></span>

  - <span data-ttu-id="bef85-116">使用 **Errors** 集合检查数据访问错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="bef85-116">Use the **Errors** collection to examine data access error details.</span></span>

<span data-ttu-id="bef85-p103">只有将 DAO 与 Microsoft Access 数据库引擎一起使用时，才可以使用其他属性和方法。可以使用这些属性和方法来控制 Microsoft Access 数据库引擎，操作该数据库引擎的属性，以及对那些不是集合元素的临时对象执行任务。例如，您可以进行下列操作：</span><span class="sxs-lookup"><span data-stu-id="bef85-p103">Other properties and methods are only available when you use DAO with the Microsoft Access database engine. You can use them to control the Microsoft Access database engine, manipulate its properties, and perform tasks on temporary objects that aren't elements of collections. For example, you can:</span></span>

  - <span data-ttu-id="bef85-120">使用 **CreateDatabase** 方法创建新的 Microsoft Access 数据库引擎 **Database** 对象。</span><span class="sxs-lookup"><span data-stu-id="bef85-120">Use the **CreateDatabase** method to create a new Microsoft Access database engine **Database** object.</span></span>

  - <span data-ttu-id="bef85-121">使用 **Idle** 方法使 Microsoft Access 数据库引擎能够完成任何待定的任务。</span><span class="sxs-lookup"><span data-stu-id="bef85-121">Use the **Idle** method to enable the Microsoft Access database engine to complete any pending tasks.</span></span>

  - <span data-ttu-id="bef85-122">使用 **CompactDatabase** 和 **RepairDatabase** 方法维护数据库文件。</span><span class="sxs-lookup"><span data-stu-id="bef85-122">Use the **CompactDatabase** and **RepairDatabase** methods to maintain database files.</span></span>

  - <span data-ttu-id="bef85-p104">分别使用 **IniPath** 和 **SystemDB** 属性指定 Microsoft Access 数据库引擎的 Windows 注册表信息文件的位置和 Microsoft Access 工作组信息文件的位置。 **SetOption** 方法允许您替代 Microsoft Access 数据库引擎的 Windows 注册表设置。</span><span class="sxs-lookup"><span data-stu-id="bef85-p104">Use the **IniPath** and **SystemDB** properties to specify the location of Microsoft Access database engine Windows Registry information and the Microsoft Access workgroup information file, respectively. The **SetOption** method allows you override windows registry settings for the Microsoft Access database engine.</span></span>

<span data-ttu-id="bef85-125">更改 **DefaultType** 和 **IniPath** 属性设置之后，只有后续的 **Workspace** 对象才会反映这些更改。</span><span class="sxs-lookup"><span data-stu-id="bef85-125">After you change the **DefaultType** and **IniPath** property settings, only subsequent **Workspace** objects will reflect these changes.</span></span>

<span data-ttu-id="bef85-126">要引用一个属于 **DBEngine** 对象的集合，或引用一个应用到该对象的方法或属性，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="bef85-126">To refer to a collection that belongs to the **DBEngine** object, or to refer to a method or property that applies to this object, use this syntax:</span></span>

<span data-ttu-id="bef85-127">\[**DBEngine**。\]\[集合 |方法 |属性\]</span><span class="sxs-lookup"><span data-stu-id="bef85-127">\[**DBEngine**.\]\[collection | method | property\]</span></span>

## <a name="example"></a><span data-ttu-id="bef85-128">示例</span><span class="sxs-lookup"><span data-stu-id="bef85-128">Example</span></span>

<span data-ttu-id="bef85-129">以下示例枚举 **DBEngine** 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="bef85-129">This example enumerates the collections of the **DBEngine** object.</span></span>

```vb
    Sub DBEngineX() 
     
     Dim wrkLoop As Workspace 
     Dim prpLoop As Property 
     
     With DBEngine 
     Debug.Print "DBEngine Properties" 
     
     ' Enumerate Properties collection of DBEngine, 
     ' trapping for properties whose values are 
     ' invalid in this context. 
     For Each prpLoop In .Properties 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & " = " _ 
     & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     Debug.Print "Workspaces collection of DBEngine" 
     
     ' Enumerate Workspaces collection of DBEngine. 
     For Each wrkLoop In .Workspaces 
     Debug.Print " " & wrkLoop.Name 
     
     ' Enumerate Properties collection of each 
     ' Workspace object, trapping for properties 
     ' whose values are invalid in this context. 
     For Each prpLoop In wrkLoop.Properties 
     On Error Resume Next 
     Debug.Print " " & prpLoop.Name & _ 
     " = " & prpLoop 
     On Error GoTo 0 
     Next prpLoop 
     
     Next wrkLoop 
     
     End With 
     
    End Sub
```
