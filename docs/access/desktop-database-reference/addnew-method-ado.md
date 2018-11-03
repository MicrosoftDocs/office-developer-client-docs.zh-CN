---
title: AddNew 方法 (ADO)
TOCTitle: AddNew method (ADO)
ms:assetid: bae09be0-5707-4f38-9c74-0acd0f29dbac
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249899(v=office.15)
ms:contentKeyID: 48547384
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5c4ac833f2ff7681e3a4abe77ff53928fc3f4fe2
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944562"
---
# <a name="addnew-method-ado"></a><span data-ttu-id="33b1a-102">AddNew 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="33b1a-102">AddNew method (ADO)</span></span>


<span data-ttu-id="33b1a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="33b1a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="33b1a-104">用于为可更新的 [Recordset](recordset-object-ado.md) 对象创建新记录。</span><span class="sxs-lookup"><span data-stu-id="33b1a-104">Creates a new record for an updatable [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="33b1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="33b1a-105">Syntax</span></span>

<span data-ttu-id="33b1a-106">*记录集*。AddNew *FieldList\*\*值*</span><span class="sxs-lookup"><span data-stu-id="33b1a-106">*recordset*.AddNew *FieldList*, *Values*</span></span>

## <a name="parameters"></a><span data-ttu-id="33b1a-107">参数</span><span class="sxs-lookup"><span data-stu-id="33b1a-107">Parameters</span></span>

|<span data-ttu-id="33b1a-108">参数</span><span class="sxs-lookup"><span data-stu-id="33b1a-108">Parameter</span></span>|<span data-ttu-id="33b1a-109">说明</span><span class="sxs-lookup"><span data-stu-id="33b1a-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="33b1a-110">*recordset*</span><span class="sxs-lookup"><span data-stu-id="33b1a-110">*recordset*</span></span> |<span data-ttu-id="33b1a-111">**Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="33b1a-111">A **Recordset** object.</span></span>|
|<span data-ttu-id="33b1a-112">*FieldList*</span><span class="sxs-lookup"><span data-stu-id="33b1a-112">*FieldList*</span></span> |<span data-ttu-id="33b1a-p101">可选。单个名称，或新记录中字段名称或序号位置的数组。</span><span class="sxs-lookup"><span data-stu-id="33b1a-p101">Optional. A single name, or an array of names or ordinal positions of the fields in the new record.</span></span>|
|<span data-ttu-id="33b1a-115">*Values*</span><span class="sxs-lookup"><span data-stu-id="33b1a-115">*Values*</span></span> |<span data-ttu-id="33b1a-116">可选。</span><span class="sxs-lookup"><span data-stu-id="33b1a-116">Optional.</span></span> <span data-ttu-id="33b1a-117">单个值，或新记录中字段值的数组。</span><span class="sxs-lookup"><span data-stu-id="33b1a-117">A single value, or an array of values for the fields in the new record.</span></span> <span data-ttu-id="33b1a-118">如果*Fieldlist*是一个数组，*值*还必须具有相同数量的成员; 数组否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="33b1a-118">If *Fieldlist* is an array, *Values* must also be an array with the same number of members; otherwise, an error occurs.</span></span> <span data-ttu-id="33b1a-119">在每个数组中，字段名称的次序必须与字段值的次序匹配。</span><span class="sxs-lookup"><span data-stu-id="33b1a-119">The order of field names must match the order of field values in each array.</span></span>|

## <a name="remarks"></a><span data-ttu-id="33b1a-120">备注</span><span class="sxs-lookup"><span data-stu-id="33b1a-120">Remarks</span></span>

<span data-ttu-id="33b1a-p103">**AddNew** 方法用于创建和初始化新记录。可以结合使用 [Supports](supports-method-ado.md) 方法和 **adAddNew** （ [CursorOptionEnum](cursoroptionenum.md) 值），以检验能否在当前 **Recordset** 对象中添加记录。</span><span class="sxs-lookup"><span data-stu-id="33b1a-p103">Use the **AddNew** method to create and initialize a new record. Use the [Supports](supports-method-ado.md) method with **adAddNew** (a [CursorOptionEnum](cursoroptionenum.md) value) to verify whether you can add records to the current **Recordset** object.</span></span>

<span data-ttu-id="33b1a-p104">调用 **AddNew** 方法之后，新记录将变为当前记录，并在调用 [Update](update-method-ado.md) 方法之后保持为当前记录。由于新记录将追加到 **Recordset** ，因此，如果在调用 Update 之后调用 **MoveNext** ，则将移动到 **Recordset** 结尾之后，从而使 **EOF** 为 True。如果 **Recordset** 对象不支持书签，那么一旦您移动到其他记录，便可能无法访问新记录。根据游标类型的不同，您可能需要调用 [Requery](requery-method-ado.md) 方法以使新记录可访问。</span><span class="sxs-lookup"><span data-stu-id="33b1a-p104">After you call the **AddNew** method, the new record becomes the current record and remains current after you call the [Update](update-method-ado.md) method. Since the new record is appended to the **Recordset**, a call to **MoveNext** following the Update will move past the end of the **Recordset**, making **EOF** True. If the **Recordset** object does not support bookmarks, you may not be able to access the new record once you move to another record. Depending on your cursor type, you may need to call the [Requery](requery-method-ado.md) method to make the new record accessible.</span></span>

<span data-ttu-id="33b1a-127">如果在编辑当前记录或添加新记录时调用 **AddNew** ，则 ADO 会调用 **Update** 方法来保存所有更改，然后创建新记录。</span><span class="sxs-lookup"><span data-stu-id="33b1a-127">If you call **AddNew** while editing the current record or while adding a new record, ADO calls the **Update** method to save any changes and then creates the new record.</span></span>

<span data-ttu-id="33b1a-128">**AddNew**方法的行为取决于**Recordset**对象以及是否传递*Fieldlist*和*Values*参数的更新模式。</span><span class="sxs-lookup"><span data-stu-id="33b1a-128">The behavior of the **AddNew** method depends on the updating mode of the **Recordset** object and whether you pass the *Fieldlist* and *Values* arguments.</span></span>

<span data-ttu-id="33b1a-p105">在*即时更新模式*下（在该模式下，只要调用 **Update** 方法，提供程序便将更改写入基础数据源），不采用参数调用 **AddNew** 参数会将 [EditMode](editmode-property-ado.md) 属性设置为 **adEditAdd**（[EditModeEnum](editmodeenum.md) 值）。提供程序将任意字段值更改缓存在本地。调用 **Update** 方法会将新记录发布到数据库并将 **EditMode** 属性重置为 **adEditNone**（**EditModeEnum** 值）。如果传递 *Fieldlist* 和 *Values* 参数，则 ADO 立即将新记录发布到数据库（无需调用 **Update**），且 **EditMode** 属性值不变 (**adEditNone**)。</span><span class="sxs-lookup"><span data-stu-id="33b1a-p105">In *immediate update mode* (in which the provider writes changes to the underlying data source once you call the **Update** method), calling the **AddNew** method without arguments sets the [EditMode](editmode-property-ado.md) property to **adEditAdd** (an [EditModeEnum](editmodeenum.md) value). The provider caches any field value changes locally. Calling the **Update** method posts the new record to the database and resets the **EditMode** property to **adEditNone** (an **EditModeEnum** value). If you pass the *Fieldlist* and *Values* arguments, ADO immediately posts the new record to the database (no **Update** call is necessary); the **EditMode** property value does not change (**adEditNone**).</span></span>

<span data-ttu-id="33b1a-133">以*批更新模式*（顺序提供程序缓存多个更改和将它们写入到基础数据源，仅在调用[UpdateBatch](updatebatch-method-ado.md)方法），调用不带参数的**AddNew**方法将**EditMode**设置属性设置为**adEditAdd**。</span><span class="sxs-lookup"><span data-stu-id="33b1a-133">In *batch update mode* (in which the provider caches multiple changes and writes them to the underlying data source only when you call the [UpdateBatch](updatebatch-method-ado.md) method), calling the **AddNew** method without arguments sets the **EditMode** property to **adEditAdd**.</span></span> <span data-ttu-id="33b1a-134">提供程序在本地缓存所有字段值的更改。</span><span class="sxs-lookup"><span data-stu-id="33b1a-134">The provider caches any field value changes locally.</span></span> <span data-ttu-id="33b1a-135">调用 **Update** 方法会将新记录添加到当前 **Recordset** 并将 **EditMode** 属性重新设置为 **adEditNone** ，但是在调用 **UpdateBatch** 方法之前，提供程序不会将更改张贴到基础数据库中。</span><span class="sxs-lookup"><span data-stu-id="33b1a-135">Calling the **Update** method adds the new record to the current **Recordset** and resets the **EditMode** property to **adEditNone**, but the provider does not post the changes to the underlying database until you call the **UpdateBatch** method.</span></span> <span data-ttu-id="33b1a-136">如果传递*Fieldlist*和*Values*参数，ADO 将新记录发送到用于存储缓存; 中的提供程序您需要调用**UpdateBatch**方法发布到基础数据库的新记录。</span><span class="sxs-lookup"><span data-stu-id="33b1a-136">If you pass the *Fieldlist* and *Values* arguments, ADO sends the new record to the provider for storage in a cache; you need to call the **UpdateBatch** method to post the new record to the underlying database.</span></span>

