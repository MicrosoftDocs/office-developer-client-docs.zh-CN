---
title: CreateProperty 方法 (DAO)
TOCTitle: CreateProperty Method
ms:assetid: f2039be9-5fd8-f673-dfbf-0a71540cdc98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836607(v=office.15)
ms:contentKeyID: 48548638
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f966e041a6d2aff773f6c3849c0846ef362d1142
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294972"
---
# <a name="databasecreateproperty-method-dao"></a><span data-ttu-id="99e37-102">CreateProperty 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="99e37-102">Database.CreateProperty method (DAO)</span></span>

<span data-ttu-id="99e37-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="99e37-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="99e37-104">创建一个新的用户定义的 **[Property](property-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="99e37-104">Creates a new user-defined **[Property](property-object-dao.md)** object (Microsoft Access workspaces only).</span></span> <span data-ttu-id="99e37-105">.</span><span class="sxs-lookup"><span data-stu-id="99e37-105"></span></span>

## <a name="syntax"></a><span data-ttu-id="99e37-106">语法</span><span class="sxs-lookup"><span data-stu-id="99e37-106">Syntax</span></span>

<span data-ttu-id="99e37-107">*表达式*。CreateProperty (***Name***、 ***Type***、 ***Value***、 ***DDL***)</span><span class="sxs-lookup"><span data-stu-id="99e37-107">*expression* .CreateProperty(***Name***, ***Type***, ***Value***, ***DDL***)</span></span>

<span data-ttu-id="99e37-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="99e37-108">*expression* A variable that represents a **Database** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="99e37-109">参数</span><span class="sxs-lookup"><span data-stu-id="99e37-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="99e37-110">名称</span><span class="sxs-lookup"><span data-stu-id="99e37-110">Name</span></span></p></th>
<th><p><span data-ttu-id="99e37-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="99e37-111">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="99e37-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="99e37-112">Data type</span></span></p></th>
<th><p><span data-ttu-id="99e37-113">说明</span><span class="sxs-lookup"><span data-stu-id="99e37-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99e37-114"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="99e37-114"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="99e37-115">可选</span><span class="sxs-lookup"><span data-stu-id="99e37-115">Optional</span></span></p></td>
<td><p><span data-ttu-id="99e37-116"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="99e37-116"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="99e37-117">一个对新的 <strong>Property</strong> 对象进行唯一命名的 <strong>String</strong>。</span><span class="sxs-lookup"><span data-stu-id="99e37-117">A <strong>String</strong> that uniquely names the new <strong>Property</strong> object.</span></span> <span data-ttu-id="99e37-118">有关有效 <strong>Property</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="99e37-118">See the <strong>Name</strong> property for details on valid <strong>Property</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99e37-119"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="99e37-119"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="99e37-120">可选</span><span class="sxs-lookup"><span data-stu-id="99e37-120">Optional</span></span></p></td>
<td><p><span data-ttu-id="99e37-121"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="99e37-121"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="99e37-122">一个定义新的 <strong>Property</strong> 对象的数据类型的常量。</span><span class="sxs-lookup"><span data-stu-id="99e37-122">A constant that defines the data type of the new <strong>Property</strong> object.</span></span> <span data-ttu-id="99e37-123">有关有效数据类型, 请参阅<strong><a href="field-type-property-dao.md">Type</a></strong>属性。</span><span class="sxs-lookup"><span data-stu-id="99e37-123">See the <strong><a href="field-type-property-dao.md">Type</a></strong> property for valid data types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99e37-124"><em>Value</em></span><span class="sxs-lookup"><span data-stu-id="99e37-124"><em>Value</em></span></span></p></td>
<td><p><span data-ttu-id="99e37-125">可选</span><span class="sxs-lookup"><span data-stu-id="99e37-125">Optional</span></span></p></td>
<td><p><span data-ttu-id="99e37-126"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="99e37-126"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="99e37-127">一个包含初始属性值的 <strong>Variant</strong>。</span><span class="sxs-lookup"><span data-stu-id="99e37-127">A <strong>Variant</strong> containing the initial property value.</span></span> <span data-ttu-id="99e37-128">有关详细信息, 请参阅<strong><a href="field-value-property-dao.md">Value</a></strong>属性。</span><span class="sxs-lookup"><span data-stu-id="99e37-128">See the <strong><a href="field-value-property-dao.md">Value</a></strong> property for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99e37-129"><em>DDL</em></span><span class="sxs-lookup"><span data-stu-id="99e37-129"><em>DDL</em></span></span></p></td>
<td><p><span data-ttu-id="99e37-130">可选</span><span class="sxs-lookup"><span data-stu-id="99e37-130">Optional</span></span></p></td>
<td><p><span data-ttu-id="99e37-131"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="99e37-131"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="99e37-132">一个 <strong>Variant</strong>（<strong>Boolean</strong> 子类型），用于指示 <strong>Property</strong> 是否为 DDL 对象。</span><span class="sxs-lookup"><span data-stu-id="99e37-132">A <strong>Variant</strong> (<strong>Boolean</strong> subtype) that indicates whether or not the <strong>Property</strong> is a DDL object.</span></span> <span data-ttu-id="99e37-133">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="99e37-133">The default is False.</span></span> <span data-ttu-id="99e37-134">如果 DDL 为 True, 则用户不能更改或删除此<strong>属性</strong>对象, 除非他们具有 dbSecWriteDef 权限。</span><span class="sxs-lookup"><span data-stu-id="99e37-134">If DDL is True, users can't change or delete this <strong>Property</strong> object unless they have dbSecWriteDef permission.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="99e37-135">返回值</span><span class="sxs-lookup"><span data-stu-id="99e37-135">Return value</span></span>

<span data-ttu-id="99e37-136">属性</span><span class="sxs-lookup"><span data-stu-id="99e37-136">Property</span></span>

## <a name="remarks"></a><span data-ttu-id="99e37-137">注解</span><span class="sxs-lookup"><span data-stu-id="99e37-137">Remarks</span></span>

<span data-ttu-id="99e37-138">只能在某个对象的永久 [**Properties**](properties-collection-dao.md) 集合中创建用户定义的 **Property** 对象。</span><span class="sxs-lookup"><span data-stu-id="99e37-138">You can create a user-defined **Property** object only in the **[Properties](properties-collection-dao.md)** collection of an object that is persistent.</span></span>

<span data-ttu-id="99e37-p106">如果使用 **CreateProperty** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅 **Name**、 **Type** 和 **Value** 属性主题。</span><span class="sxs-lookup"><span data-stu-id="99e37-p106">If you omit one or more of the optional parts when you use **CreateProperty**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the object, you can alter some but not all of its property settings. See the **Name**, **Type**, and **Value** property topics for more details.</span></span>

<span data-ttu-id="99e37-142">如果 name 引用了已经是集合成员的对象, 则当您使用**[Append](fields-append-method-dao.md)** 方法时, 将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="99e37-142">If name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="99e37-143">若要从集合中删除用户定义的 **Property** 对象，请对 **[Properties](fields-delete-method-dao.md)** 集合使用 **Delete** 方法。</span><span class="sxs-lookup"><span data-stu-id="99e37-143">To remove a user-defined **Property** object from the collection, use the **[Delete](fields-delete-method-dao.md)** method on the **Properties** collection.</span></span> <span data-ttu-id="99e37-144">不能删除内置属性。</span><span class="sxs-lookup"><span data-stu-id="99e37-144">You can't delete built-in properties.</span></span>

> [!NOTE]
> <span data-ttu-id="99e37-145">如果省略了 DDL 参数, 它的默认值为 False (非 DDL)。</span><span class="sxs-lookup"><span data-stu-id="99e37-145">If you omit the DDL argument, it defaults to False (non-DDL).</span></span> <span data-ttu-id="99e37-146">由于没有公开相应的 DDL 属性，必须删除要从 DDL 更改为非 DDL 的 **Property** 对象，然后重新创建该对象。</span><span class="sxs-lookup"><span data-stu-id="99e37-146">Because no corresponding DDL property is exposed, you must delete and re-create a **Property** object you want to change from DDL to non-DDL.</span></span>


## <a name="example"></a><span data-ttu-id="99e37-147">示例</span><span class="sxs-lookup"><span data-stu-id="99e37-147">Example</span></span>

<span data-ttu-id="99e37-p109">以下示例尝试设置用户定义的属性的值。如果该属性不存在，则使用 **CreateProperty** 方法创建一个新属性并设置其值。若要使该过程运行，需要使用 SetProperty 过程。</span><span class="sxs-lookup"><span data-stu-id="99e37-p109">This example tries to set the value of a user-defined property. If the property doesn't exist, it uses the **CreateProperty** method to create and set the value of the new property. The SetProperty procedure is required for this procedure to run.</span></span>

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
