---
title: Recordset.RecordsetType Property (DAO)
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
ms.openlocfilehash: 043437a893eaba53ff89e7e77c018b19ebd38b5c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468449"
---
# <a name="recordsetrecordsettype-property-dao"></a><span data-ttu-id="65673-102">Recordset.RecordsetType Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="65673-102">Recordset.RecordsetType Property (DAO)</span></span>

<span data-ttu-id="65673-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="65673-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="65673-p101">使用 **RecordsetType** 属性可以指定何种类型的记录集可以在窗体中使用。 **Byte** 型，可读写。</span><span class="sxs-lookup"><span data-stu-id="65673-p101">You can use the **RecordsetType** property to specify what kind of recordset is made available to a form. Read/write **Byte**.</span></span>

## <a name="syntax"></a><span data-ttu-id="65673-106">语法</span><span class="sxs-lookup"><span data-stu-id="65673-106">Syntax</span></span>

<span data-ttu-id="65673-107">*表达式*。RecordsetType</span><span class="sxs-lookup"><span data-stu-id="65673-107">*expression* .RecordsetType</span></span>

<span data-ttu-id="65673-108">*expression* 一个代表 **表单** 对象的变量。</span><span class="sxs-lookup"><span data-stu-id="65673-108">*expression* A variable that represents a **Form** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="65673-109">注解</span><span class="sxs-lookup"><span data-stu-id="65673-109">Remarks</span></span>

<span data-ttu-id="65673-110">**RecordsetType** 属性在 Microsoft Access 数据库 中使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="65673-110">The **RecordsetType** property uses the following settings in a Microsoft Access database.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="65673-111">设置</span><span class="sxs-lookup"><span data-stu-id="65673-111">Setting</span></span></p></th>
<th><p><span data-ttu-id="65673-112">记录集类型</span><span class="sxs-lookup"><span data-stu-id="65673-112">Type of Recordset</span></span></p></th>
<th><p><span data-ttu-id="65673-113">说明</span><span class="sxs-lookup"><span data-stu-id="65673-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65673-114">0</span><span class="sxs-lookup"><span data-stu-id="65673-114">0</span></span></p></td>
<td><p><span data-ttu-id="65673-115">动态集</span><span class="sxs-lookup"><span data-stu-id="65673-115">Dynaset</span></span></p></td>
<td><p><span data-ttu-id="65673-116">（默认值）您可以编辑基于单个表或具有一对一关系的表绑定的控件。</span><span class="sxs-lookup"><span data-stu-id="65673-116">(Default) You can edit bound controls based on a single table or tables with a one-to-one relationship.</span></span> <span data-ttu-id="65673-117">对于基于具有-一对多关系的表的字段绑定控件，您不能编辑的联接字段中的数据，在&quot;一个&quot;除非级联更新启用表之间的关系侧。</span><span class="sxs-lookup"><span data-stu-id="65673-117">For controls bound to fields based on tables with a one-to-many relationship, you can't edit data from the join field on the &quot;one&quot; side of the relationship unless cascade update is enabled between the tables.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65673-118">1</span><span class="sxs-lookup"><span data-stu-id="65673-118">1</span></span></p></td>
<td><p><span data-ttu-id="65673-119">动态集（不一致的更新）</span><span class="sxs-lookup"><span data-stu-id="65673-119">Dynaset (Inconsistent Updates)</span></span></p></td>
<td><p><span data-ttu-id="65673-120">所有绑定到其字段的表和控件都可以编辑。</span><span class="sxs-lookup"><span data-stu-id="65673-120">All tables and controls bound to their fields can be edited.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65673-121">2</span><span class="sxs-lookup"><span data-stu-id="65673-121">2</span></span></p></td>
<td><p><span data-ttu-id="65673-122">快照</span><span class="sxs-lookup"><span data-stu-id="65673-122">Snapshot</span></span></p></td>
<td><p><span data-ttu-id="65673-123">绑定到其字段的表和控件都不能编辑。</span><span class="sxs-lookup"><span data-stu-id="65673-123">No tables or the controls bound to their fields can be edited.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="65673-124">[!注释] 如果不希望在窗体位于窗体视图或数据表视图中时编辑绑定控件中的数据，可将 **RecordsetType** 属性设置为 2。</span><span class="sxs-lookup"><span data-stu-id="65673-124">If you don't want data in bound controls to be edited when a form is in Form view or Datasheet view, you can set the **RecordsetType** property to 2.</span></span>



<span data-ttu-id="65673-125">**RecordsetType** 属性在 Microsoft Access 项目 (.adp) 中使用以下设置：</span><span class="sxs-lookup"><span data-stu-id="65673-125">The **RecordsetType** property uses the following settings in a Microsoft Access project (.adp).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="65673-126">设置</span><span class="sxs-lookup"><span data-stu-id="65673-126">Setting</span></span></p></th>
<th><p><span data-ttu-id="65673-127">记录集类型</span><span class="sxs-lookup"><span data-stu-id="65673-127">Type of Recordset</span></span></p></th>
<th><p><span data-ttu-id="65673-128">说明</span><span class="sxs-lookup"><span data-stu-id="65673-128">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65673-129">3</span><span class="sxs-lookup"><span data-stu-id="65673-129">3</span></span></p></td>
<td><p><span data-ttu-id="65673-130">快照</span><span class="sxs-lookup"><span data-stu-id="65673-130">Snapshot</span></span></p></td>
<td><p><span data-ttu-id="65673-131">绑定到其字段的表和控件都不能编辑。</span><span class="sxs-lookup"><span data-stu-id="65673-131">No tables or the controls bound to their fields can be edited.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65673-132">4</span><span class="sxs-lookup"><span data-stu-id="65673-132">4</span></span></p></td>
<td><p><span data-ttu-id="65673-133">可更新快照</span><span class="sxs-lookup"><span data-stu-id="65673-133">Updatable Snapshot</span></span></p></td>
<td><p><span data-ttu-id="65673-134">（默认值）所有绑定到其字段的表和控件都可以编辑。</span><span class="sxs-lookup"><span data-stu-id="65673-134">(Default) All tables and controls bound to their fields can be edited.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <span data-ttu-id="65673-135">[!注释] 更改打开的窗体或报表的 **RecordsetType** 属性时，将会引起自动重新创建记录集。</span><span class="sxs-lookup"><span data-stu-id="65673-135">Changing the **RecordsetType** property of an open form or report causes an automatic recreation of the recordset.</span></span>



<span data-ttu-id="65673-p103">可以基于其字段绑定到窗体控件的多个基础表创建窗体。根据 **RecordsetType** 属性设置的不同，可以设置能够编辑哪些绑定控件。</span><span class="sxs-lookup"><span data-stu-id="65673-p103">You can create forms based on multiple underlying tables with fields bound to controls on the forms. Depending on the **RecordsetType** property setting, you can limit which of these bound controls can be edited.</span></span>

<span data-ttu-id="65673-138">除了由**RecordsetType**提供的编辑控件，窗体上的每个控件具有**Locked**属性可设置来指定是否可编辑控件和其基础数据。</span><span class="sxs-lookup"><span data-stu-id="65673-138">In addition to the editing control provided by **RecordsetType**, each control on a form has a **Locked** property that you can set to specify whether the control and its underlying data can be edited.</span></span> <span data-ttu-id="65673-139">如果 **Locked** 属性设为"是"，则不能编辑数据。</span><span class="sxs-lookup"><span data-stu-id="65673-139">If the **Locked** property is set to Yes, you can't edit the data.</span></span>

## <a name="example"></a><span data-ttu-id="65673-140">示例</span><span class="sxs-lookup"><span data-stu-id="65673-140">Example</span></span>

<span data-ttu-id="65673-p105">在下面的示例中，只有当用户 ID 为 ADMIN 时，才允许更新记录。如果公共变量的值不是 ADMIN，则该代码示例会将 gstrUserID**RecordsetType** 属性设置为“快照”。</span><span class="sxs-lookup"><span data-stu-id="65673-p105">In the following example, only if the user ID is ADMIN can records be updated. This code sample sets the **RecordsetType** property to Snapshot if the public variable gstrUserID value is not ADMIN.</span></span>

```vb
    Sub Form_Open(Cancel As Integer) 
     Const conSnapshot = 2 
     If gstrUserID <> "ADMIN" Then 
     Forms!Employees.RecordsetType = conSnapshot 
     End If 
    End Sub
```

## <a name="see-also"></a><span data-ttu-id="65673-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65673-143">See also</span></span>

- [<span data-ttu-id="65673-144">Form 对象</span><span class="sxs-lookup"><span data-stu-id="65673-144">Form Object</span></span>](https://docs.microsoft.com/office/vba/api/Access.Form)


