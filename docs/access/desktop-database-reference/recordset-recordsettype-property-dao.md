---
title: Recordset 属性 (DAO)
TOCTitle: RecordsetType Property
ms:assetid: a66d4043-08cc-ead1-f9ff-efc7d7ea21bf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821178(v=office.15)
ms:contentKeyID: 48546853
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm13361
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 64f7dda8bec7806ef510d265deab350dc3cdad6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307628"
---
# <a name="recordsetrecordsettype-property-dao"></a><span data-ttu-id="ae2ce-102">Recordset 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="ae2ce-102">Recordset.RecordsetType property (DAO)</span></span>

<span data-ttu-id="ae2ce-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ae2ce-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ae2ce-104">使用 **RecordsetType** 属性可以指定何种类型的记录集可以在窗体中使用。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-104">You can use the **RecordsetType** property to specify what kind of recordset is made available to a form.</span></span> <span data-ttu-id="ae2ce-105">**Byte** 型，可读写。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-105">Read/write **Byte**.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae2ce-106">语法</span><span class="sxs-lookup"><span data-stu-id="ae2ce-106">Syntax</span></span>

<span data-ttu-id="ae2ce-107">*表达式*。设</span><span class="sxs-lookup"><span data-stu-id="ae2ce-107">*expression* .RecordsetType</span></span>

<span data-ttu-id="ae2ce-108">*expression*：表示 **Form** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-108">*expression* A variable that represents a **Form** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae2ce-109">注解</span><span class="sxs-lookup"><span data-stu-id="ae2ce-109">Remarks</span></span>

<span data-ttu-id="ae2ce-110">**RecordsetType** 属性在 Microsoft Access 数据库 中使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="ae2ce-110">The **RecordsetType** property uses the following settings in a Microsoft Access database.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ae2ce-111">Setting</span><span class="sxs-lookup"><span data-stu-id="ae2ce-111">Setting</span></span></p></th>
<th><p><span data-ttu-id="ae2ce-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="ae2ce-112">Type of Recordset</span></span></p></th>
<th><p><span data-ttu-id="ae2ce-113">说明</span><span class="sxs-lookup"><span data-stu-id="ae2ce-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae2ce-114">0</span><span class="sxs-lookup"><span data-stu-id="ae2ce-114">0</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-115">可见</span><span class="sxs-lookup"><span data-stu-id="ae2ce-115">Dynaset</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-116">（默认值）可以对基于单个表或基于具有一对一关系的多个表的绑定控件进行编辑。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-116">(Default) You can edit bound controls based on a single table or tables with a one-to-one relationship.</span></span> <span data-ttu-id="ae2ce-117">对于基于具有一对多关系的表绑定到字段的控件, 不能编辑关系&quot;一&quot;方的联接字段中的数据, 除非在表之间启用了级联更新。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-117">For controls bound to fields based on tables with a one-to-many relationship, you can't edit data from the join field on the &quot;one&quot; side of the relationship unless cascade update is enabled between the tables.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2ce-118">1</span><span class="sxs-lookup"><span data-stu-id="ae2ce-118">1</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-119">动态集（不一致的更新）</span><span class="sxs-lookup"><span data-stu-id="ae2ce-119">Dynaset (Inconsistent Updates)</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-120">所有绑定到其字段的表和控件都可以编辑。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-120">All tables and controls bound to their fields can be edited.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae2ce-121">双面</span><span class="sxs-lookup"><span data-stu-id="ae2ce-121">2</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-122">概述</span><span class="sxs-lookup"><span data-stu-id="ae2ce-122">Snapshot</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-123">绑定到其字段的表和控件都不能编辑。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-123">No tables or the controls bound to their fields can be edited.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ae2ce-124">[!注释] 如果不希望在窗体位于窗体视图或数据表视图中时编辑绑定控件中的数据，可将 **RecordsetType** 属性设置为 2。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-124">If you don't want data in bound controls to be edited when a form is in Form view or Datasheet view, you can set the **RecordsetType** property to 2.</span></span>

<span data-ttu-id="ae2ce-125">**RecordsetType** 属性在 Microsoft Access 项目 (.adp) 中使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="ae2ce-125">The **RecordsetType** property uses the following settings in a Microsoft Access project (.adp).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ae2ce-126">Setting</span><span class="sxs-lookup"><span data-stu-id="ae2ce-126">Setting</span></span></p></th>
<th><p><span data-ttu-id="ae2ce-127">记录集类型</span><span class="sxs-lookup"><span data-stu-id="ae2ce-127">Type of Recordset</span></span></p></th>
<th><p><span data-ttu-id="ae2ce-128">说明</span><span class="sxs-lookup"><span data-stu-id="ae2ce-128">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae2ce-129">第三章</span><span class="sxs-lookup"><span data-stu-id="ae2ce-129">3</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-130">概述</span><span class="sxs-lookup"><span data-stu-id="ae2ce-130">Snapshot</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-131">绑定到其字段的表和控件都不能编辑。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-131">No tables or the controls bound to their fields can be edited.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae2ce-132">4</span><span class="sxs-lookup"><span data-stu-id="ae2ce-132">4</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-133">可更新快照</span><span class="sxs-lookup"><span data-stu-id="ae2ce-133">Updatable Snapshot</span></span></p></td>
<td><p><span data-ttu-id="ae2ce-134">（默认值）所有绑定到其字段的表和控件都可以编辑。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-134">(Default) All tables and controls bound to their fields can be edited.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="ae2ce-135">[!注释] 更改打开的窗体或报表的 **RecordsetType** 属性时，将会引起自动重新创建记录集。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-135">Changing the **RecordsetType** property of an open form or report causes an automatic recreation of the recordset.</span></span>

<span data-ttu-id="ae2ce-p103">可以基于其字段绑定到窗体控件的多个基础表创建窗体。根据 **RecordsetType** 属性设置的不同，可以设置能够编辑哪些绑定控件。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-p103">You can create forms based on multiple underlying tables with fields bound to controls on the forms. Depending on the **RecordsetType** property setting, you can limit which of these bound controls can be edited.</span></span>

<span data-ttu-id="ae2ce-138">除了由数据集提供的编辑控件\*\*\*\* 之外, 窗体上的每个控件都有一个**锁定**属性, 您可以设置该属性来指定是否可以编辑控件及其基础数据。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-138">In addition to the editing control provided by **RecordsetType**, each control on a form has a **Locked** property that you can set to specify whether the control and its underlying data can be edited.</span></span> <span data-ttu-id="ae2ce-139">如果 **Locked** 属性设为"是"，则不能编辑数据。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-139">If the **Locked** property is set to Yes, you can't edit the data.</span></span>

## <a name="example"></a><span data-ttu-id="ae2ce-140">示例</span><span class="sxs-lookup"><span data-stu-id="ae2ce-140">Example</span></span>

<span data-ttu-id="ae2ce-141">在下面的示例中，只有当用户 ID 为 ADMIN 时，才允许更新记录。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-141">In the following example, only if the user ID is ADMIN can records be updated.</span></span> <span data-ttu-id="ae2ce-142">如果公共变量的值不是 ADMIN，则该代码示例会将 gstrUserID**RecordsetType** 属性设置为“快照”。</span><span class="sxs-lookup"><span data-stu-id="ae2ce-142">This code sample sets the **RecordsetType** property to Snapshot if the public variable gstrUserID value is not ADMIN.</span></span>

```vb
    Sub Form_Open(Cancel As Integer) 
     Const conSnapshot = 2 
     If gstrUserID <> "ADMIN" Then 
     Forms!Employees.RecordsetType = conSnapshot 
     End If 
    End Sub
```

## <a name="see-also"></a><span data-ttu-id="ae2ce-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae2ce-143">See also</span></span>

- [<span data-ttu-id="ae2ce-144">Form 对象</span><span class="sxs-lookup"><span data-stu-id="ae2ce-144">Form Object</span></span>](https://docs.microsoft.com/office/vba/api/Access.Form)


