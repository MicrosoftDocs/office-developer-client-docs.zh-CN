---
title: ADO 枚举常量
TOCTitle: ADO Enumerated Constants
ms:assetid: 7c983acd-8b38-dc3c-6704-46e649ebb7d6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249522(v=office.15)
ms:contentKeyID: 48545841
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3e9944138dcdca49f33ca293a9bdf41d88d86e9e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882306"
---
# <a name="ado-enumerated-constants"></a><span data-ttu-id="29fe9-102">ADO 枚举常量</span><span class="sxs-lookup"><span data-stu-id="29fe9-102">ADO Enumerated Constants</span></span>


<span data-ttu-id="29fe9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="29fe9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="29fe9-p101">为了有助于进行调试，ADO 枚举将列出每个常量的值。但是，此值仅仅是建议性的，不同的 ADO 版本可能会各不相同。代码应当只依赖于每个枚举常量的名称，而不是实际值。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p101">To assist in debugging, the ADO enumerations list a value for each constant. However, this value is purely advisory, and may change from one release of ADO to another. Your code should only depend on the name, not the actual value, of each enumerated constant.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-107"><a href="adcprop-asyncthreadpriority-enum.md">ADCPROP_ASYNCTHREADPRIORITY_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-107"><a href="adcprop-asyncthreadpriority-enum.md">ADCPROP_ASYNCTHREADPRIORITY_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-108">对于 RDS <strong>Recordset</strong> 对象，指定用于检索数据的异步线程的执行优先级。</span><span class="sxs-lookup"><span data-stu-id="29fe9-108">For an RDS <strong>Recordset</strong> object, specifies the execution priority of the asynchronous thread that retrieves data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-109"><a href="adcprop-autorecalc-enum.md">ADCPROP_AUTORECALC_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-109"><a href="adcprop-autorecalc-enum.md">ADCPROP_AUTORECALC_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-110">指定<strong>MSDataShape</strong>提供程序何时重新计算分层<strong>Recordset</strong>中的聚合和计算列。</span><span class="sxs-lookup"><span data-stu-id="29fe9-110">Specifies when the <strong>MSDataShape</strong> provider re-calculates aggregate and calculated columns in a hierarchical <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-111"><a href="adcprop-updatecriteria-enum.md">ADCPROP_UPDATECRITERIA_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-111"><a href="adcprop-updatecriteria-enum.md">ADCPROP_UPDATECRITERIA_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-112">指定在使用 <strong>Recordset</strong> 对象来对数据源中的行进行开放式更新期间可以用哪些字段来检测冲突。</span><span class="sxs-lookup"><span data-stu-id="29fe9-112">Specifies which fields can be used to detect conflicts during an optimistic update of a row of the data source with a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-113"><a href="adcprop-updateresync-enum.md">ADCPROP_UPDATERESYNC_ENUM</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-113"><a href="adcprop-updateresync-enum.md">ADCPROP_UPDATERESYNC_ENUM</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-114">指定 <strong>UpdateBatch</strong> 方法后面是否跟随隐式的 <strong>Resync</strong> 方法操作，如果跟随，则指定该操作的范围。</span><span class="sxs-lookup"><span data-stu-id="29fe9-114">Specifies whether the <strong>UpdateBatch</strong> method is followed by an implicit <strong>Resync</strong> method operation and if so, the scope of that operation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-115"><a href="affectenum.md">AffectEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-115"><a href="affectenum.md">AffectEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-116">指定操作会影响哪些记录。</span><span class="sxs-lookup"><span data-stu-id="29fe9-116">Specifies which records are affected by an operation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-117"><a href="bookmarkenum.md">BookmarkEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-117"><a href="bookmarkenum.md">BookmarkEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-118">指定一个书签，以指示操作应开始的位置。</span><span class="sxs-lookup"><span data-stu-id="29fe9-118">Specifies a bookmark indicating where the operation should begin.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-119"><a href="commandtypeenum.md">CommandTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-119"><a href="commandtypeenum.md">CommandTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-120">指定应当如何解释命令参数。</span><span class="sxs-lookup"><span data-stu-id="29fe9-120">Specifies how a command argument should be interpreted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-121"><a href="compareenum.md">CompareEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-121"><a href="compareenum.md">CompareEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-122">指定通过记录书签表示的两个记录的相对位置。</span><span class="sxs-lookup"><span data-stu-id="29fe9-122">Specifies the relative position of two records represented by their bookmarks.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-123"><a href="connectmodeenum.md">ConnectModeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-123"><a href="connectmodeenum.md">ConnectModeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-124">指定可用于执行以下操作的权限：修改 <strong>Connection</strong> 中的数据、打开 <strong>Record</strong>，或指定 <strong>Record</strong> 和 <strong>Stream</strong> 对象的 <strong>Mode</strong> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="29fe9-124">Specifies the available permissions for modifying data in a <strong>Connection</strong>, opening a <strong>Record</strong>, or specifying values for the <strong>Mode</strong> property of the <strong>Record</strong> and <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-125"><a href="connectoptionenum.md">ConnectOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-125"><a href="connectoptionenum.md">ConnectOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-126">指定在建立连接之后（同步）或之前（异步）是否应返回 <strong>Connection</strong> 对象的 <strong>Open</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="29fe9-126">Specifies whether the <strong>Open</strong> method of a <strong>Connection</strong> object should return after (synchronously) or before (asynchronously) the connection is established.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-127"><a href="connectpromptenum.md">ConnectPromptEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-127"><a href="connectpromptenum.md">ConnectPromptEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-128">指定在打开与 ODBC 数据源的连接时，是否应当显示对话框，提示输入缺少的参数。</span><span class="sxs-lookup"><span data-stu-id="29fe9-128">Specifies whether a dialog box should be displayed to prompt for missing parameters when opening a connection to an ODBC data source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-129"><a href="copyrecordoptionsenum.md">CopyRecordOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-129"><a href="copyrecordoptionsenum.md">CopyRecordOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-130">指定 <strong>CopyRecord</strong> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="29fe9-130">Specifies the behavior of the <strong>CopyRecord</strong> method.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-131"><a href="cursorlocationenum.md">CursorLocationEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-131"><a href="cursorlocationenum.md">CursorLocationEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-132">指定游标引擎的位置。</span><span class="sxs-lookup"><span data-stu-id="29fe9-132">Specifies the location of the cursor engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-133"><a href="cursoroptionenum.md">CursorOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-133"><a href="cursoroptionenum.md">CursorOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-134">指定应针对哪项功能来测试 <strong>Supports</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="29fe9-134">Specifies what functionality the <strong>Supports</strong> method should test for.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-135"><a href="cursortypeenum.md">CursorTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-135"><a href="cursortypeenum.md">CursorTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-136">指定在 <strong>Recordset</strong> 对象中使用的游标的类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-136">Specifies the type of cursor used in a <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-137"><a href="datatypeenum.md">DataTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-137"><a href="datatypeenum.md">DataTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-138">用于指定 <strong>Field</strong>、<strong>Parameter</strong> 或 <strong>Property</strong> 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-138">Specifies the data type of a <strong>Field</strong>, <strong>Parameter</strong>, or <strong>Property</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-139"><a href="editmodeenum.md">EditModeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-139"><a href="editmodeenum.md">EditModeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-140">指定记录的编辑状态。</span><span class="sxs-lookup"><span data-stu-id="29fe9-140">Specifies the editing status of a record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-141"><a href="errorvalueenum.md">ErrorValueEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-141"><a href="errorvalueenum.md">ErrorValueEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-142">指定 ADO 运行时错误的类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-142">Specifies the type of ADO run-time error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-143"><a href="eventreasonenum.md">EventReasonEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-143"><a href="eventreasonenum.md">EventReasonEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-144">指定导致事件发生的原因。</span><span class="sxs-lookup"><span data-stu-id="29fe9-144">Specifies the reason that caused an event to occur.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-145"><a href="eventstatusenum.md">EventStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-145"><a href="eventstatusenum.md">EventStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-146">指定事件执行的当前状态。</span><span class="sxs-lookup"><span data-stu-id="29fe9-146">Specifies the current status of the execution of an event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-147"><a href="executeoptionenum.md">ExecuteOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-147"><a href="executeoptionenum.md">ExecuteOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-148">指定提供程序应当如何执行命令。</span><span class="sxs-lookup"><span data-stu-id="29fe9-148">Specifies how a provider should execute a command.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-149"><a href="fieldenum.md">FieldEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-149"><a href="fieldenum.md">FieldEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-150">指定在 <strong>Record</strong> 对象的 <strong>Fields</strong> 集合中引用的特殊字段。</span><span class="sxs-lookup"><span data-stu-id="29fe9-150">Specifies the special fields referenced in a <strong>Record</strong> object's <strong>Fields</strong> collection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-151"><a href="fieldattributeenum.md">FieldAttributeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-151"><a href="fieldattributeenum.md">FieldAttributeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-152">指定 <strong>Field</strong> 对象的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="29fe9-152">Specifies one or more attributes of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-153"><a href="fieldstatusenum.md">FieldStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-153"><a href="fieldstatusenum.md">FieldStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-154">指定 <strong>Field</strong> 对象的状态。</span><span class="sxs-lookup"><span data-stu-id="29fe9-154">Specifies the status of a <strong>Field</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-155"><a href="filtergroupenum.md">FilterGroupEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-155"><a href="filtergroupenum.md">FilterGroupEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-156">指定要从 <strong>Recordset</strong> 中筛选的记录组。</span><span class="sxs-lookup"><span data-stu-id="29fe9-156">Specifies the group of records to be filtered from a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-157"><a href="getrowsoptionenum.md">GetRowsOptionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-157"><a href="getrowsoptionenum.md">GetRowsOptionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-158">指定要从 <strong>Recordset</strong> 中检索多少记录。</span><span class="sxs-lookup"><span data-stu-id="29fe9-158">Specifies how many records to retrieve from a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-159"><a href="isolationlevelenum.md">IsolationLevelEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-159"><a href="isolationlevelenum.md">IsolationLevelEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-160">指定 <strong>Connection</strong> 对象的事务隔离级别。</span><span class="sxs-lookup"><span data-stu-id="29fe9-160">Specifies the level of transaction isolation for a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-161"><a href="lineseparatorsenum.md">LineSeparatorsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-161"><a href="lineseparatorsenum.md">LineSeparatorsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-162">指定在文本 <strong>Stream</strong> 对象中用作行分隔符的字符。</span><span class="sxs-lookup"><span data-stu-id="29fe9-162">Specifies the character used as a line separator in text <strong>Stream</strong> objects.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-163"><a href="locktypeenum.md">LockTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-163"><a href="locktypeenum.md">LockTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-164">指定在编辑过程中对记录设置的锁定类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-164">Specifies the type of lock placed on records during editing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-165"><a href="marshaloptionsenum.md">MarshalOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-165"><a href="marshaloptionsenum.md">MarshalOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-166">指定哪些记录应当返回到服务器。</span><span class="sxs-lookup"><span data-stu-id="29fe9-166">Specifies which records should be returned to the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-167"><a href="moverecordoptionsenum.md">MoveRecordOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-167"><a href="moverecordoptionsenum.md">MoveRecordOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-168">指定 <strong>Record</strong> 对象的 <strong>MoveRecord</strong> 方法的行为。</span><span class="sxs-lookup"><span data-stu-id="29fe9-168">Specifies the behavior of the <strong>Record</strong> object <strong>MoveRecord</strong> method.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-169"><a href="objectstateenum.md">ObjectStateEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-169"><a href="objectstateenum.md">ObjectStateEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-170">指定对象是否处于以下状态：打开还是关闭、正在连接到数据源、正在执行命令、或正在获取数据。</span><span class="sxs-lookup"><span data-stu-id="29fe9-170">Specifies whether an object is open or closed, connecting to a data source, executing a command, or fetching data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-171"><a href="parameterattributesenum.md">ParameterAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-171"><a href="parameterattributesenum.md">ParameterAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-172">指定 <strong>Parameter</strong> 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="29fe9-172">Specifies the attributes of a <strong>Parameter</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-173"><a href="parameterdirectionenum.md">ParameterDirectionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-173"><a href="parameterdirectionenum.md">ParameterDirectionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-174">指定 <strong>Parameter</strong> 是否表示输入参数和/或输出参数，以及参数是否是存储过程的返回值。</span><span class="sxs-lookup"><span data-stu-id="29fe9-174">Specifies whether the <strong>Parameter</strong> represents an input parameter, an output parameter, or both, or if the parameter is the return value from a stored procedure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-175"><a href="persistformatenum.md">PersistFormatEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-175"><a href="persistformatenum.md">PersistFormatEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-176">指定保存 <strong>Recordset</strong> 时所用的格式。</span><span class="sxs-lookup"><span data-stu-id="29fe9-176">Specifies the format in which to save a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-177"><a href="positionenum.md">PositionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-177"><a href="positionenum.md">PositionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-178">指定在 <strong>Recordset</strong> 中记录指针的当前位置。</span><span class="sxs-lookup"><span data-stu-id="29fe9-178">Specifies the current position of the record pointer within a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-179"><a href="propertyattributesenum.md">PropertyAttributesEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-179"><a href="propertyattributesenum.md">PropertyAttributesEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-180">指定 <strong>Property</strong> 对象的属性。</span><span class="sxs-lookup"><span data-stu-id="29fe9-180">Specifies the attributes of a <strong>Property</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-181"><a href="recordcreateoptionsenum.md">RecordCreateOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-181"><a href="recordcreateoptionsenum.md">RecordCreateOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-182">指定对于 <strong>Record</strong> 对象的 <strong>Open</strong> 方法，是应当打开现有 <strong>Record</strong>，还是应当创建新的 <strong>Record</strong>。</span><span class="sxs-lookup"><span data-stu-id="29fe9-182">Specifies for the <strong>Record</strong> object <strong>Open</strong> method whether an existing <strong>Record</strong> should be opened, or a new <strong>Record</strong> should be created.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-183"><a href="recordopenoptionsenum.md">RecordOpenOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-183"><a href="recordopenoptionsenum.md">RecordOpenOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-p102">指定用于打开 <strong>Record</strong> 的选项。可以使用 OR 运算符将这些值组合在一起。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p102">Specifies options for opening a <strong>Record</strong>. These values may be combined by using an OR operator.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-186"><a href="recordstatusenum.md">RecordStatusEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-186"><a href="recordstatusenum.md">RecordStatusEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-187">指定记录的批更新和其他批量操作的状态。</span><span class="sxs-lookup"><span data-stu-id="29fe9-187">Specifies the status of a record with regard to batch updates and other bulk operations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-188"><a href="recordtypeenum.md">RecordTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-188"><a href="recordtypeenum.md">RecordTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-189">指定 <strong>Record</strong> 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-189">Specifies the type of <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-190"><a href="resyncenum.md">ResyncEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-190"><a href="resyncenum.md">ResyncEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-191">指定是否通过调用 <strong>Resync</strong> 来覆盖基础值。</span><span class="sxs-lookup"><span data-stu-id="29fe9-191">Specifies whether underlying values are overwritten by a call to <strong>Resync</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-192"><a href="saveoptionsenum.md">SaveOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-192"><a href="saveoptionsenum.md">SaveOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-p103">指定当从 <strong>Stream</strong> 对象进行保存时，应创建文件还是覆盖文件。可以使用 AND 运算符来组合使用这些值。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p103">Specifies whether a file should be created or overwritten when saving from a <strong>Stream</strong> object. The values can be combined with an AND operator.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-195"><a href="schemaenum.md">SchemaEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-195"><a href="schemaenum.md">SchemaEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-p104">指定 <strong>OpenSchema</strong> 方法所检索的架构 <strong>Recordset</strong> 的类型。指定在 <strong>Recordset</strong> 内进行记录搜索的方向。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p104">Specifies the type of schema <strong>Recordset</strong> that the <strong>OpenSchema</strong> method retrieves. Specifies the direction of a record search within a <strong>Recordset</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-198"><a href="searchdirectionenum.md">SearchDirectionEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-198"><a href="searchdirectionenum.md">SearchDirectionEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-199">指定在 <strong>Recordset</strong> 中进行记录搜索的方向。指定要执行的 <strong>Seek</strong> 的类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-199">Specifies the direction of a record search within a <strong>Recordset</strong>.Specifies the type of <strong>Seek</strong> to execute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-200"><a href="seekenum.md">SeekEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-200"><a href="seekenum.md">SeekEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-p105">指定要执行的 <strong>Seek</strong> 的类型。指定用于打开 <strong>Stream</strong> 对象的选项。该值可以与 AND 运算符组合。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p105">Specifies the type of <strong>Seek</strong> to execute.Specifies options for opening a <strong>Stream</strong> object. The values can be combined with an AND operator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-203"><a href="streamopenoptionsenum.md">StreamOpenOptionsEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-203"><a href="streamopenoptionsenum.md">StreamOpenOptionsEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-p106">指定用于打开 <strong>Stream</strong> 对象的选项。这些值可以与 AND 运算符组合。指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。</span><span class="sxs-lookup"><span data-stu-id="29fe9-p106">Specifies options for opening a <strong>Stream</strong> object. The values can be combined with an AND operator.Specifies whether the whole stream or the next line should be read from a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-206"><a href="streamreadenum.md">StreamReadEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-206"><a href="streamreadenum.md">StreamReadEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-207">指定应当从 <strong>Stream</strong> 对象读取整个流还是下一行。指定存储在 <strong>Stream</strong> 对象中的数据的类型。</span><span class="sxs-lookup"><span data-stu-id="29fe9-207">Specifies whether the whole stream or the next line should be read from a <strong>Stream</strong> object.Specifies the type of data stored in a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-208"><a href="streamtypeenum.md">StreamTypeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-208"><a href="streamtypeenum.md">StreamTypeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-209">指定存储在 <strong>Stream</strong> 对象中的数据的类型。指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="29fe9-209">Specifies the type of data stored in a <strong>Stream</strong> object.Specifies whether a line separator is appended to the string written to a <strong>Stream</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-210"><a href="streamwriteenum.md">StreamWriteEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-210"><a href="streamwriteenum.md">StreamWriteEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-211">指定是否将行分隔符追加到写入 <strong>Stream</strong> 对象的字符串。指定检索 <strong>Recordset</strong> 时的格式为字符串。</span><span class="sxs-lookup"><span data-stu-id="29fe9-211">Specifies whether a line separator is appended to the string written to a <strong>Stream</strong> object.Specifies the format when retrieving a <strong>Recordset</strong> as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29fe9-212"><a href="stringformatenum.md">StringFormatEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-212"><a href="stringformatenum.md">StringFormatEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-213">指定检索 <strong>Recordset</strong> 时的格式为字符串。指定 <strong>Connection</strong> 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="29fe9-213">Specifies the format when retrieving a <strong>Recordset</strong> as a string.Specifies the transaction attributes of a <strong>Connection</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29fe9-214"><a href="xactattributeenum.md">XactAttributeEnum</a></span><span class="sxs-lookup"><span data-stu-id="29fe9-214"><a href="xactattributeenum.md">XactAttributeEnum</a></span></span></p></td>
<td><p><span data-ttu-id="29fe9-215">指定 <strong>Connection</strong> 对象的事务属性。</span><span class="sxs-lookup"><span data-stu-id="29fe9-215">Specifies the transaction attributes of a <strong>Connection</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>

