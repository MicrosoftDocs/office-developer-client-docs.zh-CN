---
title: Field2.CreateProperty 方法 (DAO)
TOCTitle: CreateProperty Method
ms:assetid: bdbd6bec-216f-138e-78df-9c3221692aa4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822737(v=office.15)
ms:contentKeyID: 48547446
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9488da95e9e95d1b474d6121546ff09083566f93
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998670"
---
# <a name="field2createproperty-method-dao"></a><span data-ttu-id="bfdfc-102">Field2.CreateProperty 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bfdfc-102">Field2.CreateProperty method (DAO)</span></span>

<span data-ttu-id="bfdfc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bfdfc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bfdfc-104">创建一个新的用户定义的 **[Property](property-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-104">Creates a new user-defined **[Property](property-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="bfdfc-105">语法</span><span class="sxs-lookup"><span data-stu-id="bfdfc-105">Syntax</span></span>

<span data-ttu-id="bfdfc-106">*表达式*。CreateProperty （***名称***、***类型***、***值***、 ***DDL***）</span><span class="sxs-lookup"><span data-stu-id="bfdfc-106">*expression* .CreateProperty(***Name***, ***Type***, ***Value***, ***DDL***)</span></span>

<span data-ttu-id="bfdfc-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="bfdfc-108">参数</span><span class="sxs-lookup"><span data-stu-id="bfdfc-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bfdfc-109">名称</span><span class="sxs-lookup"><span data-stu-id="bfdfc-109">Name</span></span></p></th>
<th><p><span data-ttu-id="bfdfc-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="bfdfc-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="bfdfc-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="bfdfc-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="bfdfc-112">说明</span><span class="sxs-lookup"><span data-stu-id="bfdfc-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfdfc-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="bfdfc-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-114">可选</span><span class="sxs-lookup"><span data-stu-id="bfdfc-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="bfdfc-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bfdfc-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-p101">一个对新的 <strong>Property</strong> 对象进行唯一命名的 <strong>String</strong>。有关有效 <strong>Property</strong> 名称的详细信息，请参阅 <strong>Name</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-p101">A <strong>String</strong> that uniquely names the new <strong>Property</strong> object. See the <strong>Name</strong> property for details on valid <strong>Property</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfdfc-118"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="bfdfc-118"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-119">可选</span><span class="sxs-lookup"><span data-stu-id="bfdfc-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="bfdfc-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bfdfc-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-p102">一个定义新的 <strong>Property</strong> 对象的数据类型的常量。有关有效数据类型的信息，请参阅 <strong><a href="field-type-property-dao.md">Type</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-p102">A constant that defines the data type of the new <strong>Property</strong> object. See the <strong><a href="field-type-property-dao.md">Type</a></strong> property for valid data types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfdfc-123"><em>Value</em></span><span class="sxs-lookup"><span data-stu-id="bfdfc-123"><em>Value</em></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-124">可选</span><span class="sxs-lookup"><span data-stu-id="bfdfc-124">Optional</span></span></p></td>
<td><p><span data-ttu-id="bfdfc-125"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bfdfc-125"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-p103">一个包含初始属性值的 <strong>Variant</strong>。有关详细信息，请参阅 <strong><a href="field-value-property-dao.md">Value</a></strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-p103">A <strong>Variant</strong> containing the initial property value. See the <strong><a href="field-value-property-dao.md">Value</a></strong> property for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfdfc-128"><em>DDL</em></span><span class="sxs-lookup"><span data-stu-id="bfdfc-128"><em>DDL</em></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-129">可选</span><span class="sxs-lookup"><span data-stu-id="bfdfc-129">Optional</span></span></p></td>
<td><p><span data-ttu-id="bfdfc-130"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="bfdfc-130"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="bfdfc-131"><strong>Variant</strong> （<strong>布尔</strong>子类型），该值指示<strong>属性</strong>DDL 对象。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-131">A <strong>Variant</strong> (<strong>Boolean</strong> subtype) that indicates whether or not the <strong>Property</strong> is a DDL object.</span></span> <span data-ttu-id="bfdfc-132">默认值为 <strong>False</strong> 。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-132">The default is <strong>False</strong>.</span></span> <span data-ttu-id="bfdfc-133">如果 DDL 为<strong>True</strong>，则用户无法更改或删除此<strong>Property</strong>对象，除非他们具有<strong>dbSecWriteDef</strong>权限。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-133">If DDL is <strong>True</strong>, users can't change or delete this <strong>Property</strong> object unless they have <strong>dbSecWriteDef</strong> permission.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="bfdfc-134">返回值</span><span class="sxs-lookup"><span data-stu-id="bfdfc-134">Return value</span></span>

<span data-ttu-id="bfdfc-135">属性</span><span class="sxs-lookup"><span data-stu-id="bfdfc-135">Property</span></span>

## <a name="remarks"></a><span data-ttu-id="bfdfc-136">注解</span><span class="sxs-lookup"><span data-stu-id="bfdfc-136">Remarks</span></span>

<span data-ttu-id="bfdfc-137">只能在某个对象的永久 [**Properties**](properties-collection-dao.md) 集合中创建用户定义的 **Property** 对象。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-137">You can create a user-defined **Property** object only in the **[Properties](properties-collection-dao.md)** collection of an object that is persistent.</span></span>

<span data-ttu-id="bfdfc-p105">如果使用 **CreateProperty** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅 **Name**、 **Type** 和 **Value** 属性主题。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-p105">If you omit one or more of the optional parts when you use **CreateProperty**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the object, you can alter some but not all of its property settings. See the **Name**, **Type**, and **Value** property topics for more details.</span></span>

<span data-ttu-id="bfdfc-141">如果 name 引用对象的已经是集合的成员，使用**[Append](fields-append-method-dao.md)** 方法时，发生此事件运行时错误。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-141">If name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="bfdfc-p106">若要从集合中删除用户定义的 **Property** 对象，请对 **[Properties](fields-delete-method-dao.md)** 集合使用 **[Delete](properties-collection-dao.md)** 方法。不能删除内置属性。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-p106">To remove a user-defined **Property** object from the collection, use the **[Delete](fields-delete-method-dao.md)** method on the **[Properties](properties-collection-dao.md)** collection. You can't delete built-in properties.</span></span>


> [!NOTE]
> <span data-ttu-id="bfdfc-144">如果省略 DDL 参数，则默认为 False (非 DDL)。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-144">If you omit the DDL argument, it defaults to False (non-DDL).</span></span> <span data-ttu-id="bfdfc-145">由于没有公开相应的 DDL 属性，必须删除要从 DDL 更改为非 DDL 的 **Property** 对象，然后重新创建该对象。</span><span class="sxs-lookup"><span data-stu-id="bfdfc-145">Because no corresponding DDL property is exposed, you must delete and re-create a **Property** object you want to change from DDL to non-DDL.</span></span>


