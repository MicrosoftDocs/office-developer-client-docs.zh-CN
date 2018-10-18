---
title: Database.CreateProperty Method (DAO)
TOCTitle: CreateProperty Method
ms:assetid: f2039be9-5fd8-f673-dfbf-0a71540cdc98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836607(v=office.15)
ms:contentKeyID: 48548638
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b8da9145d41a2ae973e8d310d1286f3d7ed2594e
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602144"
---
# <a name="databasecreateproperty-method-dao"></a><span data-ttu-id="3f7bd-102">Database.CreateProperty Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="3f7bd-102">Database.CreateProperty Method (DAO)</span></span>


<span data-ttu-id="3f7bd-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3f7bd-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="3f7bd-p101">创建一个新的用户定义的 **[Property](property-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p101">Creates a new user-defined **[Property](property-object-dao.md)** object (Microsoft Access workspaces only). .</span></span>

## <a name="syntax"></a><span data-ttu-id="3f7bd-106">语法</span><span class="sxs-lookup"><span data-stu-id="3f7bd-106">Syntax</span></span>

<span data-ttu-id="3f7bd-107">*表达式*。CreateProperty （***名称***、***类型***、***值***、 ***DDL***）</span><span class="sxs-lookup"><span data-stu-id="3f7bd-107">*expression* .CreateProperty(***Name***, ***Type***, ***Value***, ***DDL***)</span></span>

<span data-ttu-id="3f7bd-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-108">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="3f7bd-109">参数</span><span class="sxs-lookup"><span data-stu-id="3f7bd-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3f7bd-110">名称</span><span class="sxs-lookup"><span data-stu-id="3f7bd-110">Name</span></span></p></th>
<th><p><span data-ttu-id="3f7bd-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="3f7bd-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="3f7bd-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="3f7bd-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="3f7bd-113">说明</span><span class="sxs-lookup"><span data-stu-id="3f7bd-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f7bd-114">名称</span><span class="sxs-lookup"><span data-stu-id="3f7bd-114">Name</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-115">可选</span><span class="sxs-lookup"><span data-stu-id="3f7bd-115">Optional</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-116"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="3f7bd-116"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="3f7bd-p102">一个对新的 <strong>Property</strong> 对象进行唯一命名的 <strong>String</strong>。有关有效 <strong>Property</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p102">A <strong>String</strong> that uniquely names the new <strong>Property</strong> object. See the <strong>Name</strong> property for details on valid <strong>Property</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f7bd-119">类型</span><span class="sxs-lookup"><span data-stu-id="3f7bd-119">Type</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-120">可选</span><span class="sxs-lookup"><span data-stu-id="3f7bd-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="3f7bd-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="3f7bd-p103">一个定义新的 <strong>Property</strong> 对象的数据类型的常量。有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p103">A constant that defines the data type of the new <strong>Property</strong> object. See the <strong><a href="field-type-property-dao.md">Type</a></strong> property for valid data types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f7bd-124">值</span><span class="sxs-lookup"><span data-stu-id="3f7bd-124">Value</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-125">可选</span><span class="sxs-lookup"><span data-stu-id="3f7bd-125">Optional</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-126"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="3f7bd-126"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="3f7bd-p104">一个包含初始属性值的 <strong>Variant</strong>。有关详细信息，请参阅 <strong><a href="field-value-property-dao.md">Value</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p104">A <strong>Variant</strong> containing the initial property value. See the <strong><a href="field-value-property-dao.md">Value</a></strong> property for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f7bd-129">DDL</span><span class="sxs-lookup"><span data-stu-id="3f7bd-129">DDL</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-130">可选</span><span class="sxs-lookup"><span data-stu-id="3f7bd-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="3f7bd-131"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="3f7bd-131"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="3f7bd-132"><strong>Variant</strong> （<strong>布尔</strong>子类型），该值指示<strong>属性</strong>DDL 对象。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-132">A <strong>Variant</strong> (<strong>Boolean</strong> subtype) that indicates whether or not the <strong>Property</strong> is a DDL object.</span></span> <span data-ttu-id="3f7bd-133">默认值为 False 。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-133">The default is False.</span></span> <span data-ttu-id="3f7bd-134">如果 DDL 为 True，则用户无法更改或删除此<strong>Property</strong>对象，除非他们具有 dbSecWriteDef 权限。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-134">If DDL is True, users can't change or delete this <strong>Property</strong> object unless they have dbSecWriteDef permission.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3f7bd-135"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="3f7bd-135"><<<<<<< HEAD</span></span>
### <a name="return-value"></a><span data-ttu-id="3f7bd-136">返回值</span><span class="sxs-lookup"><span data-stu-id="3f7bd-136">Return Value</span></span>
=======
### <a name="return-value"></a><span data-ttu-id="3f7bd-137">返回值</span><span class="sxs-lookup"><span data-stu-id="3f7bd-137">Return value</span></span>
>>>>>>> <span data-ttu-id="3f7bd-138">master</span><span class="sxs-lookup"><span data-stu-id="3f7bd-138">master</span></span>

<span data-ttu-id="3f7bd-139">属性</span><span class="sxs-lookup"><span data-stu-id="3f7bd-139">Property</span></span>

## <a name="remarks"></a><span data-ttu-id="3f7bd-140">注解</span><span class="sxs-lookup"><span data-stu-id="3f7bd-140">Remarks</span></span>

<span data-ttu-id="3f7bd-141">只能在某个对象的永久 [**Properties**](properties-collection-dao.md) 集合中创建用户定义的 **Property** 对象。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-141">You can create a user-defined **Property** object only in the **[Properties](properties-collection-dao.md)** collection of an object that is persistent.</span></span>

<span data-ttu-id="3f7bd-p106">如果使用 **CreateProperty** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅 **Name**、 **Type** 和 **Value** 属性主题。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p106">If you omit one or more of the optional parts when you use **CreateProperty**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the object, you can alter some but not all of its property settings. See the **Name**, **Type**, and **Value** property topics for more details.</span></span>

<span data-ttu-id="3f7bd-145">如果 name 引用对象的已经是集合的成员，使用**[Append](fields-append-method-dao.md)** 方法时，发生此事件运行时错误。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-145">If name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="3f7bd-p107">若要从集合中删除用户定义的 **Property** 对象，请对 **[Properties](fields-delete-method-dao.md)** 集合使用 **Delete** 方法。不能删除内置属性。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p107">To remove a user-defined **Property** object from the collection, use the **[Delete](fields-delete-method-dao.md)** method on the **Properties** collection. You can't delete built-in properties.</span></span>

> [!NOTE]
> <span data-ttu-id="3f7bd-148">如果省略 DDL 参数，则默认为 False (非 DDL)。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-148">If you omit the DDL argument, it defaults to False (non-DDL).</span></span> <span data-ttu-id="3f7bd-149">由于没有公开相应的 DDL 属性，必须删除要从 DDL 更改为非 DDL 的 **Property** 对象，然后重新创建该对象。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-149">Because no corresponding DDL property is exposed, you must delete and re-create a **Property** object you want to change from DDL to non-DDL.</span></span>


## <a name="example"></a><span data-ttu-id="3f7bd-150">示例</span><span class="sxs-lookup"><span data-stu-id="3f7bd-150">Example</span></span>

<span data-ttu-id="3f7bd-p109">以下示例尝试设置用户定义的属性的值。如果该属性不存在，则使用 **CreateProperty** 方法创建一个新属性并设置其值。若要使该过程运行，需要使用 SetProperty 过程。</span><span class="sxs-lookup"><span data-stu-id="3f7bd-p109">This example tries to set the value of a user-defined property. If the property doesn't exist, it uses the **CreateProperty** method to create and set the value of the new property. The SetProperty procedure is required for this procedure to run.</span></span>

```vb
    Sub CreatePropertyX() 
     
       Dim dbsNorthwind As Database 
       Dim prpLoop As Property 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
       ' Set the Archive property to True. 
       SetProperty dbsNorthwind, "Archive", True 
        
       With dbsNorthwind 
          Debug.Print "Properties of " & .Name 
           
          ' Enumerate Properties collection of the Northwind  
          ' database. 
          For Each prpLoop In .Properties 
             If prpLoop <> "" Then Debug.Print "  " & _ 
                prpLoop.Name & " = " & prpLoop 
          Next prpLoop 
     
          ' Delete the new property since this is a  
          ' demonstration. 
          .Properties.Delete "Archive" 
     
          .Close 
       End With 
     
    End Sub 
     
    Sub SetProperty(dbsTemp As Database, strName As String, _ 
       booTemp As Boolean) 
     
       Dim prpNew As Property 
       Dim errLoop As Error 
     
       ' Attempt to set the specified property. 
       On Error GoTo Err_Property 
       dbsTemp.Properties("strName") = booTemp 
       On Error GoTo 0 
     
       Exit Sub 
     
    Err_Property: 
     
       ' Error 3270 means that the property was not found. 
       If DBEngine.Errors(0).Number = 3270 Then 
          ' Create property, set its value, and append it to the  
          ' Properties collection. 
          Set prpNew = dbsTemp.CreateProperty(strName, _ 
             dbBoolean, booTemp) 
          dbsTemp.Properties.Append prpNew 
          Resume Next 
       Else 
          ' If different error has occurred, display message. 
          For Each errLoop In DBEngine.Errors 
             MsgBox "Error number: " & errLoop.Number & vbCr & _ 
                errLoop.Description 
          Next errLoop 
          End 
       End If 
     
    End Sub
```
