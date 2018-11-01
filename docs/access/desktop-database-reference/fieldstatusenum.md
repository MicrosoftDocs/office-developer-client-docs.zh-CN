---
title: FieldStatusEnum （访问桌面数据库参考 （英文）
TOCTitle: FieldStatusEnum
ms:assetid: 49570042-8435-8618-3ba1-7006c47735e0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249225(v=office.15)
ms:contentKeyID: 48544635
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 007daa84e15b79d6aa82e4e1e75b1c3d2b0901ce
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867921"
---
# <a name="fieldstatusenum"></a><span data-ttu-id="cbaba-102">FieldStatusEnum</span><span class="sxs-lookup"><span data-stu-id="cbaba-102">FieldStatusEnum</span></span>

<span data-ttu-id="cbaba-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cbaba-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cbaba-104">指定 **Field** 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="cbaba-104">Specifies the status of a **Field** object.</span></span>

<span data-ttu-id="cbaba-105">**adFieldPending\*** 值指示导致设置状态的操作，可以与其他状态值一起使用。</span><span class="sxs-lookup"><span data-stu-id="cbaba-105">The **adFieldPending\*** values indicate the operation that caused the status to be set, and may be combined with other status values.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cbaba-106">常量</span><span class="sxs-lookup"><span data-stu-id="cbaba-106">Constant</span></span></p></th>
<th><p><span data-ttu-id="cbaba-107">值</span><span class="sxs-lookup"><span data-stu-id="cbaba-107">Value</span></span></p></th>
<th><p><span data-ttu-id="cbaba-108">说明</span><span class="sxs-lookup"><span data-stu-id="cbaba-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-109"><strong>adFieldAlreadyExists</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-109"><strong>adFieldAlreadyExists</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-110">26</span><span class="sxs-lookup"><span data-stu-id="cbaba-110">26</span></span></p></td>
<td><p><span data-ttu-id="cbaba-111">指示指定的字段已经存在。</span><span class="sxs-lookup"><span data-stu-id="cbaba-111">Indicates that the specified field already exists.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-112"><strong>adFieldBadStatus</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-112"><strong>adFieldBadStatus</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-113">12</span><span class="sxs-lookup"><span data-stu-id="cbaba-113">12</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p101">指示从 ADO 向 OLE DB 提供程序发送了无效的状态值。可能的原因包括 OLE DB 提供程序的版本是 1.0 或 1.1，或者 <a href="value-property-ado.md">Value 属性 (ADO)</a> 和 <a href="status-property-ado-field.md">Status 属性 (ADO Field)</a> 的组合不正确。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p101">Indicates that an invalid status value was sent from ADO to the OLE DB provider. Possible causes include an OLE DB 1.0 or 1.1 provider, or an improper combination of <a href="value-property-ado.md">Value</a> and <a href="status-property-ado-field.md">Status</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-116"><strong>adFieldCannotComplete</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-116"><strong>adFieldCannotComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-117">20</span><span class="sxs-lookup"><span data-stu-id="cbaba-117">20</span></span></p></td>
<td><p><span data-ttu-id="cbaba-118">指示由 <a href="source-property-ado-record.md">Source 属性 (ADO Record)</a> 指定的 URL 的服务器无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="cbaba-118">Indicates that the server of the URL specified by <a href="source-property-ado-record.md">Source</a> could not complete the operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-119"><strong>adFieldCannotDeleteSource</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-119"><strong>adFieldCannotDeleteSource</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-120">23</span><span class="sxs-lookup"><span data-stu-id="cbaba-120">23</span></span></p></td>
<td><p><span data-ttu-id="cbaba-121">指示在移动操作期间，将树或子树移动到了新位置，但无法删除源。</span><span class="sxs-lookup"><span data-stu-id="cbaba-121">Indicates that during a move operation, a tree or subtree was moved to a new location, but the source could not be deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-122"><strong>adFieldCantConvertValue</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-122"><strong>adFieldCantConvertValue</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-123">2</span><span class="sxs-lookup"><span data-stu-id="cbaba-123">2</span></span></p></td>
<td><p><span data-ttu-id="cbaba-124">指示由于丢失数据而无法检索或存储字段。</span><span class="sxs-lookup"><span data-stu-id="cbaba-124">Indicates that the field cannot be retrieved or stored without loss of data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-125"><strong>adFieldCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-125"><strong>adFieldCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-126">7</span><span class="sxs-lookup"><span data-stu-id="cbaba-126">7</span></span></p></td>
<td><p><span data-ttu-id="cbaba-127">指示无法添加字段，因为提供程序超过了限制（如允许的字段数）。</span><span class="sxs-lookup"><span data-stu-id="cbaba-127">Indicates that the field could not be added because the provider exceeded a limitation (such as the number of fields allowed).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-128"><strong>adFieldDataOverflow</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-128"><strong>adFieldDataOverflow</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-129">6</span><span class="sxs-lookup"><span data-stu-id="cbaba-129">6</span></span></p></td>
<td><p><span data-ttu-id="cbaba-130">指示从提供程序返回的数据使字段的数据类型发生溢出。</span><span class="sxs-lookup"><span data-stu-id="cbaba-130">Indicates that the data returned from the provider overflowed the data type of the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-131"><strong>adFieldDefault</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-131"><strong>adFieldDefault</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-132">13</span><span class="sxs-lookup"><span data-stu-id="cbaba-132">13</span></span></p></td>
<td><p><span data-ttu-id="cbaba-133">指示在设置数据时使用字段的默认值。</span><span class="sxs-lookup"><span data-stu-id="cbaba-133">Indicates that the default value for the field was used when setting data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-134"><strong>adFieldDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-134"><strong>adFieldDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-135">16</span><span class="sxs-lookup"><span data-stu-id="cbaba-135">16</span></span></p></td>
<td><p><span data-ttu-id="cbaba-136">指示指定的字段不存在。</span><span class="sxs-lookup"><span data-stu-id="cbaba-136">Indicates that the field specified does not exist.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-137"><strong>adFieldIgnore</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-137"><strong>adFieldIgnore</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-138">15</span><span class="sxs-lookup"><span data-stu-id="cbaba-138">15</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p102">指示在设置数据源中的数据值时已跳过此字段。提供程序未设置值。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p102">Indicates that this field was skipped when setting data values in the source. The provider set no value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-141"><strong>adFieldIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-141"><strong>adFieldIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-142">10</span><span class="sxs-lookup"><span data-stu-id="cbaba-142">10</span></span></p></td>
<td><p><span data-ttu-id="cbaba-143">指示无法修改字段，因为它是计算得出的实体或派生实体。</span><span class="sxs-lookup"><span data-stu-id="cbaba-143">Indicates that the field cannot be modified because it is a calculated or derived entity.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-144"><strong>adFieldInvalidURL</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-144"><strong>adFieldInvalidURL</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-145">17</span><span class="sxs-lookup"><span data-stu-id="cbaba-145">17</span></span></p></td>
<td><p><span data-ttu-id="cbaba-146">指示数据源 URL 包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="cbaba-146">Indicates that the data source URL contains invalid characters.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-147"><strong>adFieldIsNull</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-147"><strong>adFieldIsNull</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-148">3</span><span class="sxs-lookup"><span data-stu-id="cbaba-148">3</span></span></p></td>
<td><p><span data-ttu-id="cbaba-149">指示提供程序返回了类型为 VT_NULL 的 VARIANT 值，并且此字段非空。</span><span class="sxs-lookup"><span data-stu-id="cbaba-149">Indicates that the provider returned a VARIANT value of type VT_NULL and that the field is not empty.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-150"><strong>adFieldOK</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-150"><strong>adFieldOK</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-151">0</span><span class="sxs-lookup"><span data-stu-id="cbaba-151">0</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p103">默认值。指示此字段已成功添加或删除。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p103">Default. Indicates that the field was successfully added or deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-154"><strong>adFieldOutOfSpace</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-154"><strong>adFieldOutOfSpace</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-155">22</span><span class="sxs-lookup"><span data-stu-id="cbaba-155">22</span></span></p></td>
<td><p><span data-ttu-id="cbaba-156">指示提供程序无法获取足够的存储空间来完成移动或复制操作。</span><span class="sxs-lookup"><span data-stu-id="cbaba-156">Indicates that the provider is unable to obtain enough storage space to complete a move or copy operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-157"><strong>adFieldPendingChange</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-157"><strong>adFieldPendingChange</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-158">而 0x40000 可</span><span class="sxs-lookup"><span data-stu-id="cbaba-158">0x40000</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p104">指示此字段已被删除然后重新添加（可能使用不同的数据类型）过，或者以前具有 adFieldOK 状态的此字段的值已被更改。在调用 <a href="update-method-ado.md">Update</a> 方法之后，字段的最终形式将修改 <a href="fields-collection-ado.md">Fields</a> 集合。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p104">Indicates either that the field has been deleted and then re-added, perhaps with a different data type, or that the value of the field that previously had a status of adFieldOK has changed. The final form of the field will modify the <a href="fields-collection-ado.md">Fields</a> collection after the <a href="update-method-ado.md">Update</a> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-161"><strong>adFieldPendingDelete</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-161"><strong>adFieldPendingDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-162">0x20000</span><span class="sxs-lookup"><span data-stu-id="cbaba-162">0x20000</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p105">指示 <strong>Delete</strong> 操作导致设置状态。此字段已标记为在调用 <strong>Update</strong> 方法之后从 <strong>Fields</strong> 集合中删除。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p105">Indicates that the <strong>Delete</strong> operation caused the status to be set. The field has been marked for deletion from the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-165"><strong>adFieldPendingInsert</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-165"><strong>adFieldPendingInsert</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-166">0x10000</span><span class="sxs-lookup"><span data-stu-id="cbaba-166">0x10000</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p106">指示 <strong>Append</strong> 操作导致设置状态。此<strong>字段</strong>已标记为在调用 <strong>Update</strong> 方法之后添加到 <strong>Fields</strong> 集合中。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p106">Indicates that the <strong>Append</strong> operation caused the status to be set. The <strong>Field</strong> has been marked to be added to the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-169"><strong>adFieldPendingUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-169"><strong>adFieldPendingUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-170">0x80000</span><span class="sxs-lookup"><span data-stu-id="cbaba-170">0x80000</span></span></p></td>
<td><p><span data-ttu-id="cbaba-171">指示提供程序无法确定哪个操作导致设置字段状态。</span><span class="sxs-lookup"><span data-stu-id="cbaba-171">Indicates that the provider cannot determine what operation caused field status to be set.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-172"><strong>adFieldPendingUnknownDelete</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-172"><strong>adFieldPendingUnknownDelete</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-173">0x100000</span><span class="sxs-lookup"><span data-stu-id="cbaba-173">0x100000</span></span></p></td>
<td><p><span data-ttu-id="cbaba-174">指示提供程序无法确定哪个操作导致设置字段状态，且在调用 <strong>Update</strong> 方法之后将从 <strong>Fields</strong> 集合中删除此字段。</span><span class="sxs-lookup"><span data-stu-id="cbaba-174">Indicates that the provider cannot determine what operation caused field status to be set, and that the field will be deleted from the <strong>Fields</strong> collection after the <strong>Update</strong> method is called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-175"><strong>adFieldPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-175"><strong>adFieldPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-176">9</span><span class="sxs-lookup"><span data-stu-id="cbaba-176">9</span></span></p></td>
<td><p><span data-ttu-id="cbaba-177">指示无法修改此字段，因为它被定义为只读。</span><span class="sxs-lookup"><span data-stu-id="cbaba-177">Indicates that the field cannot be modified because it is defined as read-only.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-178"><strong>adFieldReadOnly</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-178"><strong>adFieldReadOnly</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-179">24</span><span class="sxs-lookup"><span data-stu-id="cbaba-179">24</span></span></p></td>
<td><p><span data-ttu-id="cbaba-180">指示数据源中的字段被定义为只读。</span><span class="sxs-lookup"><span data-stu-id="cbaba-180">Indicates that the field in the data source is defined as read-only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-181"><strong>adFieldResourceExists</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-181"><strong>adFieldResourceExists</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-182">19</span><span class="sxs-lookup"><span data-stu-id="cbaba-182">19</span></span></p></td>
<td><p><span data-ttu-id="cbaba-183">指示提供程序无法执行此操作，因为目标 URL 中已经存在一个对象，且无法覆盖该字段。</span><span class="sxs-lookup"><span data-stu-id="cbaba-183">Indicates that the provider was unable to perform the operation because an object already exists at the destination URL and it is not able to overwrite the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-184"><strong>adFieldResourceLocked</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-184"><strong>adFieldResourceLocked</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-185">18</span><span class="sxs-lookup"><span data-stu-id="cbaba-185">18</span></span></p></td>
<td><p><span data-ttu-id="cbaba-186">指示提供程序无法执行此操作，因为数据源已被一个或多个其他应用程序或进程锁定。</span><span class="sxs-lookup"><span data-stu-id="cbaba-186">Indicates that the provider was unable to perform the operation because the data source is locked by one or more other application or process.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-187"><strong>adFieldResourceOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-187"><strong>adFieldResourceOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-188">25</span><span class="sxs-lookup"><span data-stu-id="cbaba-188">25</span></span></p></td>
<td><p><span data-ttu-id="cbaba-189">指示源 URL 或目标 URL 在当前记录的范围之外。</span><span class="sxs-lookup"><span data-stu-id="cbaba-189">Indicates that a source or destination URL is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-190"><strong>adFieldSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-190"><strong>adFieldSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-191">11</span><span class="sxs-lookup"><span data-stu-id="cbaba-191">11</span></span></p></td>
<td><p><span data-ttu-id="cbaba-192">指示此值违反了字段的数据源架构约束。</span><span class="sxs-lookup"><span data-stu-id="cbaba-192">Indicates that the value violated the data source schema constraint for the field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-193"><strong>adFieldSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-193"><strong>adFieldSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-194">5</span><span class="sxs-lookup"><span data-stu-id="cbaba-194">5</span></span></p></td>
<td><p><span data-ttu-id="cbaba-195">指示提供程序返回的数据值有符号，但 ADO 字段值的数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="cbaba-195">Indicates that data value returned by the provider was signed but the data type of the ADO field value was unsigned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-196"><strong>adFieldTruncated</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-196"><strong>adFieldTruncated</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-197">4</span><span class="sxs-lookup"><span data-stu-id="cbaba-197">4</span></span></p></td>
<td><p><span data-ttu-id="cbaba-198">指示从数据源进行读取时截断了长度可变的数据。</span><span class="sxs-lookup"><span data-stu-id="cbaba-198">Indicates that variable-length data was truncated when reading from the data source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbaba-199"><strong>adFieldUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-199"><strong>adFieldUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-200">8</span><span class="sxs-lookup"><span data-stu-id="cbaba-200">8</span></span></p></td>
<td><p><span data-ttu-id="cbaba-p107">指示当从数据源进行读取时，提供程序无法确定值。例如，只创建了行，列的默认值不可用，并且尚未指定新值。</span><span class="sxs-lookup"><span data-stu-id="cbaba-p107">Indicates that the provider could not determine the value when reading from the data source. For example, the row was just created, the default value for the column was not available, and a new value had not yet been specified.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbaba-203"><strong>adFieldVolumeNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="cbaba-203"><strong>adFieldVolumeNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="cbaba-204">21</span><span class="sxs-lookup"><span data-stu-id="cbaba-204">21</span></span></p></td>
<td><p><span data-ttu-id="cbaba-205">指示提供程序无法定位由 URL 指定的存储卷。</span><span class="sxs-lookup"><span data-stu-id="cbaba-205">Indicates that the provider is unable to locate the storage volume indicated by the URL.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="cbaba-206">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="cbaba-206">ADO/WFC equivalent</span></span>

<span data-ttu-id="cbaba-207">这些常量没有 ADO/WFC 等效值。</span><span class="sxs-lookup"><span data-stu-id="cbaba-207">These constants do not have ADO/WFC equivalents.</span></span>

