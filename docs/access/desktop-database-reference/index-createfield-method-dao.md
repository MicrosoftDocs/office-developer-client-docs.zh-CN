---
title: CreateField 方法 (DAO)
TOCTitle: CreateField Method
ms:assetid: fc82b785-8768-b144-a2a4-c1f1798865a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837208(v=office.15)
ms:contentKeyID: 48548892
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aedda14273446ff6823776e535eb7995aa127fa5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291829"
---
# <a name="indexcreatefield-method-dao"></a><span data-ttu-id="0d56f-102">CreateField 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="0d56f-102">Index.CreateField method (DAO)</span></span>

<span data-ttu-id="0d56f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0d56f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0d56f-104">创建一个新的 **[Field](field-object-dao.md)** 对象（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="0d56f-104">Creates a new **[Field](field-object-dao.md)** object (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="0d56f-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d56f-105">Syntax</span></span>

<span data-ttu-id="0d56f-106">*表达式*。CreateField (***名称***、***类型***、***大小***)</span><span class="sxs-lookup"><span data-stu-id="0d56f-106">*expression* .CreateField(***Name***, ***Type***, ***Size***)</span></span>

<span data-ttu-id="0d56f-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0d56f-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="0d56f-108">参数</span><span class="sxs-lookup"><span data-stu-id="0d56f-108">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0d56f-109">名称</span><span class="sxs-lookup"><span data-stu-id="0d56f-109">Name</span></span></p></th>
<th><p><span data-ttu-id="0d56f-110">必需/可选</span><span class="sxs-lookup"><span data-stu-id="0d56f-110">Required/optional</span></span></p></th>
<th><p><span data-ttu-id="0d56f-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="0d56f-111">Data type</span></span></p></th>
<th><p><span data-ttu-id="0d56f-112">说明</span><span class="sxs-lookup"><span data-stu-id="0d56f-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d56f-113"><em>Name</em></span><span class="sxs-lookup"><span data-stu-id="0d56f-113"><em>Name</em></span></span></p></td>
<td><p><span data-ttu-id="0d56f-114">可选</span><span class="sxs-lookup"><span data-stu-id="0d56f-114">Optional</span></span></p></td>
<td><p><span data-ttu-id="0d56f-115"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="0d56f-115"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="0d56f-116">一个 String 类型的值，用于对新的 <strong>Field</strong> 对象进行唯一命名。</span><span class="sxs-lookup"><span data-stu-id="0d56f-116">A String that uniquely names the new <strong>Field</strong> object.</span></span> <span data-ttu-id="0d56f-117">有关有效<strong>字段</strong>名称的详细信息, 请参阅<strong><a href="connection-name-property-dao.md">Name</a></strong>属性。</span><span class="sxs-lookup"><span data-stu-id="0d56f-117">See the <strong><a href="connection-name-property-dao.md">Name</a></strong> property for details on valid <strong>Field</strong> names.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d56f-118"><em>Type</em></span><span class="sxs-lookup"><span data-stu-id="0d56f-118"><em>Type</em></span></span></p></td>
<td><p><span data-ttu-id="0d56f-119">可选</span><span class="sxs-lookup"><span data-stu-id="0d56f-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="0d56f-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="0d56f-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="0d56f-121">此对象不支持的参数。</span><span class="sxs-lookup"><span data-stu-id="0d56f-121">Argument not supported for this object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d56f-122"><em>Size</em></span><span class="sxs-lookup"><span data-stu-id="0d56f-122"><em>Size</em></span></span></p></td>
<td><p><span data-ttu-id="0d56f-123">可选</span><span class="sxs-lookup"><span data-stu-id="0d56f-123">Optional</span></span></p></td>
<td><p><span data-ttu-id="0d56f-124"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="0d56f-124"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="0d56f-125">此对象不支持的参数。</span><span class="sxs-lookup"><span data-stu-id="0d56f-125">Argument not supported for this object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a><span data-ttu-id="0d56f-126">返回值</span><span class="sxs-lookup"><span data-stu-id="0d56f-126">Return value</span></span>

<span data-ttu-id="0d56f-127">Field</span><span class="sxs-lookup"><span data-stu-id="0d56f-127">Field</span></span>

## <a name="remarks"></a><span data-ttu-id="0d56f-128">注解</span><span class="sxs-lookup"><span data-stu-id="0d56f-128">Remarks</span></span>

<span data-ttu-id="0d56f-p102">可以使用 **CreateField** 方法创建新的字段，以及指定字段的名称、数据类型和大小。如果使用 **CreateField** 时省略了一个或多个可选部分，则可以在将新对象追加到集合之前，使用适当的赋值语句设置或重置相应的属性。追加新对象后，可以改动此对象的某些（但不是所有）属性设置。有关详细信息，请参阅各个属性主题。</span><span class="sxs-lookup"><span data-stu-id="0d56f-p102">You can use the **CreateField** method to create a new field, as well as specify the name, data type, and size of the field. If you omit one or more of the optional parts when you use **CreateField**, you can use an appropriate assignment statement to set or reset the corresponding property before you append the new object to a collection. After you append the new object, you can alter some but not all of its property settings. See the individual property topics for more details.</span></span>

<span data-ttu-id="0d56f-133">type 和 size 参数仅适用于**TableDef**对象中的**Field**对象。</span><span class="sxs-lookup"><span data-stu-id="0d56f-133">The type and size arguments apply only to **Field** objects in a **TableDef** object.</span></span> <span data-ttu-id="0d56f-134">如果 **Field** 对象与 **Index** 或 **Relation** 对象关联，则会忽略这些参数。</span><span class="sxs-lookup"><span data-stu-id="0d56f-134">These arguments are ignored when a **Field** object is associated with an **Index** or **Relation** object.</span></span>

<span data-ttu-id="0d56f-135">如果 name 引用了已经是集合成员的对象, 则当您使用**[Append](fields-append-method-dao.md)** 方法时, 将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="0d56f-135">If name refers to an object that is already a member of the collection, a run-time error occurs when you use the **[Append](fields-append-method-dao.md)** method.</span></span>

<span data-ttu-id="0d56f-p104">要从 **Fields** 集合中删除 **Field** 对象，请对集合使用 **[Delete](fields-delete-method-dao.md)** 方法。创建了一个引用字段的索引后，不能从 **TableDef** 对象的 **Fields** 集合中删除 **Field** 对象。</span><span class="sxs-lookup"><span data-stu-id="0d56f-p104">To remove a **Field** object from a **Fields** collection, use the **[Delete](fields-delete-method-dao.md)** method on the collection. You can't delete a **Field** object from a **TableDef** object's **Fields** collection after you create an index that references the field.</span></span>

