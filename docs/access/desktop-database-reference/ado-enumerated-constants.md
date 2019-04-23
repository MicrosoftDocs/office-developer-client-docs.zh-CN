---
title: ADO 枚举常量
TOCTitle: ADO enumerated constants
ms:assetid: 7c983acd-8b38-dc3c-6704-46e649ebb7d6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249522(v=office.15)
ms:contentKeyID: 48545841
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 05e5d3a77dc7db5ef5a0d81a3f13d5fc5987f5de
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283406"
---
# <a name="ado-enumerated-constants"></a><span data-ttu-id="b44ed-102">ADO 枚举常量</span><span class="sxs-lookup"><span data-stu-id="b44ed-102">ADO enumerated constants</span></span>

<span data-ttu-id="b44ed-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b44ed-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b44ed-p101">为了有助于进行调试，ADO 枚举将列出每个常量的值。但是，此值仅仅是建议性的，不同的 ADO 版本可能会各不相同。代码应当只依赖于每个枚举常量的名称，而不是实际值。</span><span class="sxs-lookup"><span data-stu-id="b44ed-p101">To assist in debugging, the ADO enumerations list a value for each constant. However, this value is purely advisory, and may change from one release of ADO to another. Your code should only depend on the name, not the actual value, of each enumerated constant.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="even">
<th><span data-ttu-id="b44ed-107">枚举常量</span><span class="sxs-lookup"><span data-stu-id="b44ed-107">Enumerated constant</span></span></th>
<th><span data-ttu-id="b44ed-108">说明</span><span class="sxs-lookup"><span data-stu-id="b44ed-108">Description</span></span></th>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-109"><a href="adcprop-asyncthreadpriority-enum.md">ADCPROP_ASYNCTHREADPRIORITY_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-109"><a href="adcprop-asyncthreadpriority-enum.md">ADCPROP_ASYNCTHREADPRIORITY_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-110">对于 RDS <strong>Recordset</strong> 对象，指定用于检索数据的异步线程的执行优先级。</span><span class="sxs-lookup"><span data-stu-id="b44ed-110">For an RDS <strong>Recordset</strong> object, specifies the execution priority of the asynchronous thread that retrieves data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-111"><a href="adcprop-autorecalc-enum.md">ADCPROP_AUTORECALC_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-111"><a href="adcprop-autorecalc-enum.md">ADCPROP_AUTORECALC_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-112">指定 <strong>MSDataShape</strong> 提供程序何时重新计算 <strong>Recordset</strong> 中的聚合和计算列。</span><span class="sxs-lookup"><span data-stu-id="b44ed-112">Specifies when the <strong>MSDataShape</strong> provider re-calculates aggregate and calculated columns in a hierarchical <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-113"><a href="adcprop-updatecriteria-enum.md">ADCPROP_UPDATECRITERIA_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-113"><a href="adcprop-updatecriteria-enum.md">ADCPROP_UPDATECRITERIA_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-114">指定在使用 <strong>Recordset</strong> 对象来对数据源中的行进行开放式更新期间可以用哪些字段来检测冲突。</span><span class="sxs-lookup"><span data-stu-id="b44ed-114">Specifies which fields can be used to detect conflicts during an optimistic update of a row of the data source with a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-115"><a href="adcprop-updateresync-enum.md">ADCPROP_UPDATERESYNC_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-115"><a href="adcprop-updateresync-enum.md">ADCPROP_UPDATERESYNC_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-116">指定 <strong>UpdateBatch</strong> 方法后面是否跟随隐式的 <strong>Resync</strong> 方法操作，如果跟随，则指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="b44ed-116">Specifies whether the <strong>UpdateBatch</strong> method is followed by an implicit <strong>Resync</strong> method operation and if so, the scope of that operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-117"><a href="affectenum.md">AffectEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-117"><a href="affectenum.md">AffectEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-118">指定操作会影响哪些记录。</span><span class="sxs-lookup"><span data-stu-id="b44ed-118">Specifies which records are affected by an operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-119"><a href="bookmarkenum.md">BookmarkEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-119"><a href="bookmarkenum.md">BookmarkEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-120">指定一个书签，以指示操作应开始的位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-120">Specifies a bookmark indicating where the operation should begin.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-121"><a href="commandtypeenum.md">CommandTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-121"><a href="commandtypeenum.md">CommandTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-122">指定应当如何解释命令参数。</span><span class="sxs-lookup"><span data-stu-id="b44ed-122">Specifies how a command argument should be interpreted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-123"><a href="compareenum.md">CompareEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-123"><a href="compareenum.md">CompareEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-124">指定通过记录书签表示的两个记录的相对位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-124">Specifies the relative position of two records represented by their bookmarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-125"><a href="connectmodeenum.md">ConnectModeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-125"><a href="connectmodeenum.md">ConnectModeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-126">指定可用于执行以下操作的权限：修改 <strong>Connection</strong> 中的数据、打开 <strong>Record</strong>，或指定 <strong>Record</strong> 和 <strong>Stream</strong> 对象的 <strong>Mode</strong> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="b44ed-126">Specifies the available permissions for modifying data in a <strong>Connection</strong>, opening a <strong>Record</strong>, or specifying values for the <strong>Mode</strong> property of the <strong>Record</strong> and <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-127"><a href="connectoptionenum.md">ConnectOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-127"><a href="connectoptionenum.md">ConnectOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-128">指定在建立连接之后（同步）或之前（异步）是否应当返回 <strong>Connection</strong> 对象的 <strong>Open</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="b44ed-128">Specifies whether the <strong>Open</strong> method of a <strong>Connection</strong> object should return after (synchronously) or before (asynchronously) the connection is established.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-129"><a href="connectpromptenum.md">ConnectPromptEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-129"><a href="connectpromptenum.md">ConnectPromptEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-130">指定在打开与 ODBC 数据源的连接时，是否应当显示对话框，提示输入缺少的参数。</span><span class="sxs-lookup"><span data-stu-id="b44ed-130">Specifies whether a dialog box should be displayed to prompt for missing parameters when opening a connection to an ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-131"><a href="copyrecordoptionsenum.md">CopyRecordOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-131"><a href="copyrecordoptionsenum.md">CopyRecordOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-132">指定 <strong>CopyRecord</strong> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b44ed-132">Specifies the behavior of the <strong>CopyRecord</strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-133"><a href="cursorlocationenum.md">CursorLocationEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-133"><a href="cursorlocationenum.md">CursorLocationEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-134">指定游标引擎的位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-134">Specifies the location of the cursor engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-135"><a href="cursoroptionenum.md">CursorOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-135"><a href="cursoroptionenum.md">CursorOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-136">指定应针对哪项功能来测试 <strong>Supports</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="b44ed-136">Specifies what functionality the <strong>Supports</strong> method should test for.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-137"><a href="cursortypeenum.md">CursorTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-137"><a href="cursortypeenum.md">CursorTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-138">指定在 <strong>Recordset</strong> 对象中使用的游标的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-138">Specifies the type of cursor used in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-139"><a href="datatypeenum.md">DataTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-139"><a href="datatypeenum.md">DataTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-140">指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-140">Specifies the data type of a <strong>Field</strong>, <strong>Parameter</strong>, or <strong>Property</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-141"><a href="editmodeenum.md">EditModeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-141"><a href="editmodeenum.md">EditModeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-142">指定记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="b44ed-142">Specifies the editing status of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-143"><a href="errorvalueenum.md">ErrorValueEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-143"><a href="errorvalueenum.md">ErrorValueEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-144">指定 ADO 运行时错误的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-144">Specifies the type of ADO run-time error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-145"><a href="eventreasonenum.md">EventReasonEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-145"><a href="eventreasonenum.md">EventReasonEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-146">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="b44ed-146">Specifies the reason that caused an event to occur.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-147"><a href="eventstatusenum.md">EventStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-147"><a href="eventstatusenum.md">EventStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-148">指定事件执行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="b44ed-148">Specifies the current status of the execution of an event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-149"><a href="executeoptionenum.md">ExecuteOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-149"><a href="executeoptionenum.md">ExecuteOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-150">指定提供程序应当如何执行命令。</span><span class="sxs-lookup"><span data-stu-id="b44ed-150">Specifies how a provider should execute a command.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-151"><a href="fieldenum.md">FieldEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-151"><a href="fieldenum.md">FieldEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-152">指定在 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合中引用的特殊字段。</span><span class="sxs-lookup"><span data-stu-id="b44ed-152">Specifies the special fields referenced in a <strong>Record</strong> object's <strong>Fields</strong> collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-153"><a href="fieldattributeenum.md">FieldAttributeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-153"><a href="fieldattributeenum.md">FieldAttributeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-154">指定 <strong>Field</strong> 对象的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="b44ed-154">Specifies one or more attributes of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-155"><a href="fieldstatusenum.md">FieldStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-155"><a href="fieldstatusenum.md">FieldStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-156">指定 <strong>Field</strong> 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="b44ed-156">Specifies the status of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-157"><a href="filtergroupenum.md">FilterGroupEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-157"><a href="filtergroupenum.md">FilterGroupEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-158">指定要从 <strong>Recordset</strong> 中筛选的记录组。</span><span class="sxs-lookup"><span data-stu-id="b44ed-158">Specifies the group of records to be filtered from a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-159"><a href="getrowsoptionenum.md">GetRowsOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-159"><a href="getrowsoptionenum.md">GetRowsOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-160">指定要从 <strong>Recordset</strong> 中检索多少记录。</span><span class="sxs-lookup"><span data-stu-id="b44ed-160">Specifies how many records to retrieve from a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-161"><a href="isolationlevelenum.md">IsolationLevelEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-161"><a href="isolationlevelenum.md">IsolationLevelEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-162">指定 <strong>Connection</strong> 对象的事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="b44ed-162">Specifies the level of transaction isolation for a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-163"><a href="lineseparatorsenum.md">LineSeparatorsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-163"><a href="lineseparatorsenum.md">LineSeparatorsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-164">指定在文本 <strong>Stream</strong> 对象中用作行分隔符的字符。</span><span class="sxs-lookup"><span data-stu-id="b44ed-164">Specifies the character used as a line separator in text <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-165"><a href="locktypeenum.md">LockTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-165"><a href="locktypeenum.md">LockTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-166">指定在编辑过程中对记录设置的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-166">Specifies the type of lock placed on records during editing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-167"><a href="marshaloptionsenum.md">MarshalOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-167"><a href="marshaloptionsenum.md">MarshalOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-168">指定哪些记录应当返回到服务器。</span><span class="sxs-lookup"><span data-stu-id="b44ed-168">Specifies which records should be returned to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-169"><a href="moverecordoptionsenum.md">MoveRecordOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-169"><a href="moverecordoptionsenum.md">MoveRecordOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-170">指定 <strong>Record</strong> 对象的 <strong>MoveRecord</strong> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="b44ed-170">Specifies the behavior of the <strong>Record</strong> object <strong>MoveRecord</strong> method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-171"><a href="objectstateenum.md">ObjectStateEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-171"><a href="objectstateenum.md">ObjectStateEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-172">指定对象是否处于以下状态：打开还是关闭、正在连接到数据源、正在执行命令、或正在获取数据。</span><span class="sxs-lookup"><span data-stu-id="b44ed-172">Specifies whether an object is open or closed, connecting to a data source, executing a command, or fetching data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-173"><a href="parameterattributesenum.md">ParameterAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-173"><a href="parameterattributesenum.md">ParameterAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-174">指定 <strong>Parameter</strong> 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b44ed-174">Specifies the attributes of a <strong>Parameter</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-175"><a href="parameterdirectionenum.md">ParameterDirectionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-175"><a href="parameterdirectionenum.md">ParameterDirectionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-176">指定 <strong>Parameter</strong> 是否表示输入参数和/或输出参数，以及参数是否是存储过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="b44ed-176">Specifies whether the <strong>Parameter</strong> represents an input parameter, an output parameter, or both, or if the parameter is the return value from a stored procedure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-177"><a href="persistformatenum.md">PersistFormatEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-177"><a href="persistformatenum.md">PersistFormatEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-178">指定保存 <strong>Recordset</strong> 时所用的格式。</span><span class="sxs-lookup"><span data-stu-id="b44ed-178">Specifies the format in which to save a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-179"><a href="positionenum.md">PositionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-179"><a href="positionenum.md">PositionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-180">指定在 <strong>Recordset</strong> 中记录指针的当前位置。</span><span class="sxs-lookup"><span data-stu-id="b44ed-180">Specifies the current position of the record pointer within a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-181"><a href="propertyattributesenum.md">PropertyAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-181"><a href="propertyattributesenum.md">PropertyAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-182">指定 <strong>Property</strong> 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b44ed-182">Specifies the attributes of a <strong>Property</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-183"><a href="recordcreateoptionsenum.md">RecordCreateOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-183"><a href="recordcreateoptionsenum.md">RecordCreateOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-184">指定对于 <strong>Record</strong> 对象的 <strong>Open</strong> 方法，是应当打开现有 <strong>Record</strong>，还是应当创建新的 <strong>Record</strong>。</span><span class="sxs-lookup"><span data-stu-id="b44ed-184">Specifies for the <strong>Record</strong> object <strong>Open</strong> method whether an existing <strong>Record</strong> should be opened, or a new <strong>Record</strong> should be created.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-185"><a href="recordopenoptionsenum.md">RecordOpenOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-185"><a href="recordopenoptionsenum.md">RecordOpenOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-186">指定用于打开 <strong>Record</strong> 的选项。</span><span class="sxs-lookup"><span data-stu-id="b44ed-186">Specifies options for opening a <strong>Record</strong>.</span></span> <span data-ttu-id="b44ed-187">可以使用 OR 运算符将这些值组合在一起。</span><span class="sxs-lookup"><span data-stu-id="b44ed-187">These values may be combined by using an OR operator.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-188"><a href="recordstatusenum.md">RecordStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-188"><a href="recordstatusenum.md">RecordStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-189">指定记录的批更新和其他批量操作的状态。</span><span class="sxs-lookup"><span data-stu-id="b44ed-189">Specifies the status of a record with regard to batch updates and other bulk operations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-190"><a href="recordtypeenum.md">RecordTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-190"><a href="recordtypeenum.md">RecordTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-191">指定 <strong>Record</strong> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-191">Specifies the type of <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-192"><a href="resyncenum.md">ResyncEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-192"><a href="resyncenum.md">ResyncEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-193">指定是否通过调用 <strong>Resync</strong> 来覆盖基础值。</span><span class="sxs-lookup"><span data-stu-id="b44ed-193">Specifies whether underlying values are overwritten by a call to <strong>Resync</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-194"><a href="saveoptionsenum.md">SaveOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-194"><a href="saveoptionsenum.md">SaveOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-p103">指定当从 <strong>Stream</strong> 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="b44ed-p103">Specifies whether a file should be created or overwritten when saving from a <strong>Stream</strong> object. The values can be combined with an AND operator.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-197"><a href="schemaenum.md">SchemaEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-197"><a href="schemaenum.md">SchemaEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-198">指定 <strong>OpenSchema</strong> 方法所检索的架构 <strong>Recordset</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-198">Specifies the type of schema <strong>Recordset</strong> that the <strong>OpenSchema</strong> method retrieves.</span></span> <span data-ttu-id="b44ed-199">指定在 <strong>Recordset</strong> 内进行记录搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="b44ed-199">Specifies the direction of a record search within a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-200"><a href="searchdirectionenum.md">SearchDirectionEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-200"><a href="searchdirectionenum.md">SearchDirectionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-201">指定在 <strong>Recordset</strong> 中进行记录搜索的方向。指定要执行的 <strong>Seek</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-201">Specifies the direction of a record search within a <strong>Recordset</strong>.Specifies the type of <strong>Seek</strong> to execute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-202"><a href="seekenum.md">SeekEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-202"><a href="seekenum.md">SeekEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-p105">指定要执行的 <strong>Seek</strong> 的类型。指定用于打开 <strong>Stream</strong> 对象的选项。该值可以与 AND 运算符组合。</span><span class="sxs-lookup"><span data-stu-id="b44ed-p105">Specifies the type of <strong>Seek</strong> to execute.Specifies options for opening a <strong>Stream</strong> object. The values can be combined with an AND operator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-205"><a href="streamopenoptionsenum.md">StreamOpenOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-205"><a href="streamopenoptionsenum.md">StreamOpenOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-p106">指定用于打开 <strong>Stream</strong> 对象的选项。这些值可以与 AND 运算符组合。指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。</span><span class="sxs-lookup"><span data-stu-id="b44ed-p106">Specifies options for opening a <strong>Stream</strong> object. The values can be combined with an AND operator.Specifies whether the whole stream or the next line should be read from a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-208"><a href="streamreadenum.md">StreamReadEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-208"><a href="streamreadenum.md">StreamReadEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-209">指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。指定存储在 <strong>Stream</strong> 对象中的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="b44ed-209">Specifies whether the whole stream or the next line should be read from a <strong>Stream</strong> object.Specifies the type of data stored in a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-210"><a href="streamtypeenum.md">StreamTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-210"><a href="streamtypeenum.md">StreamTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-211">指定存储在 <strong>Stream</strong> 对象中的数据的类型。指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="b44ed-211">Specifies the type of data stored in a <strong>Stream</strong> object.Specifies whether a line separator is appended to the string written to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-212"><a href="streamwriteenum.md">StreamWriteEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-212"><a href="streamwriteenum.md">StreamWriteEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-213">指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。指定检索 <strong>Recordset</strong> 时的格式为字符串。</span><span class="sxs-lookup"><span data-stu-id="b44ed-213">Specifies whether a line separator is appended to the string written to a <strong>Stream</strong> object.Specifies the format when retrieving a <strong>Recordset</strong> as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b44ed-214"><a href="stringformatenum.md">StringFormatEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-214"><a href="stringformatenum.md">StringFormatEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-215">指定检索 <strong>Recordset</strong> 时的格式为字符串。指定 <strong>Connection</strong> 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="b44ed-215">Specifies the format when retrieving a <strong>Recordset</strong> as a string.Specifies the transaction attributes of a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b44ed-216"><a href="xactattributeenum.md">XactAttributeEnum</a></span><span class="sxs-lookup"><span data-stu-id="b44ed-216"><a href="xactattributeenum.md">XactAttributeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="b44ed-217">指定 <strong>Connection</strong> 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="b44ed-217">Specifies the transaction attributes of a <strong>Connection</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>

