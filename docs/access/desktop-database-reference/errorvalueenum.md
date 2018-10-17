---
title: ErrorValueEnum （访问桌面数据库参考 （英文）
TOCTitle: ErrorValueEnum
ms:assetid: 2af99f32-6004-1225-367c-45d693f447b8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249058(v=office.15)
ms:contentKeyID: 48543921
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: de7f19c119c3161ece57344b911fcca36a1a8a3d
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467437"
---
# <a name="errorvalueenum"></a><span data-ttu-id="ef539-102">ErrorValueEnum</span><span class="sxs-lookup"><span data-stu-id="ef539-102">ErrorValueEnum</span></span>


<span data-ttu-id="ef539-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ef539-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ef539-104">指定 ADO 运行时错误的类型。</span><span class="sxs-lookup"><span data-stu-id="ef539-104">Specifies the type of ADO run-time error.</span></span>

<span data-ttu-id="ef539-105">下面列出了三种格式的错误号：</span><span class="sxs-lookup"><span data-stu-id="ef539-105">Three forms of the error number are listed:</span></span>

  - <span data-ttu-id="ef539-p101">正十进制 - 十进制格式的完整编号的两个低位字节。此编号显示在默认的 Visual Basic 错误消息对话框中。例如，运行时错误"3707"。</span><span class="sxs-lookup"><span data-stu-id="ef539-p101">Positive decimal — the low two bytes of the full number in decimal format. This number is displayed in the default Visual Basic error message dialog box. For example, Run-time error '3707'.</span></span>

  - <span data-ttu-id="ef539-109">负十进制 - 完整错误号的十进制转换形式。</span><span class="sxs-lookup"><span data-stu-id="ef539-109">Negative decimal — The decimal translation of the full error number.</span></span>

  - <span data-ttu-id="ef539-p102">十六进制 - 完整错误号的十六进制表示。Windows 设备代码在第四位。ADO 错误号的设备代码为 *A*。例如：0x800***A***0E7B。</span><span class="sxs-lookup"><span data-stu-id="ef539-p102">Hexadecimal — The hexadecimal representation of the full error number. The Windows facility code is in the fourth digit. The facility code for ADO error numbers is *A*. For example: 0x800***A***0E7B.</span></span>


> [!NOTE]
> <P><span data-ttu-id="ef539-p103">OLE DB 错误可以传递给 ADO 应用程序。通常，可以通过 Windows 设备代码 <EM>4</EM> 来标识这些错误。例如，0x800<STRONG><EM>4</EM></STRONG>.... 有关这些编号的详细信息，请参阅<EM>《OLE DB 程序员参考》</EM>第 16 章。</span><span class="sxs-lookup"><span data-stu-id="ef539-p103">OLE DB errors may be passed to your ADO application. Typically, these can be identified by a Windows facility code of <EM>4</EM>. For example, 0x800<STRONG><EM>4</EM></STRONG>.... For more information about these numbers, see Chapter 16 of the <EM>OLE DB Programmer's Reference.</EM></span></span></P>



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ef539-116">常量</span><span class="sxs-lookup"><span data-stu-id="ef539-116">Constant</span></span></p></th>
<th><p><span data-ttu-id="ef539-117">值</span><span class="sxs-lookup"><span data-stu-id="ef539-117">Value</span></span></p></th>
<th><p><span data-ttu-id="ef539-118">说明</span><span class="sxs-lookup"><span data-stu-id="ef539-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef539-119"><strong>adErrBoundToCommand</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-119"><strong>adErrBoundToCommand</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-120">3707</span><span class="sxs-lookup"><span data-stu-id="ef539-120">3707</span></span><br />
<span data-ttu-id="ef539-121">-2146824581</span><span class="sxs-lookup"><span data-stu-id="ef539-121">-2146824581</span></span><br />
<span data-ttu-id="ef539-122">0x800A0E7B</span><span class="sxs-lookup"><span data-stu-id="ef539-122">0x800A0E7B</span></span></p></td>
<td><p><span data-ttu-id="ef539-123">无法更改以 <strong>Command</strong> 对象为源的 <strong>Recordset</strong> 对象的 <strong>ActiveConnection</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="ef539-123">Cannot change the <strong>ActiveConnection</strong> property of a <strong>Recordset</strong> object which has a <strong>Command</strong> object as its source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-124"><strong>adErrCannotComplete</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-124"><strong>adErrCannotComplete</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-125">3732</span><span class="sxs-lookup"><span data-stu-id="ef539-125">3732</span></span><br />
<span data-ttu-id="ef539-126">-2146824556</span><span class="sxs-lookup"><span data-stu-id="ef539-126">-2146824556</span></span><br />
<span data-ttu-id="ef539-127">0x800A0E94</span><span class="sxs-lookup"><span data-stu-id="ef539-127">0x800A0E94</span></span></p></td>
<td><p><span data-ttu-id="ef539-128">服务器无法完成操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-128">Server cannot complete the operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-129"><strong>adErrCantChangeConnection</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-129"><strong>adErrCantChangeConnection</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-130">3748</span><span class="sxs-lookup"><span data-stu-id="ef539-130">3748</span></span><br />
<span data-ttu-id="ef539-131">-2146824540</span><span class="sxs-lookup"><span data-stu-id="ef539-131">-2146824540</span></span><br />
<span data-ttu-id="ef539-132">0x800A0EA4</span><span class="sxs-lookup"><span data-stu-id="ef539-132">0x800A0EA4</span></span></p></td>
<td><p><span data-ttu-id="ef539-p104">连接被拒绝。请求的新连接和已被使用的连接的特性不一致。</span><span class="sxs-lookup"><span data-stu-id="ef539-p104">Connection was denied. New connection you requested has different characteristics than the one already in use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-135"><strong>adErrCantChangeProvider</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-135"><strong>adErrCantChangeProvider</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-136">3220</span><span class="sxs-lookup"><span data-stu-id="ef539-136">3220</span></span><br />
<span data-ttu-id="ef539-137">-2146825068</span><span class="sxs-lookup"><span data-stu-id="ef539-137">-2146825068</span></span><br />
<span data-ttu-id="ef539-138">0X800A0C94</span><span class="sxs-lookup"><span data-stu-id="ef539-138">0X800A0C94</span></span></p></td>
<td><p><span data-ttu-id="ef539-139">所提供的提供程序与正在使用的提供程序不同。</span><span class="sxs-lookup"><span data-stu-id="ef539-139">Supplied provider is different from the one already in use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-140"><strong>adErrCantConvertvalue</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-140"><strong>adErrCantConvertvalue</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-141">3724</span><span class="sxs-lookup"><span data-stu-id="ef539-141">3724</span></span><br />
<span data-ttu-id="ef539-142">-2146824564</span><span class="sxs-lookup"><span data-stu-id="ef539-142">-2146824564</span></span><br />
<span data-ttu-id="ef539-143">0x800A0E8C</span><span class="sxs-lookup"><span data-stu-id="ef539-143">0x800A0E8C</span></span></p></td>
<td><p><span data-ttu-id="ef539-p105">由于符号不匹配或数据溢出以外的其他原因，数据值无法转换。例如，转换会截断数据。</span><span class="sxs-lookup"><span data-stu-id="ef539-p105">Data value cannot be converted for reasons other than sign mismatch or data overflow. For example, conversion would have truncated data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-146"><strong>adErrCantCreate</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-146"><strong>adErrCantCreate</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-147">3725</span><span class="sxs-lookup"><span data-stu-id="ef539-147">3725</span></span><br />
<span data-ttu-id="ef539-148">-2146824563</span><span class="sxs-lookup"><span data-stu-id="ef539-148">-2146824563</span></span><br />
<span data-ttu-id="ef539-149">0x800A0E8D</span><span class="sxs-lookup"><span data-stu-id="ef539-149">0x800A0E8D</span></span></p></td>
<td><p><span data-ttu-id="ef539-150">因为字段数据类型未知，或提供程序没有足够的资源执行该操作，无法设置或检索数据值。</span><span class="sxs-lookup"><span data-stu-id="ef539-150">Data value cannot be set or retrieved because the field data type was unknown, or the provider had insufficient resources to perform the operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-151"><strong>adErrCatalogNotSet</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-151"><strong>adErrCatalogNotSet</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-152">3747</span><span class="sxs-lookup"><span data-stu-id="ef539-152">3747</span></span><br />
<span data-ttu-id="ef539-153">-2146824541</span><span class="sxs-lookup"><span data-stu-id="ef539-153">-2146824541</span></span><br />
<span data-ttu-id="ef539-154">0x800A0EA3</span><span class="sxs-lookup"><span data-stu-id="ef539-154">0x800A0EA3</span></span></p></td>
<td><p><span data-ttu-id="ef539-155">操作需要一个有效的 <strong>ParentCatalog</strong> 。</span><span class="sxs-lookup"><span data-stu-id="ef539-155">Operation requires a valid <strong>ParentCatalog</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-156"><strong>adErrColumnNotOnThisRow</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-156"><strong>adErrColumnNotOnThisRow</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-157">3726</span><span class="sxs-lookup"><span data-stu-id="ef539-157">3726</span></span><br />
<span data-ttu-id="ef539-158">-2146824562</span><span class="sxs-lookup"><span data-stu-id="ef539-158">-2146824562</span></span><br />
<span data-ttu-id="ef539-159">0x800A0E8E</span><span class="sxs-lookup"><span data-stu-id="ef539-159">0x800A0E8E</span></span></p></td>
<td><p><span data-ttu-id="ef539-160">记录不包含此字段。</span><span class="sxs-lookup"><span data-stu-id="ef539-160">Record does not contain this field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-161"><strong>adErrDataConversion</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-161"><strong>adErrDataConversion</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-162">3421</span><span class="sxs-lookup"><span data-stu-id="ef539-162">3421</span></span><br />
<span data-ttu-id="ef539-163">-2146824867</span><span class="sxs-lookup"><span data-stu-id="ef539-163">-2146824867</span></span><br />
<span data-ttu-id="ef539-164">0x800A0D5D</span><span class="sxs-lookup"><span data-stu-id="ef539-164">0x800A0D5D</span></span></p></td>
<td><p><span data-ttu-id="ef539-165">应用程序在当前操作中使用了错误类型的值。</span><span class="sxs-lookup"><span data-stu-id="ef539-165">Application uses a value of the wrong type for the current operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-166"><strong>adErrDataOverflow</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-166"><strong>adErrDataOverflow</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-167">3721</span><span class="sxs-lookup"><span data-stu-id="ef539-167">3721</span></span><br />
<span data-ttu-id="ef539-168">-2146824567</span><span class="sxs-lookup"><span data-stu-id="ef539-168">-2146824567</span></span><br />
<span data-ttu-id="ef539-169">0x800A0E89</span><span class="sxs-lookup"><span data-stu-id="ef539-169">0x800A0E89</span></span></p></td>
<td><p><span data-ttu-id="ef539-170">数据值过大，无法以字段数据类型表示。</span><span class="sxs-lookup"><span data-stu-id="ef539-170">Data value is too large to be represented by the field data type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-171"><strong>adErrDelResOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-171"><strong>adErrDelResOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-172">3738</span><span class="sxs-lookup"><span data-stu-id="ef539-172">3738</span></span><br />
<span data-ttu-id="ef539-173">-2146824550</span><span class="sxs-lookup"><span data-stu-id="ef539-173">-2146824550</span></span><br />
<span data-ttu-id="ef539-174">0x800A0E9A</span><span class="sxs-lookup"><span data-stu-id="ef539-174">0x800A0E9A</span></span></p></td>
<td><p><span data-ttu-id="ef539-175">要被删除对象的 URL 超出了当前记录的范围。</span><span class="sxs-lookup"><span data-stu-id="ef539-175">URL of the object to be deleted is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-176"><strong>adErrDenyNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-176"><strong>adErrDenyNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-177">3750</span><span class="sxs-lookup"><span data-stu-id="ef539-177">3750</span></span><br />
<span data-ttu-id="ef539-178">-2146824538</span><span class="sxs-lookup"><span data-stu-id="ef539-178">-2146824538</span></span><br />
<span data-ttu-id="ef539-179">0x800A0EA6</span><span class="sxs-lookup"><span data-stu-id="ef539-179">0x800A0EA6</span></span></p></td>
<td><p><span data-ttu-id="ef539-180">提供程序不支持共享限制。</span><span class="sxs-lookup"><span data-stu-id="ef539-180">Provider does not support sharing restrictions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-181"><strong>adErrDenyTypeNotSupported</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-181"><strong>adErrDenyTypeNotSupported</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-182">3751</span><span class="sxs-lookup"><span data-stu-id="ef539-182">3751</span></span><br />
<span data-ttu-id="ef539-183">-2146824537</span><span class="sxs-lookup"><span data-stu-id="ef539-183">-2146824537</span></span><br />
<span data-ttu-id="ef539-184">0x800A0EA7</span><span class="sxs-lookup"><span data-stu-id="ef539-184">0x800A0EA7</span></span></p></td>
<td><p><span data-ttu-id="ef539-185">提供程序不支持所请求的共享限制类型。</span><span class="sxs-lookup"><span data-stu-id="ef539-185">Provider does not support the requested kind of sharing restriction.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-186"><strong>adErrFeatureNotAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-186"><strong>adErrFeatureNotAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-187">3251</span><span class="sxs-lookup"><span data-stu-id="ef539-187">3251</span></span><br />
<span data-ttu-id="ef539-188">-2146825037</span><span class="sxs-lookup"><span data-stu-id="ef539-188">-2146825037</span></span><br />
<span data-ttu-id="ef539-189">0x800A0CB3</span><span class="sxs-lookup"><span data-stu-id="ef539-189">0x800A0CB3</span></span></p></td>
<td><p><span data-ttu-id="ef539-190">对象或提供程序不能执行所需的操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-190">Object or provider is not capable of performing requested operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-191"><strong>adErrFieldsUpdateFailed</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-191"><strong>adErrFieldsUpdateFailed</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-192">3749</span><span class="sxs-lookup"><span data-stu-id="ef539-192">3749</span></span><br />
<span data-ttu-id="ef539-193">-2146824539</span><span class="sxs-lookup"><span data-stu-id="ef539-193">-2146824539</span></span><br />
<span data-ttu-id="ef539-194">0x800A0EA5</span><span class="sxs-lookup"><span data-stu-id="ef539-194">0x800A0EA5</span></span></p></td>
<td><p><span data-ttu-id="ef539-p106">字段更新失败。有关详细信息，请检查各个字段对象的 <strong>Status</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="ef539-p106">Fields update failed. For further information, examine the <strong>Status</strong> property of individual field objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-197"><strong>adErrIllegalOperation</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-197"><strong>adErrIllegalOperation</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-198">3219</span><span class="sxs-lookup"><span data-stu-id="ef539-198">3219</span></span><br />
<span data-ttu-id="ef539-199">-2146825069</span><span class="sxs-lookup"><span data-stu-id="ef539-199">-2146825069</span></span><br />
<span data-ttu-id="ef539-200">0x800A0C93</span><span class="sxs-lookup"><span data-stu-id="ef539-200">0x800A0C93</span></span></p></td>
<td><p><span data-ttu-id="ef539-201">此上下文中不允许操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-201">Operation is not allowed in this context.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-202"><strong>adErrIntegrityViolation</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-202"><strong>adErrIntegrityViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-203">3719</span><span class="sxs-lookup"><span data-stu-id="ef539-203">3719</span></span><br />
<span data-ttu-id="ef539-204">-2146824569</span><span class="sxs-lookup"><span data-stu-id="ef539-204">-2146824569</span></span><br />
<span data-ttu-id="ef539-205">0x800A0E87</span><span class="sxs-lookup"><span data-stu-id="ef539-205">0x800A0E87</span></span></p></td>
<td><p><span data-ttu-id="ef539-206">数据值与字段的完整性约束冲突。</span><span class="sxs-lookup"><span data-stu-id="ef539-206">Data value conflicts with the integrity constraints of the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-207"><strong>adErrInTransaction</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-207"><strong>adErrInTransaction</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-208">3246</span><span class="sxs-lookup"><span data-stu-id="ef539-208">3246</span></span><br />
<span data-ttu-id="ef539-209">-2146825042</span><span class="sxs-lookup"><span data-stu-id="ef539-209">-2146825042</span></span><br />
<span data-ttu-id="ef539-210">0x800A0CAE</span><span class="sxs-lookup"><span data-stu-id="ef539-210">0x800A0CAE</span></span></p></td>
<td><p><span data-ttu-id="ef539-211">在事务处理过程中，不能显式关闭 <strong>Connection</strong> 对象。</span><span class="sxs-lookup"><span data-stu-id="ef539-211"><strong>Connection</strong> object cannot be explicitly closed while in a transaction.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-212"><strong>adErrInvalidArgument</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-212"><strong>adErrInvalidArgument</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-213">3001</span><span class="sxs-lookup"><span data-stu-id="ef539-213">3001</span></span><br />
<span data-ttu-id="ef539-214">-2146825287</span><span class="sxs-lookup"><span data-stu-id="ef539-214">-2146825287</span></span><br />
<span data-ttu-id="ef539-215">0x800A0BB9</span><span class="sxs-lookup"><span data-stu-id="ef539-215">0x800A0BB9</span></span></p></td>
<td><p><span data-ttu-id="ef539-216">参数类型不正确，或不在可以接受的范围之内，或与其他参数冲突。</span><span class="sxs-lookup"><span data-stu-id="ef539-216">Arguments are of the wrong type, are out of acceptable range, or are in conflict with one another.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-217"><strong>adErrInvalidConnection</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-217"><strong>adErrInvalidConnection</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-218">3709</span><span class="sxs-lookup"><span data-stu-id="ef539-218">3709</span></span><br />
<span data-ttu-id="ef539-219">-2146824579</span><span class="sxs-lookup"><span data-stu-id="ef539-219">-2146824579</span></span><br />
<span data-ttu-id="ef539-220">0x800A0E7D</span><span class="sxs-lookup"><span data-stu-id="ef539-220">0x800A0E7D</span></span></p></td>
<td><p><span data-ttu-id="ef539-p107">该连接无法用于执行此操作。它已关闭或在此上下文中无效。</span><span class="sxs-lookup"><span data-stu-id="ef539-p107">The connection cannot be used to perform this operation. It is either closed or invalid in this context.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-223"><strong>adErrInvalidParamInfo</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-223"><strong>adErrInvalidParamInfo</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-224">3708</span><span class="sxs-lookup"><span data-stu-id="ef539-224">3708</span></span><br />
<span data-ttu-id="ef539-225">-2146824580</span><span class="sxs-lookup"><span data-stu-id="ef539-225">-2146824580</span></span><br />
<span data-ttu-id="ef539-226">0x800A0E7C</span><span class="sxs-lookup"><span data-stu-id="ef539-226">0x800A0E7C</span></span></p></td>
<td><p><span data-ttu-id="ef539-p108">没有正确定义 <strong>Parameter</strong> 对象。提供的信息不一致或不完整。  </span><span class="sxs-lookup"><span data-stu-id="ef539-p108"><strong>Parameter</strong> object is improperly defined. Inconsistent or incomplete information was provided.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-229"><strong>adErrInvalidTransaction</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-229"><strong>adErrInvalidTransaction</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-230">3714</span><span class="sxs-lookup"><span data-stu-id="ef539-230">3714</span></span><br />
<span data-ttu-id="ef539-231">-2146824574</span><span class="sxs-lookup"><span data-stu-id="ef539-231">-2146824574</span></span><br />
<span data-ttu-id="ef539-232">0x800A0E82</span><span class="sxs-lookup"><span data-stu-id="ef539-232">0x800A0E82</span></span></p></td>
<td><p><span data-ttu-id="ef539-233">协调事务无效或未开始。</span><span class="sxs-lookup"><span data-stu-id="ef539-233">Coordinating transaction is invalid or has not started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-234"><strong>adErrInvalidURL</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-234"><strong>adErrInvalidURL</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-235">3729</span><span class="sxs-lookup"><span data-stu-id="ef539-235">3729</span></span><br />
<span data-ttu-id="ef539-236">-2146824559</span><span class="sxs-lookup"><span data-stu-id="ef539-236">-2146824559</span></span><br />
<span data-ttu-id="ef539-237">0x800A0E91</span><span class="sxs-lookup"><span data-stu-id="ef539-237">0x800A0E91</span></span></p></td>
<td><p><span data-ttu-id="ef539-p109">URL 包含无效字符。请确保键入的 URL 正确。</span><span class="sxs-lookup"><span data-stu-id="ef539-p109">URL contains invalid characters. Make sure the URL is typed correctly.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-240"><strong>adErrItemNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-240"><strong>adErrItemNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-241">3265</span><span class="sxs-lookup"><span data-stu-id="ef539-241">3265</span></span><br />
<span data-ttu-id="ef539-242">-2146825023</span><span class="sxs-lookup"><span data-stu-id="ef539-242">-2146825023</span></span><br />
<span data-ttu-id="ef539-243">0x800A0CC1</span><span class="sxs-lookup"><span data-stu-id="ef539-243">0x800A0CC1</span></span></p></td>
<td><p><span data-ttu-id="ef539-244">在对应于所请求的名称或序号的集合中没有找到项。</span><span class="sxs-lookup"><span data-stu-id="ef539-244">Item cannot be found in the collection corresponding to the requested name or ordinal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-245"><strong>adErrNoCurrentRecord</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-245"><strong>adErrNoCurrentRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-246">3021</span><span class="sxs-lookup"><span data-stu-id="ef539-246">3021</span></span><br />
<span data-ttu-id="ef539-247">-2146825267</span><span class="sxs-lookup"><span data-stu-id="ef539-247">-2146825267</span></span><br />
<span data-ttu-id="ef539-248">0x800A0BCD</span><span class="sxs-lookup"><span data-stu-id="ef539-248">0x800A0BCD</span></span></p></td>
<td><p><span data-ttu-id="ef539-p110"><strong>BOF</strong> 或 <strong>EOF</strong> 为 True，或者当前记录已被删除。所请求的操作需要当前记录。</span><span class="sxs-lookup"><span data-stu-id="ef539-p110">Either <strong>BOF</strong> or <strong>EOF</strong> is True, or the current record has been deleted. Requested operation requires a current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-251"><strong>adErrNotExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-251"><strong>adErrNotExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-252">3715</span><span class="sxs-lookup"><span data-stu-id="ef539-252">3715</span></span><br />
<span data-ttu-id="ef539-253">-2146824573</span><span class="sxs-lookup"><span data-stu-id="ef539-253">-2146824573</span></span><br />
<span data-ttu-id="ef539-254">0x800A0E83</span><span class="sxs-lookup"><span data-stu-id="ef539-254">0x800A0E83</span></span></p></td>
<td><p><span data-ttu-id="ef539-255">没有执行时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-255">Operation cannot be performed while not executing.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-256"><strong>adErrNotReentrant</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-256"><strong>adErrNotReentrant</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-257">3710</span><span class="sxs-lookup"><span data-stu-id="ef539-257">3710</span></span><br />
<span data-ttu-id="ef539-258">-2146824578</span><span class="sxs-lookup"><span data-stu-id="ef539-258">-2146824578</span></span><br />
<span data-ttu-id="ef539-259">0x800A0E7E</span><span class="sxs-lookup"><span data-stu-id="ef539-259">0x800A0E7E</span></span></p></td>
<td><p><span data-ttu-id="ef539-260">在处理事件的过程中，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-260">Operation cannot be performed while processing event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-261"><strong>adErrObjectClosed</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-261"><strong>adErrObjectClosed</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-262">3704</span><span class="sxs-lookup"><span data-stu-id="ef539-262">3704</span></span><br />
<span data-ttu-id="ef539-263">-2146824584</span><span class="sxs-lookup"><span data-stu-id="ef539-263">-2146824584</span></span><br />
<span data-ttu-id="ef539-264">0x800A0E78</span><span class="sxs-lookup"><span data-stu-id="ef539-264">0x800A0E78</span></span></p></td>
<td><p><span data-ttu-id="ef539-265">对象关闭时不允许操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-265">Operation is not allowed when the object is closed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-266"><strong>adErrObjectInCollection</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-266"><strong>adErrObjectInCollection</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-267">3367</span><span class="sxs-lookup"><span data-stu-id="ef539-267">3367</span></span><br />
<span data-ttu-id="ef539-268">-2146824921</span><span class="sxs-lookup"><span data-stu-id="ef539-268">-2146824921</span></span><br />
<span data-ttu-id="ef539-269">0x800A0D27</span><span class="sxs-lookup"><span data-stu-id="ef539-269">0x800A0D27</span></span></p></td>
<td><p><span data-ttu-id="ef539-p111">对象已在集合中。不能追加。</span><span class="sxs-lookup"><span data-stu-id="ef539-p111">Object is already in collection. Cannot append.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-272"><strong>adErrObjectNotSet</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-272"><strong>adErrObjectNotSet</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-273">3420</span><span class="sxs-lookup"><span data-stu-id="ef539-273">3420</span></span><br />
<span data-ttu-id="ef539-274">-2146824868</span><span class="sxs-lookup"><span data-stu-id="ef539-274">-2146824868</span></span><br />
<span data-ttu-id="ef539-275">0x800A0D5C</span><span class="sxs-lookup"><span data-stu-id="ef539-275">0x800A0D5C</span></span></p></td>
<td><p><span data-ttu-id="ef539-276">对象不再有效。</span><span class="sxs-lookup"><span data-stu-id="ef539-276">Object is no longer valid.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-277"><strong>adErrObjectOpen</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-277"><strong>adErrObjectOpen</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-278">3705</span><span class="sxs-lookup"><span data-stu-id="ef539-278">3705</span></span><br />
<span data-ttu-id="ef539-279">-2146824583</span><span class="sxs-lookup"><span data-stu-id="ef539-279">-2146824583</span></span><br />
<span data-ttu-id="ef539-280">0x800A0E79</span><span class="sxs-lookup"><span data-stu-id="ef539-280">0x800A0E79</span></span></p></td>
<td><p><span data-ttu-id="ef539-281">对象打开时不允许操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-281">Operation is not allowed when the object is open.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-282"><strong>adErrOpeningFile</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-282"><strong>adErrOpeningFile</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-283">3002</span><span class="sxs-lookup"><span data-stu-id="ef539-283">3002</span></span><br />
<span data-ttu-id="ef539-284">-2146825286</span><span class="sxs-lookup"><span data-stu-id="ef539-284">-2146825286</span></span><br />
<span data-ttu-id="ef539-285">0x800A0BBA</span><span class="sxs-lookup"><span data-stu-id="ef539-285">0x800A0BBA</span></span></p></td>
<td><p><span data-ttu-id="ef539-286">无法打开文件。</span><span class="sxs-lookup"><span data-stu-id="ef539-286">File could not be opened.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-287"><strong>adErrOperationCancelled</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-287"><strong>adErrOperationCancelled</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-288">3712</span><span class="sxs-lookup"><span data-stu-id="ef539-288">3712</span></span><br />
<span data-ttu-id="ef539-289">-2146824576</span><span class="sxs-lookup"><span data-stu-id="ef539-289">-2146824576</span></span><br />
<span data-ttu-id="ef539-290">0x800A0E80</span><span class="sxs-lookup"><span data-stu-id="ef539-290">0x800A0E80</span></span></p></td>
<td><p><span data-ttu-id="ef539-291">操作已被用户取消。</span><span class="sxs-lookup"><span data-stu-id="ef539-291">Operation has been cancelled by the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-292"><strong>adErrOutOfSpace</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-292"><strong>adErrOutOfSpace</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-293">3734</span><span class="sxs-lookup"><span data-stu-id="ef539-293">3734</span></span><br />
<span data-ttu-id="ef539-294">-2146824554</span><span class="sxs-lookup"><span data-stu-id="ef539-294">-2146824554</span></span><br />
<span data-ttu-id="ef539-295">0x800A0E96</span><span class="sxs-lookup"><span data-stu-id="ef539-295">0x800A0E96</span></span></p></td>
<td><p><span data-ttu-id="ef539-p112">无法执行操作。提供程序无法获取足够的存储空间。</span><span class="sxs-lookup"><span data-stu-id="ef539-p112">Operation cannot be performed. Provider cannot obtain enough storage space.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-298"><strong>adErrPermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-298"><strong>adErrPermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-299">3720</span><span class="sxs-lookup"><span data-stu-id="ef539-299">3720</span></span><br />
<span data-ttu-id="ef539-300">-2146824568</span><span class="sxs-lookup"><span data-stu-id="ef539-300">-2146824568</span></span><br />
<span data-ttu-id="ef539-301">0x800A0E88</span><span class="sxs-lookup"><span data-stu-id="ef539-301">0x800A0E88</span></span></p></td>
<td><p><span data-ttu-id="ef539-302">权限不足，阻止写入字段。</span><span class="sxs-lookup"><span data-stu-id="ef539-302">Insufficent permission prevents writing to the field.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-303"><strong>adErrProviderFailed</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-303"><strong>adErrProviderFailed</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-304">3000</span><span class="sxs-lookup"><span data-stu-id="ef539-304">3000</span></span><br />
<span data-ttu-id="ef539-305">-2146825288</span><span class="sxs-lookup"><span data-stu-id="ef539-305">-2146825288</span></span><br />
<span data-ttu-id="ef539-306">0x800A0BB8</span><span class="sxs-lookup"><span data-stu-id="ef539-306">0x800A0BB8</span></span></p></td>
<td><p><span data-ttu-id="ef539-307">提供程序未能执行请求的操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-307">Provider failed to perform the requested operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-308"><strong>adErrProviderNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-308"><strong>adErrProviderNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-309">3706</span><span class="sxs-lookup"><span data-stu-id="ef539-309">3706</span></span><br />
<span data-ttu-id="ef539-310">-2146824582</span><span class="sxs-lookup"><span data-stu-id="ef539-310">-2146824582</span></span><br />
<span data-ttu-id="ef539-311">0x800A0E7A</span><span class="sxs-lookup"><span data-stu-id="ef539-311">0x800A0E7A</span></span></p></td>
<td><p><span data-ttu-id="ef539-p113">找不到提供程序。该程序可能未正确安装。</span><span class="sxs-lookup"><span data-stu-id="ef539-p113">Provider cannot be found. It may not be properly installed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-314"><strong>adErrReadFile</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-314"><strong>adErrReadFile</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-315">3003</span><span class="sxs-lookup"><span data-stu-id="ef539-315">3003</span></span><br />
<span data-ttu-id="ef539-316">-2146825285</span><span class="sxs-lookup"><span data-stu-id="ef539-316">-2146825285</span></span><br />
<span data-ttu-id="ef539-317">0x800A0BBB</span><span class="sxs-lookup"><span data-stu-id="ef539-317">0x800A0BBB</span></span></p></td>
<td><p><span data-ttu-id="ef539-318">无法读取文件。</span><span class="sxs-lookup"><span data-stu-id="ef539-318">File could not be read.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-319"><strong>adErrResourceExists</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-319"><strong>adErrResourceExists</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-320">3731</span><span class="sxs-lookup"><span data-stu-id="ef539-320">3731</span></span><br />
<span data-ttu-id="ef539-321">-2146824557</span><span class="sxs-lookup"><span data-stu-id="ef539-321">-2146824557</span></span><br />
<span data-ttu-id="ef539-322">0x800A0E93</span><span class="sxs-lookup"><span data-stu-id="ef539-322">0x800A0E93</span></span></p></td>
<td><p><span data-ttu-id="ef539-p114">无法执行复制操作。由目标 URL 命名的对象已经存在。指定 <strong>adCopyOverwrite</strong> 替换该对象。</span><span class="sxs-lookup"><span data-stu-id="ef539-p114">Copy operation cannot be performed. Object named by destination URL already exists. Specify <strong>adCopyOverwrite</strong> to replace the object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-326"><strong>adErrResourceLocked</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-326"><strong>adErrResourceLocked</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-327">3730</span><span class="sxs-lookup"><span data-stu-id="ef539-327">3730</span></span><br />
<span data-ttu-id="ef539-328">-2146824558</span><span class="sxs-lookup"><span data-stu-id="ef539-328">-2146824558</span></span><br />
<span data-ttu-id="ef539-329">0x800A0E92</span><span class="sxs-lookup"><span data-stu-id="ef539-329">0x800A0E92</span></span></p></td>
<td><p><span data-ttu-id="ef539-p115">由指定的 URL 表示的对象被一个或多个其他进程锁定。请等待该进程完成，然后重试该操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-p115">Object represented by the specified URL is locked by one or more other processes. Wait until the process has finished and attempt the operation again.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-332"><strong>adErrResourceOutOfScope</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-332"><strong>adErrResourceOutOfScope</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-333">3735</span><span class="sxs-lookup"><span data-stu-id="ef539-333">3735</span></span><br />
<span data-ttu-id="ef539-334">-2146824553</span><span class="sxs-lookup"><span data-stu-id="ef539-334">-2146824553</span></span><br />
<span data-ttu-id="ef539-335">0x800A0E97</span><span class="sxs-lookup"><span data-stu-id="ef539-335">0x800A0E97</span></span></p></td>
<td><p><span data-ttu-id="ef539-336">源 URL 或目标 URL 在当前记录的范围之外。</span><span class="sxs-lookup"><span data-stu-id="ef539-336">Source or destination URL is outside the scope of the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-337"><strong>adErrSchemaViolation</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-337"><strong>adErrSchemaViolation</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-338">3722</span><span class="sxs-lookup"><span data-stu-id="ef539-338">3722</span></span><br />
<span data-ttu-id="ef539-339">-2146824566</span><span class="sxs-lookup"><span data-stu-id="ef539-339">-2146824566</span></span><br />
<span data-ttu-id="ef539-340">0x800A0E8A</span><span class="sxs-lookup"><span data-stu-id="ef539-340">0x800A0E8A</span></span></p></td>
<td><p><span data-ttu-id="ef539-341">数据值与数据类型或字段的约束冲突。</span><span class="sxs-lookup"><span data-stu-id="ef539-341">Data value conflicts with the data type or constraints of the field.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-342"><strong>adErrSignMismatch</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-342"><strong>adErrSignMismatch</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-343">3723</span><span class="sxs-lookup"><span data-stu-id="ef539-343">3723</span></span><br />
<span data-ttu-id="ef539-344">-2146824565</span><span class="sxs-lookup"><span data-stu-id="ef539-344">-2146824565</span></span><br />
<span data-ttu-id="ef539-345">0x800A0E8B</span><span class="sxs-lookup"><span data-stu-id="ef539-345">0x800A0E8B</span></span></p></td>
<td><p><span data-ttu-id="ef539-346">转换失败，原因是数据值有符号，而提供程序所使用的字段数据类型无符号。</span><span class="sxs-lookup"><span data-stu-id="ef539-346">Conversion failed because the data value was signed and the field data type used by the provider was unsigned.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-347"><strong>adErrStillConnecting</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-347"><strong>adErrStillConnecting</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-348">3713</span><span class="sxs-lookup"><span data-stu-id="ef539-348">3713</span></span><br />
<span data-ttu-id="ef539-349">-2146824575</span><span class="sxs-lookup"><span data-stu-id="ef539-349">-2146824575</span></span><br />
<span data-ttu-id="ef539-350">0x800A0E81</span><span class="sxs-lookup"><span data-stu-id="ef539-350">0x800A0E81</span></span></p></td>
<td><p><span data-ttu-id="ef539-351">在异步连接时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-351">Operation cannot be performed while connecting aynchronously.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-352"><strong>adErrStillExecuting</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-352"><strong>adErrStillExecuting</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-353">3711</span><span class="sxs-lookup"><span data-stu-id="ef539-353">3711</span></span><br />
<span data-ttu-id="ef539-354">-2146824577</span><span class="sxs-lookup"><span data-stu-id="ef539-354">-2146824577</span></span><br />
<span data-ttu-id="ef539-355">0x800A0E7F</span><span class="sxs-lookup"><span data-stu-id="ef539-355">0x800A0E7F</span></span></p></td>
<td><p><span data-ttu-id="ef539-356">在异步执行时，无法执行操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-356">Operation cannot be performed while executing asynchronously.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-357"><strong>adErrTreePermissionDenied</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-357"><strong>adErrTreePermissionDenied</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-358">3728</span><span class="sxs-lookup"><span data-stu-id="ef539-358">3728</span></span><br />
<span data-ttu-id="ef539-359">-2146824560</span><span class="sxs-lookup"><span data-stu-id="ef539-359">-2146824560</span></span><br />
<span data-ttu-id="ef539-360">0x800A0E90</span><span class="sxs-lookup"><span data-stu-id="ef539-360">0x800A0E90</span></span></p></td>
<td><p><span data-ttu-id="ef539-361">权限不足，无法访问树或子树。</span><span class="sxs-lookup"><span data-stu-id="ef539-361">Permissions are insufficient to access tree or subtree.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-362"><strong>adErrUnavailable</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-362"><strong>adErrUnavailable</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-363">3736</span><span class="sxs-lookup"><span data-stu-id="ef539-363">3736</span></span><br />
<span data-ttu-id="ef539-364">-2146824552</span><span class="sxs-lookup"><span data-stu-id="ef539-364">-2146824552</span></span><br />
<span data-ttu-id="ef539-365">0x800A0E98</span><span class="sxs-lookup"><span data-stu-id="ef539-365">0x800A0E98</span></span></p></td>
<td><p><span data-ttu-id="ef539-p116">操作未能完成，状态不可用。可能是字段不可用或未尝试任何操作。</span><span class="sxs-lookup"><span data-stu-id="ef539-p116">Operation failed to complete and the status is unavailable. The field may be unavailable or the operation was not attempted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-368"><strong>adErrUnsafeOperation</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-368"><strong>adErrUnsafeOperation</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-369">3716</span><span class="sxs-lookup"><span data-stu-id="ef539-369">3716</span></span><br />
<span data-ttu-id="ef539-370">-2146824572</span><span class="sxs-lookup"><span data-stu-id="ef539-370">-2146824572</span></span><br />
<span data-ttu-id="ef539-371">0x800A0E84</span><span class="sxs-lookup"><span data-stu-id="ef539-371">0x800A0E84</span></span></p></td>
<td><p><span data-ttu-id="ef539-372">此计算机上的安全设置禁止访问其他域上的数据源。</span><span class="sxs-lookup"><span data-stu-id="ef539-372">Safety settings on this computer prohibit accessing a data source on another domain.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-373"><strong>adErrURLDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-373"><strong>adErrURLDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-374">3727</span><span class="sxs-lookup"><span data-stu-id="ef539-374">3727</span></span><br />
<span data-ttu-id="ef539-375">-2146824561</span><span class="sxs-lookup"><span data-stu-id="ef539-375">-2146824561</span></span><br />
<span data-ttu-id="ef539-376">0x800A0E8F</span><span class="sxs-lookup"><span data-stu-id="ef539-376">0x800A0E8F</span></span></p></td>
<td><p><span data-ttu-id="ef539-377">源 URL 或目标 URL 的父级不存在。</span><span class="sxs-lookup"><span data-stu-id="ef539-377">Either the source URL or the parent of the destination URL does not exist.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-378"><strong>adErrURLNamedRowDoesNotExist</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-378"><strong>adErrURLNamedRowDoesNotExist</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-379">3737</span><span class="sxs-lookup"><span data-stu-id="ef539-379">3737</span></span><br />
<span data-ttu-id="ef539-380">-2146824551</span><span class="sxs-lookup"><span data-stu-id="ef539-380">-2146824551</span></span><br />
<span data-ttu-id="ef539-381">0x800A0E99</span><span class="sxs-lookup"><span data-stu-id="ef539-381">0x800A0E99</span></span></p></td>
<td><p><span data-ttu-id="ef539-382">此 URL 指定的记录不存在。</span><span class="sxs-lookup"><span data-stu-id="ef539-382">Record named by this URL does not exist.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-383"><strong>adErrVolumeNotFound</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-383"><strong>adErrVolumeNotFound</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-384">3733</span><span class="sxs-lookup"><span data-stu-id="ef539-384">3733</span></span><br />
<span data-ttu-id="ef539-385">-2146824555</span><span class="sxs-lookup"><span data-stu-id="ef539-385">-2146824555</span></span><br />
<span data-ttu-id="ef539-386">0x800A0E95</span><span class="sxs-lookup"><span data-stu-id="ef539-386">0x800A0E95</span></span></p></td>
<td><p><span data-ttu-id="ef539-p117">提供程序找不到 URL 指定的存储设备。请确保键入的 URL 正确。</span><span class="sxs-lookup"><span data-stu-id="ef539-p117">Provider cannot locate the storage device indicated by the URL. Make sure the URL is typed correctly.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-389"><strong>adErrWriteFile</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-389"><strong>adErrWriteFile</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-390">3004</span><span class="sxs-lookup"><span data-stu-id="ef539-390">3004</span></span><br />
<span data-ttu-id="ef539-391">-2146825284</span><span class="sxs-lookup"><span data-stu-id="ef539-391">-2146825284</span></span><br />
<span data-ttu-id="ef539-392">0x800A0BBC</span><span class="sxs-lookup"><span data-stu-id="ef539-392">0x800A0BBC</span></span></p></td>
<td><p><span data-ttu-id="ef539-393">写入文件失败。</span><span class="sxs-lookup"><span data-stu-id="ef539-393">Write to file failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-394"><strong>adWrnSecurityDialog</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-394"><strong>adWrnSecurityDialog</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-395">3717</span><span class="sxs-lookup"><span data-stu-id="ef539-395">3717</span></span><br />
<span data-ttu-id="ef539-396">-2146824571</span><span class="sxs-lookup"><span data-stu-id="ef539-396">-2146824571</span></span><br />
<span data-ttu-id="ef539-397">0x800A0E85</span><span class="sxs-lookup"><span data-stu-id="ef539-397">0x800A0E85</span></span></p></td>
<td><p><span data-ttu-id="ef539-p118">仅供内部使用。请勿使用。</span><span class="sxs-lookup"><span data-stu-id="ef539-p118">For internal use only. Don't use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-400"><strong>adWrnSecurityDialogHeader</strong></span><span class="sxs-lookup"><span data-stu-id="ef539-400"><strong>adWrnSecurityDialogHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="ef539-401">3718</span><span class="sxs-lookup"><span data-stu-id="ef539-401">3718</span></span><br />
<span data-ttu-id="ef539-402">-2146824570</span><span class="sxs-lookup"><span data-stu-id="ef539-402">-2146824570</span></span><br />
<span data-ttu-id="ef539-403">0x800A0E86</span><span class="sxs-lookup"><span data-stu-id="ef539-403">0x800A0E86</span></span></p></td>
<td><p><span data-ttu-id="ef539-p119">仅供内部使用。请勿使用。</span><span class="sxs-lookup"><span data-stu-id="ef539-p119">For internal use only. Don't use.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ef539-406">**ADO/WFC 等效值**</span><span class="sxs-lookup"><span data-stu-id="ef539-406">**ADO/WFC Equivalent**</span></span>

<span data-ttu-id="ef539-407">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="ef539-407">Package: **com.ms.wfc.data**</span></span>

<span data-ttu-id="ef539-408">仅定义了 ADO/WFC 等效值的以下子集。</span><span class="sxs-lookup"><span data-stu-id="ef539-408">Only the following subsets of ADO/WFC equivalents are defined.</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ef539-409">常量</span><span class="sxs-lookup"><span data-stu-id="ef539-409">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef539-410">AdoEnums.ErrorValue.BOUNDTOCOMMAND</span><span class="sxs-lookup"><span data-stu-id="ef539-410">AdoEnums.ErrorValue.BOUNDTOCOMMAND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-411">AdoEnums.ErrorValue.DATACONVERSION</span><span class="sxs-lookup"><span data-stu-id="ef539-411">AdoEnums.ErrorValue.DATACONVERSION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-412">AdoEnums.ErrorValue.FEATURENOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef539-412">AdoEnums.ErrorValue.FEATURENOTAVAILABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-413">AdoEnums.ErrorValue.ILLEGALOPERATION</span><span class="sxs-lookup"><span data-stu-id="ef539-413">AdoEnums.ErrorValue.ILLEGALOPERATION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-414">AdoEnums.ErrorValue.INTRANSACTION</span><span class="sxs-lookup"><span data-stu-id="ef539-414">AdoEnums.ErrorValue.INTRANSACTION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-415">AdoEnums.ErrorValue.INVALIDARGUMENT</span><span class="sxs-lookup"><span data-stu-id="ef539-415">AdoEnums.ErrorValue.INVALIDARGUMENT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-416">AdoEnums.ErrorValue.INVALIDCONNECTION</span><span class="sxs-lookup"><span data-stu-id="ef539-416">AdoEnums.ErrorValue.INVALIDCONNECTION</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-417">AdoEnums.ErrorValue.INVALIDPARAMINFO</span><span class="sxs-lookup"><span data-stu-id="ef539-417">AdoEnums.ErrorValue.INVALIDPARAMINFO</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-418">AdoEnums.ErrorValue.ITEMNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="ef539-418">AdoEnums.ErrorValue.ITEMNOTFOUND</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-419">AdoEnums.ErrorValue.NOCURRENTRECORD</span><span class="sxs-lookup"><span data-stu-id="ef539-419">AdoEnums.ErrorValue.NOCURRENTRECORD</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-420">AdoEnums.ErrorValue.NOTEXECUTING</span><span class="sxs-lookup"><span data-stu-id="ef539-420">AdoEnums.ErrorValue.NOTEXECUTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-421">AdoEnums.ErrorValue.NOTREENTRANT</span><span class="sxs-lookup"><span data-stu-id="ef539-421">AdoEnums.ErrorValue.NOTREENTRANT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-422">AdoEnums.ErrorValue.OBJECTCLOSED</span><span class="sxs-lookup"><span data-stu-id="ef539-422">AdoEnums.ErrorValue.OBJECTCLOSED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-423">AdoEnums.ErrorValue.OBJECTINCOLLECTION</span><span class="sxs-lookup"><span data-stu-id="ef539-423">AdoEnums.ErrorValue.OBJECTINCOLLECTION</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-424">AdoEnums.ErrorValue.OBJECTNOTSET</span><span class="sxs-lookup"><span data-stu-id="ef539-424">AdoEnums.ErrorValue.OBJECTNOTSET</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-425">AdoEnums.ErrorValue.OBJECTOPEN</span><span class="sxs-lookup"><span data-stu-id="ef539-425">AdoEnums.ErrorValue.OBJECTOPEN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-426">AdoEnums.ErrorValue.OPERATIONCANCELLED</span><span class="sxs-lookup"><span data-stu-id="ef539-426">AdoEnums.ErrorValue.OPERATIONCANCELLED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-427">AdoEnums.ErrorValue.PROVIDERNOTFOUND</span><span class="sxs-lookup"><span data-stu-id="ef539-427">AdoEnums.ErrorValue.PROVIDERNOTFOUND</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-428">AdoEnums.ErrorValue.STILLCONNECTING</span><span class="sxs-lookup"><span data-stu-id="ef539-428">AdoEnums.ErrorValue.STILLCONNECTING</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef539-429">AdoEnums.ErrorValue.STILLEXECUTING</span><span class="sxs-lookup"><span data-stu-id="ef539-429">AdoEnums.ErrorValue.STILLEXECUTING</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef539-430">AdoEnums.ErrorValue.UNSAFEOPERATION</span><span class="sxs-lookup"><span data-stu-id="ef539-430">AdoEnums.ErrorValue.UNSAFEOPERATION</span></span></p></td>
</tr>
</tbody>
</table>
