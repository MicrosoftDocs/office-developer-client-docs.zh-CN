---
title: FieldStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: FieldStatusEnum
ms:assetid: 49570042-8435-8618-3ba1-7006c47735e0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249225(v=office.15)
ms:contentKeyID: 48544635
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 22c5d53427d1380273ea82b3a28ae044e103b179
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860607"
---
# <a name="fieldstatusenum"></a><span data-ttu-id="60a52-102">FieldStatusEnum</span><span class="sxs-lookup"><span data-stu-id="60a52-102">FieldStatusEnum</span></span>

<span data-ttu-id="60a52-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="60a52-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="60a52-104">指定 **Field** 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="60a52-104">Specifies the status of a **Field** object.</span></span>

<span data-ttu-id="60a52-105">**adFieldPending\*** 值指示导致设置状态的操作，可以与其他状态值一起使用。</span><span class="sxs-lookup"><span data-stu-id="60a52-105">The **adFieldPending\*** values indicate the operation that caused the status to be set, and may be combined with other status values.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="60a52-106">常量</span><span class="sxs-lookup"><span data-stu-id="60a52-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="60a52-107">值</span><span class="sxs-lookup"><span data-stu-id="60a52-107">Value</span></span></p></th>
<th><p><span data-ttu-id="60a52-108">说明</span><span class="sxs-lookup"><span data-stu-id="60a52-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60a52-109"><strong>adFieldAlreadyExists</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-109"><strong>adFieldAlreadyExists</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-110">26</span><span class="sxs-lookup"><span data-stu-id="60a52-110">26</span></span></p></td>
<td><p><span data-ttu-id="60a52-111">指示指定的字段已经存在。</span><span class="sxs-lookup"><span data-stu-id="60a52-111">Indicates that the specified field already exists.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-112"><strong>adFieldBadStatus</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-112"><strong>adFieldBadStatus</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-113">12</span><span class="sxs-lookup"><span data-stu-id="60a52-113">12</span></span></p></td>
<td><p><span data-ttu-id="60a52-p101">指示从 ADO 向 OLE DB 提供程序发送了无效的状态值。可能的原因包括 OLE DB 提供程序的版本是 1.0 或 1.1，或者 <a href="value-property-ado.md">Value 属性 (ADO)</a> 和 <a href="status-property-ado-field.md">Status 属性 (ADO Field)</a> 的组合不正确。</span><span class="sxs-lookup"><span data-stu-id="60a52-p101">Indicates that an invalid status value was sent from ADO to the OLE DB provider. Possible causes include an OLE DB 1.0 or 1.1 provider, or an improper combination of <a href="value-property-ado.md">Value</a> and <a href="status-property-ado-field.md">Status</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-116"><strong>adFieldCannotComplete</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-116"><strong>adFieldCannotComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-117">20</span><span class="sxs-lookup"><span data-stu-id="60a52-117">20</span></span></p></td>
<td><p><span data-ttu-id="60a52-118">指示由 <a href="source-property-ado-record.md">Source 属性 (ADO Record)</a> 指定的 URL 的服务器无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="60a52-118">Indicates that the server of the URL specified by <a href="source-property-ado-record.md">Source</a> could not complete the operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-119"><strong>adFieldCannotDeleteSource</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-119"><strong>adFieldCannotDeleteSource</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-120">23</span><span class="sxs-lookup"><span data-stu-id="60a52-120">23</span></span></p></td>
<td><p><span data-ttu-id="60a52-121">指示在移动操作期间，将树或子树移动到了新位置，但无法删除源。</span><span class="sxs-lookup"><span data-stu-id="60a52-121">Indicates that during a move operation, a tree or subtree was moved to a new location, but the source could not be deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-122"><strong>adFieldCantConvertValue</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-122"><strong>adFieldCantConvertValue</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-123">2</span><span class="sxs-lookup"><span data-stu-id="60a52-123">2</span></span></p></td>
<td><p><span data-ttu-id="60a52-124">指示由于丢失数据而无法检索或存储字段。</span><span class="sxs-lookup"><span data-stu-id="60a52-124">Indicates that the field cannot be retrieved or stored without loss of data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-125"><strong>adFieldCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-125"><strong>adFieldCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-126">7</span><span class="sxs-lookup"><span data-stu-id="60a52-126">7</span></span></p></td>
<td><p><span data-ttu-id="60a52-127">指示无法添加字段，因为提供程序超过了限制（如允许的字段数）。</span><span class="sxs-lookup"><span data-stu-id="60a52-127">Indicates that the field could not be added because the provider exceeded a limitation (such as the number of fields allowed).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-128"><strong>adFieldDataOverflow</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-128"><strong>adFieldDataOverflow</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-129">6</span><span class="sxs-lookup"><span data-stu-id="60a52-129">6</span></span></p></td>
<td><p><span data-ttu-id="60a52-130">指示从提供程序返回的数据使字段的数据类型发生溢出。</span><span class="sxs-lookup"><span data-stu-id="60a52-130">Indicates that the data returned from the provider overflowed the data type of the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-131"><strong>adFieldDefault</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-131"><strong>adFieldDefault</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-132">13</span><span class="sxs-lookup"><span data-stu-id="60a52-132">13</span></span></p></td>
<td><p><span data-ttu-id="60a52-133">指示在设置数据时使用字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="60a52-133">Indicates that the default value for the field was used when setting data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-134"><strong>adFieldDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-134"><strong>adFieldDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-135">16</span><span class="sxs-lookup"><span data-stu-id="60a52-135">16</span></span></p></td>
<td><p><span data-ttu-id="60a52-136">指示指定的字段不存在。</span><span class="sxs-lookup"><span data-stu-id="60a52-136">Indicates that the field specified does not exist.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-137"><strong>adFieldIgnore</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-137"><strong>adFieldIgnore</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-138">15</span><span class="sxs-lookup"><span data-stu-id="60a52-138">15</span></span></p></td>
<td><p><span data-ttu-id="60a52-p102">指示在设置数据源中的数据值时已跳过此字段。提供程序未设置值。</span><span class="sxs-lookup"><span data-stu-id="60a52-p102">Indicates that this field was skipped when setting data values in the source. The provider set no value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-141"><strong>adFieldIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-141"><strong>adFieldIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-142">10</span><span class="sxs-lookup"><span data-stu-id="60a52-142">10</span></span></p></td>
<td><p><span data-ttu-id="60a52-143">指示无法修改字段，因为它是计算得出的实体或派生实体。</span><span class="sxs-lookup"><span data-stu-id="60a52-143">Indicates that the field cannot be modified because it is a calculated or derived entity.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-144"><strong>adFieldInvalidURL</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-144"><strong>adFieldInvalidURL</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-145">17</span><span class="sxs-lookup"><span data-stu-id="60a52-145">17</span></span></p></td>
<td><p><span data-ttu-id="60a52-146">指示数据源 URL 包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="60a52-146">Indicates that the data source URL contains invalid characters.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-147"><strong>adFieldIsNull</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-147"><strong>adFieldIsNull</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-148">3</span><span class="sxs-lookup"><span data-stu-id="60a52-148">3</span></span></p></td>
<td><p><span data-ttu-id="60a52-149">指示提供程序返回了类型为 VT_NULL 的 VARIANT 值，并且此字段非空。</span><span class="sxs-lookup"><span data-stu-id="60a52-149">Indicates that the provider returned a VARIANT value of type VT_NULL and that the field is not empty.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-150"><strong>adFieldOK</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-150"><strong>adFieldOK</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-151">0</span><span class="sxs-lookup"><span data-stu-id="60a52-151">0</span></span></p></td>
<td><p><span data-ttu-id="60a52-p103">默认值。指示此字段已成功添加或删除。</span><span class="sxs-lookup"><span data-stu-id="60a52-p103">Default. Indicates that the field was successfully added or deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-154"><strong>adFieldOutOfSpace</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-154"><strong>adFieldOutOfSpace</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-155">22</span><span class="sxs-lookup"><span data-stu-id="60a52-155">22</span></span></p></td>
<td><p><span data-ttu-id="60a52-156">指示提供程序无法获取足够的存储空间来完成移动或复制操作。</span><span class="sxs-lookup"><span data-stu-id="60a52-156">Indicates that the provider is unable to obtain enough storage space to complete a move or copy operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-157"><strong>adFieldPendingChange</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-157"><strong>adFieldPendingChange</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-158">而 0x40000 可</span><span class="sxs-lookup"><span data-stu-id="60a52-158">0x40000</span></span></p></td>
<td><p><span data-ttu-id="60a52-p104">指示此字段已被删除然后重新添加（可能使用不同的数据类型）过，或者以前具有 adFieldOK 状态的此字段的值已被更改。在调用 <a href="update-method-ado.md">Update</a> 方法之后，字段的最终形式将修改 <a href="fields-collection-ado.md">Fields</a> 集合。</span><span class="sxs-lookup"><span data-stu-id="60a52-p104">Indicates either that the field has been deleted and then re-added, perhaps with a different data type, or that the value of the field that previously had a status of adFieldOK has changed. The final form of the field will modify the <a href="fields-collection-ado.md">Fields</a> collection after the <a href="update-method-ado.md">Update</a> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-161"><strong>adFieldPendingDelete</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-161"><strong>adFieldPendingDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-162">0x20000</span><span class="sxs-lookup"><span data-stu-id="60a52-162">0x20000</span></span></p></td>
<td><p><span data-ttu-id="60a52-p105">指示 <strong>Delete</strong> 操作导致设置状态。此字段已标记为在调用 <strong>Update</strong> 方法之后从 <strong>Fields</strong> 集合中删除。</span><span class="sxs-lookup"><span data-stu-id="60a52-p105">Indicates that the <strong>Delete</strong> operation caused the status to be set. The field has been marked for deletion from the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-165"><strong>adFieldPendingInsert</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-165"><strong>adFieldPendingInsert</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-166">0x10000</span><span class="sxs-lookup"><span data-stu-id="60a52-166">0x10000</span></span></p></td>
<td><p><span data-ttu-id="60a52-p106">指示 <strong>Append</strong> 操作导致设置状态。此<strong>字段</strong>已标记为在调用 <strong>Update</strong> 方法之后添加到 <strong>Fields</strong> 集合中。</span><span class="sxs-lookup"><span data-stu-id="60a52-p106">Indicates that the <strong>Append</strong> operation caused the status to be set. The <strong>Field</strong> has been marked to be added to the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-169"><strong>adFieldPendingUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-169"><strong>adFieldPendingUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-170">0x80000</span><span class="sxs-lookup"><span data-stu-id="60a52-170">0x80000</span></span></p></td>
<td><p><span data-ttu-id="60a52-171">指示提供程序无法确定哪个操作导致设置字段状态。</span><span class="sxs-lookup"><span data-stu-id="60a52-171">Indicates that the provider cannot determine what operation caused field status to be set.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-172"><strong>adFieldPendingUnknownDelete</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-172"><strong>adFieldPendingUnknownDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-173">0x100000</span><span class="sxs-lookup"><span data-stu-id="60a52-173">0x100000</span></span></p></td>
<td><p><span data-ttu-id="60a52-174">指示提供程序无法确定哪个操作导致设置字段状态，且在调用 <strong>Update</strong> 方法之后将从 <strong>Fields</strong> 集合中删除此字段。</span><span class="sxs-lookup"><span data-stu-id="60a52-174">Indicates that the provider cannot determine what operation caused field status to be set, and that the field will be deleted from the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-175"><strong>adFieldPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-175"><strong>adFieldPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-176">9</span><span class="sxs-lookup"><span data-stu-id="60a52-176">9</span></span></p></td>
<td><p><span data-ttu-id="60a52-177">指示无法修改此字段，因为它被定义为只读。</span><span class="sxs-lookup"><span data-stu-id="60a52-177">Indicates that the field cannot be modified because it is defined as read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-178"><strong>adFieldReadOnly</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-178"><strong>adFieldReadOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-179">24</span><span class="sxs-lookup"><span data-stu-id="60a52-179">24</span></span></p></td>
<td><p><span data-ttu-id="60a52-180">指示数据源中的字段被定义为只读。</span><span class="sxs-lookup"><span data-stu-id="60a52-180">Indicates that the field in the data source is defined as read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-181"><strong>adFieldResourceExists</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-181"><strong>adFieldResourceExists</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-182">19</span><span class="sxs-lookup"><span data-stu-id="60a52-182">19</span></span></p></td>
<td><p><span data-ttu-id="60a52-183">指示提供程序无法执行此操作，因为目标 URL 中已经存在一个对象，且无法覆盖该字段。</span><span class="sxs-lookup"><span data-stu-id="60a52-183">Indicates that the provider was unable to perform the operation because an object already exists at the destination URL and it is not able to overwrite the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-184"><strong>adFieldResourceLocked</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-184"><strong>adFieldResourceLocked</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-185">18</span><span class="sxs-lookup"><span data-stu-id="60a52-185">18</span></span></p></td>
<td><p><span data-ttu-id="60a52-186">指示提供程序无法执行此操作，因为数据源已被一个或多个其他应用程序或进程锁定。</span><span class="sxs-lookup"><span data-stu-id="60a52-186">Indicates that the provider was unable to perform the operation because the data source is locked by one or more other application or process.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-187"><strong>adFieldResourceOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-187"><strong>adFieldResourceOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-188">25</span><span class="sxs-lookup"><span data-stu-id="60a52-188">25</span></span></p></td>
<td><p><span data-ttu-id="60a52-189">指示源 URL 或目标 URL 在当前记录的范围之外。</span><span class="sxs-lookup"><span data-stu-id="60a52-189">Indicates that a source or destination URL is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-190"><strong>adFieldSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-190"><strong>adFieldSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-191">11</span><span class="sxs-lookup"><span data-stu-id="60a52-191">11</span></span></p></td>
<td><p><span data-ttu-id="60a52-192">指示此值违反了字段的数据源架构约束。</span><span class="sxs-lookup"><span data-stu-id="60a52-192">Indicates that the value violated the data source schema constraint for the field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-193"><strong>adFieldSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-193"><strong>adFieldSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-194">5</span><span class="sxs-lookup"><span data-stu-id="60a52-194">5</span></span></p></td>
<td><p><span data-ttu-id="60a52-195">指示提供程序返回的数据值有符号，但 ADO 字段值的数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="60a52-195">Indicates that data value returned by the provider was signed but the data type of the ADO field value was unsigned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-196"><strong>adFieldTruncated</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-196"><strong>adFieldTruncated</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-197">4</span><span class="sxs-lookup"><span data-stu-id="60a52-197">4</span></span></p></td>
<td><p><span data-ttu-id="60a52-198">指示从数据源进行读取时截断了长度可变的数据。</span><span class="sxs-lookup"><span data-stu-id="60a52-198">Indicates that variable-length data was truncated when reading from the data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60a52-199"><strong>adFieldUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-199"><strong>adFieldUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-200">8</span><span class="sxs-lookup"><span data-stu-id="60a52-200">8</span></span></p></td>
<td><p><span data-ttu-id="60a52-p107">指示当从数据源进行读取时，提供程序无法确定值。例如，只创建了行，列的默认值不可用，并且尚未指定新值。</span><span class="sxs-lookup"><span data-stu-id="60a52-p107">Indicates that the provider could not determine the value when reading from the data source. For example, the row was just created, the default value for the column was not available, and a new value had not yet been specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60a52-203"><strong>adFieldVolumeNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="60a52-203"><strong>adFieldVolumeNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="60a52-204">21</span><span class="sxs-lookup"><span data-stu-id="60a52-204">21</span></span></p></td>
<td><p><span data-ttu-id="60a52-205">指示提供程序无法定位由 URL 指定的存储卷。</span><span class="sxs-lookup"><span data-stu-id="60a52-205">Indicates that the provider is unable to locate the storage volume indicated by the URL.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="60a52-206">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="60a52-206">ADO/WFC equivalent</span></span>

<span data-ttu-id="60a52-207">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="60a52-207">These constants do not have ADO/WFC equivalents.</span></span>

