---
title: CreateIndex 方法 (DAO) TableDef
TOCTitle: CreateIndex Method
ms:assetid: 857b25c1-01fa-b926-0c74-7105e71b7505
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196791(v=office.15)
ms:contentKeyID: 48546062
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052970
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: baa82b659cc2260d4a003c644b2d03d6c897fd21
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314369"
---
# <a name="tabledefcreateindex-method-dao"></a><span data-ttu-id="7e0ad-102">CreateIndex 方法 (DAO) TableDef</span><span class="sxs-lookup"><span data-stu-id="7e0ad-102">TableDef.CreateIndex method (DAO)</span></span>

<span data-ttu-id="7e0ad-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e0ad-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="7e0ad-104">创建新的**[Index](index-object-dao.md)** 对象 (仅适用于 Microsoft Access 工作区)。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-104">Creates a new **[Index](index-object-dao.md)** object (Microsoft Access workspaces only).</span></span> <span data-ttu-id="7e0ad-105">.</span><span class="sxs-lookup"><span data-stu-id="7e0ad-105"></span></span>

## <a name="syntax"></a><span data-ttu-id="7e0ad-106">语法</span><span class="sxs-lookup"><span data-stu-id="7e0ad-106">Syntax</span></span>

<span data-ttu-id="7e0ad-107">*表达式*。CreateIndex (***Name***)</span><span class="sxs-lookup"><span data-stu-id="7e0ad-107">*expression* .CreateIndex(***Name***)</span></span>

<span data-ttu-id="7e0ad-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="7e0ad-109">参数</span><span class="sxs-lookup"><span data-stu-id="7e0ad-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7e0ad-110">名称</span><span class="sxs-lookup"><span data-stu-id="7e0ad-110">Name</span></span></p></th>
<th><p><span data-ttu-id="7e0ad-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="7e0ad-111">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="7e0ad-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="7e0ad-112">Data type</span></span></p></th>
<th><p><span data-ttu-id="7e0ad-113">说明</span><span class="sxs-lookup"><span data-stu-id="7e0ad-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e0ad-114"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="7e0ad-114"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="7e0ad-115">可选</span><span class="sxs-lookup"><span data-stu-id="7e0ad-115">Optional</span></span></p></td>
<td><p><span data-ttu-id="7e0ad-116"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="7e0ad-116"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="7e0ad-117">一个对新的 <strong>Index</strong> 对象进行唯一命名的 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-117">A <strong>String</strong> that uniquely names the new <strong>Index</strong> object.</span></span> <span data-ttu-id="7e0ad-118">有关有效 <strong>Index</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-118">See the <strong>Name</strong> property for details on valid <strong>Index</strong> names.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="7e0ad-119">返回值</span><span class="sxs-lookup"><span data-stu-id="7e0ad-119">Return value</span></span>

<span data-ttu-id="7e0ad-120">Index</span><span class="sxs-lookup"><span data-stu-id="7e0ad-120">Index</span></span>

## <a name="remarks"></a><span data-ttu-id="7e0ad-121">注解</span><span class="sxs-lookup"><span data-stu-id="7e0ad-121">Remarks</span></span>

<span data-ttu-id="7e0ad-122">您可以使用 **CreateIndex** 方法为 **TableDef** 对象创建一个新的 **Index** 对象。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-122">You can use the **CreateIndex** method to create a new **Index** object for a **TableDef** object.</span></span> <span data-ttu-id="7e0ad-123">如果在使用**CreateIndex**时省略了可选的 name 部分, 则可以在将新对象追加到集合之前, 使用适当的赋值语句设置或重置**name**属性。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-123">If you omit the optional name part when you use **CreateIndex**, you can use an appropriate assignment statement to set or reset the **Name** property before you append the new object to a collection.</span></span> <span data-ttu-id="7e0ad-124">追加对象后，您也许能够或不能设置其 **Name** 属性（取决于包含 **Indexes** 集合的对象类型）。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-124">After you append the object, you may or may not be able to set its **Name** property, depending on the type of object that contains the **Indexes** collection.</span></span> <span data-ttu-id="7e0ad-125">有关详细信息，请参阅 **Name** 属性主题。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-125">See the **Name** property topic for more details.</span></span>

<span data-ttu-id="7e0ad-126">如果 name 引用了已经是集合成员的对象, 则当您使用**[Append](fields-append-method-dao.md)** 方法时, 将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-126">If name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="7e0ad-127">要从集合中删除 **Index** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-127">To remove an **Index** object from a collection, use the **[Delete](fields-delete-method-dao.md)** method on the collection.</span></span>

## <a name="example"></a><span data-ttu-id="7e0ad-128">示例</span><span class="sxs-lookup"><span data-stu-id="7e0ad-128">Example</span></span>

<span data-ttu-id="7e0ad-p104">以下示例使用 **CreateIndex** 方法创建两个新的 **Index** 对象，然后将它们追加到 Employees **TableDef** 对象的 **Indexes** 集合。然后，该示例枚举 **TableDef** 对象的 Indexes 集合、新 **Index** 对象的 **Fields** 集合，以及新 **Index** 对象的 Properties 集合。若要使该过程正常运行，需要使用 CreateIndexOutput 函数。</span><span class="sxs-lookup"><span data-stu-id="7e0ad-p104">This example uses the **CreateIndex** method to create two new **Index** objects and then appends them to the **Indexes** collection of the Employees **TableDef** object. It then enumerates the Indexes collection of the **TableDef** object, the **Fields** collection of the new **Index** objects, and the Properties collection of the new **Index** objects. The CreateIndexOutput function is required for this procedure to run.</span></span>

```vb
    Sub CreateIndexX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim idxCountry As Index 
     Dim idxFirstName As Index 
     Dim idxLoop As Index 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind!Employees 
     
     With tdfEmployees 
     ' Create first Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxCountry = .CreateIndex("CountryIndex") 
     With idxCountry 
     .Fields.Append .CreateField("Country") 
     .Fields.Append .CreateField("LastName") 
     .Fields.Append .CreateField("FirstName") 
     End With 
     .Indexes.Append idxCountry 
     
     ' Create second Index object, create and append Field 
     ' objects to the Index object, and then append the 
     ' Index object to the Indexes collection of the 
     ' TableDef. 
     Set idxFirstName = .CreateIndex 
     With idxFirstName 
     .Name = "FirstNameIndex" 
     .Fields.Append .CreateField("FirstName") 
     .Fields.Append .CreateField("LastName") 
     End With 
     .Indexes.Append idxFirstName 
     
     ' Refresh collection so that you can access new Index 
     ' objects. 
     .Indexes.Refresh 
     
     Debug.Print .Indexes.Count & " Indexes in " & _ 
     .Name & " TableDef" 
     
     ' Enumerate Indexes collection. 
     For Each idxLoop In .Indexes 
     Debug.Print " " & idxLoop.Name 
     Next idxLoop 
     
     ' Print report. 
     CreateIndexOutput idxCountry 
     CreateIndexOutput idxFirstName 
     
     ' Delete new Index objects because this is a 
     ' demonstration. 
     .Indexes.Delete idxCountry.Name 
     .Indexes.Delete idxFirstName.Name 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CreateIndexOutput(idxTemp As Index) 
     
     Dim fldLoop As Field 
     Dim prpLoop As Property 
     
     With idxTemp 
     ' Enumerate Fields collection of Index object. 
     Debug.Print "Fields in " & .Name 
     For Each fldLoop In .Fields 
     Debug.Print " " & fldLoop.Name 
     Next fldLoop 
     
     ' Enumerate Properties collection of Index object. 
     Debug.Print "Properties of " & .Name 
     For Each prpLoop In .Properties 
     Debug.Print " " & prpLoop.Name & " - " & _ 
     IIf(prpLoop = "", "[empty]", prpLoop) 
     Next prpLoop 
     End With 
     
    End Function
```
