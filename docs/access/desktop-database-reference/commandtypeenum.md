---
title: CommandTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: CommandTypeEnum
ms:assetid: 9ad8f155-88a0-00eb-2855-1e1a2a677437
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249700(v=office.15)
ms:contentKeyID: 48546549
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: a570aaed8f0b2da415c3866ec88e7023085a1319
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887941"
---
# <a name="commandtypeenum"></a><span data-ttu-id="49cf2-102">CommandTypeEnum</span><span class="sxs-lookup"><span data-stu-id="49cf2-102">CommandTypeEnum</span></span>

<span data-ttu-id="49cf2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="49cf2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="49cf2-104">指定应当如何解释命令参数。</span><span class="sxs-lookup"><span data-stu-id="49cf2-104">Specifies how a command argument should be interpreted.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="49cf2-105">常量</span><span class="sxs-lookup"><span data-stu-id="49cf2-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="49cf2-106">值</span><span class="sxs-lookup"><span data-stu-id="49cf2-106">Value</span></span></p></th>
<th><p><span data-ttu-id="49cf2-107">说明</span><span class="sxs-lookup"><span data-stu-id="49cf2-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-108"><strong>adCmdUnspecified</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-108"><strong>adCmdUnspecified</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-109">-1</span><span class="sxs-lookup"><span data-stu-id="49cf2-109">-1</span></span></p></td>
<td><p><span data-ttu-id="49cf2-110">不指定命令类型参数。</span><span class="sxs-lookup"><span data-stu-id="49cf2-110">Does not specify the command type argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-111"><strong>adCmdText</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-111"><strong>adCmdText</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-112">1</span><span class="sxs-lookup"><span data-stu-id="49cf2-112">1</span></span></p></td>
<td><p><span data-ttu-id="49cf2-113">将 <a href="commandtext-property-ado.md">CommandText</a> 求值为命令或存储过程调用的文字定义。</span><span class="sxs-lookup"><span data-stu-id="49cf2-113">Evaluates <a href="commandtext-property-ado.md">CommandText</a> as a textual definition of a command or stored procedure call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-114"><strong>adCmdTable</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-114"><strong>adCmdTable</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-115">2</span><span class="sxs-lookup"><span data-stu-id="49cf2-115">2</span></span></p></td>
<td><p><span data-ttu-id="49cf2-116">将 <strong>CommandText</strong> 求值为表名，该表中的列全部由内部生成的 SQL 查询返回。</span><span class="sxs-lookup"><span data-stu-id="49cf2-116">Evaluates <strong>CommandText</strong> as a table name whose columns are all returned by an internally generated SQL query.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-117"><strong>adCmdStoredProc</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-117"><strong>adCmdStoredProc</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-118">4</span><span class="sxs-lookup"><span data-stu-id="49cf2-118">4</span></span></p></td>
<td><p><span data-ttu-id="49cf2-119">将 <strong>CommandText</strong> 求值为存储过程名称。</span><span class="sxs-lookup"><span data-stu-id="49cf2-119">Evaluates <strong>CommandText</strong> as a stored procedure name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-120"><strong>adCmdUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-120"><strong>adCmdUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-121">8</span><span class="sxs-lookup"><span data-stu-id="49cf2-121">8</span></span></p></td>
<td><p><span data-ttu-id="49cf2-p101">默认值。指示 <strong>CommandText</strong> 属性中的命令类型未知。</span><span class="sxs-lookup"><span data-stu-id="49cf2-p101">Default. Indicates that the type of command in the <strong>CommandText</strong> property is not known.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-124"><strong>adCmdFile</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-124"><strong>adCmdFile</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-125">256</span><span class="sxs-lookup"><span data-stu-id="49cf2-125">256</span></span></p></td>
<td><p><span data-ttu-id="49cf2-p102">将 <strong>CommandText</strong> 求值为永久存储的 <a href="recordset-object-ado.md">Recordset</a> 的文件名。仅与 <strong>Recordset.</strong><a href="open-method-ado-recordset.md">Open</a> 或 <a href="requery-method-ado.md">Requery</a> 一起使用。</span><span class="sxs-lookup"><span data-stu-id="49cf2-p102">Evaluates <strong>CommandText</strong> as the file name of a persistently stored <a href="recordset-object-ado.md">Recordset</a>. Used with <strong>Recordset.</strong><a href="open-method-ado-recordset.md">Open</a> or <a href="requery-method-ado.md">Requery</a> only.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-128"><strong>adCmdTableDirect</strong></span><span class="sxs-lookup"><span data-stu-id="49cf2-128"><strong>adCmdTableDirect</strong></span></span></p></td>
<td><p><span data-ttu-id="49cf2-129">512</span><span class="sxs-lookup"><span data-stu-id="49cf2-129">512</span></span></p></td>
<td><p><span data-ttu-id="49cf2-130"><strong>将 CommandText</strong>求为所有返回的列的表名。</span><span class="sxs-lookup"><span data-stu-id="49cf2-130">Evaluates <strong>CommandText</strong> as a table name whose columns are all returned.</span></span> <span data-ttu-id="49cf2-131">仅与<strong>Recordset.Open</strong>或<strong>Requery</strong>一起使用。</span><span class="sxs-lookup"><span data-stu-id="49cf2-131">Used with <strong>Recordset.Open</strong> or <strong>Requery</strong> only.</span></span> <span data-ttu-id="49cf2-132">若要使用<a href="seek-method-ado.md">Seek</a>方法，必须使用<strong>adCmdTableDirect</strong>打开<strong>记录集</strong>。</span><span class="sxs-lookup"><span data-stu-id="49cf2-132">To use the <a href="seek-method-ado.md">Seek</a> method, the <strong>Recordset</strong> must be opened with <strong>adCmdTableDirect</strong>.</span></span> <span data-ttu-id="49cf2-133">此值不能与 <a href="executeoptionenum.md">ExecuteOptionEnum</a> 值 <strong>adAsyncExecute</strong> 组合使用。</span><span class="sxs-lookup"><span data-stu-id="49cf2-133">This value cannot be combined with the <a href="executeoptionenum.md">ExecuteOptionEnum</a> value <strong>adAsyncExecute</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="49cf2-134">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="49cf2-134">ADO/WFC equivalent</span></span>

<span data-ttu-id="49cf2-135">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="49cf2-135">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="49cf2-136">常量</span><span class="sxs-lookup"><span data-stu-id="49cf2-136">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-137">AdoEnums.CommandType.UNSPECIFIED</span><span class="sxs-lookup"><span data-stu-id="49cf2-137">AdoEnums.CommandType.UNSPECIFIED</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-138">AdoEnums.CommandType.TEXT</span><span class="sxs-lookup"><span data-stu-id="49cf2-138">AdoEnums.CommandType.TEXT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-139">AdoEnums.CommandType.TABLE</span><span class="sxs-lookup"><span data-stu-id="49cf2-139">AdoEnums.CommandType.TABLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-140">AdoEnums.CommandType.STOREDPROC</span><span class="sxs-lookup"><span data-stu-id="49cf2-140">AdoEnums.CommandType.STOREDPROC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-141">AdoEnums.CommandType.UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="49cf2-141">AdoEnums.CommandType.UNKNOWN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49cf2-142">AdoEnums.CommandType.FILE</span><span class="sxs-lookup"><span data-stu-id="49cf2-142">AdoEnums.CommandType.FILE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49cf2-143">AdoEnums.CommandType.TABLEDIRECT</span><span class="sxs-lookup"><span data-stu-id="49cf2-143">AdoEnums.CommandType.TABLEDIRECT</span></span></p></td>
</tr>
</tbody>
</table>

