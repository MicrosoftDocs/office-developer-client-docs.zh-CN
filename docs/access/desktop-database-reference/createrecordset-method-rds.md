---
title: CreateRecordset 方法 (RDS)
TOCTitle: CreateRecordset method (RDS)
ms:assetid: 19524509-31da-9af1-4062-cd3c59b51278
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248940(v=office.15)
ms:contentKeyID: 48543497
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0b4d68ac2dfca344cb98885846f2cd09fafd0ea0
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950235"
---
# <a name="createrecordset-method-rds"></a><span data-ttu-id="71b69-102">CreateRecordset 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="71b69-102">CreateRecordset method (RDS)</span></span>

<span data-ttu-id="71b69-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="71b69-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="71b69-104">用于创建断开连接的空 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="71b69-104">Creates an empty, disconnected [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="71b69-105">语法</span><span class="sxs-lookup"><span data-stu-id="71b69-105">Syntax</span></span>

<span data-ttu-id="71b69-106">*对象*。CreateRecordset (*ColumnInfos*)</span><span class="sxs-lookup"><span data-stu-id="71b69-106">*object*.CreateRecordset(*ColumnInfos*)</span></span>

## <a name="parameters"></a><span data-ttu-id="71b69-107">参数</span><span class="sxs-lookup"><span data-stu-id="71b69-107">Parameters</span></span>

|<span data-ttu-id="71b69-108">参数</span><span class="sxs-lookup"><span data-stu-id="71b69-108">Parameter</span></span>|<span data-ttu-id="71b69-109">说明</span><span class="sxs-lookup"><span data-stu-id="71b69-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="71b69-110">*Object*</span><span class="sxs-lookup"><span data-stu-id="71b69-110">*Object*</span></span> |<span data-ttu-id="71b69-111">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="71b69-111">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) or [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="71b69-112">*ColumnsInfos*</span><span class="sxs-lookup"><span data-stu-id="71b69-112">*ColumnsInfos*</span></span> |<span data-ttu-id="71b69-113">属性的 **变量型** 数组，用于定义所创建的 **Recordset** 中的各个列。</span><span class="sxs-lookup"><span data-stu-id="71b69-113">A **Variant** array of attributes that defines each column in the **Recordset** created.</span></span> <span data-ttu-id="71b69-114">每个列定义都包含一个数组，其中包含四个必需属性和一个可选属性。</span><span class="sxs-lookup"><span data-stu-id="71b69-114">Each column definition contains an array of four required attributes and one optional attribute.</span></span> <span data-ttu-id="71b69-115">列数组集合随后组合到定义 **Recordset** 的数组中。</span><span class="sxs-lookup"><span data-stu-id="71b69-115">The set of column arrays is then grouped into an array, which defines the **Recordset**.</span></span> <span data-ttu-id="71b69-116">属性的列表，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="71b69-116">For a list of attributes, see the following table.</span></span>|

### <a name="variant-array-attributes"></a><span data-ttu-id="71b69-117">Variant 数组属性</span><span class="sxs-lookup"><span data-stu-id="71b69-117">Variant array attributes</span></span>

|<span data-ttu-id="71b69-118">属性</span><span class="sxs-lookup"><span data-stu-id="71b69-118">Attribute</span></span>|<span data-ttu-id="71b69-119">说明</span><span class="sxs-lookup"><span data-stu-id="71b69-119">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="71b69-120">Name</span><span class="sxs-lookup"><span data-stu-id="71b69-120">Name</span></span> |<span data-ttu-id="71b69-121">列标题的名称。</span><span class="sxs-lookup"><span data-stu-id="71b69-121">Name of the column header.</span></span>|
|<span data-ttu-id="71b69-122">Type</span><span class="sxs-lookup"><span data-stu-id="71b69-122">Type</span></span> |<span data-ttu-id="71b69-123">代表数据类型的整数。</span><span class="sxs-lookup"><span data-stu-id="71b69-123">Integer of the data type.</span></span>|
|<span data-ttu-id="71b69-124">Size</span><span class="sxs-lookup"><span data-stu-id="71b69-124">Size</span></span> |<span data-ttu-id="71b69-125">代表宽度的整数（以字符为单位），与数据类型无关。</span><span class="sxs-lookup"><span data-stu-id="71b69-125">Integer of the width in characters, regardless of data type.</span></span>|
|<span data-ttu-id="71b69-126">Nullability</span><span class="sxs-lookup"><span data-stu-id="71b69-126">Nullability</span></span> |<span data-ttu-id="71b69-127">布尔值。</span><span class="sxs-lookup"><span data-stu-id="71b69-127">Boolean value.</span></span>|
|<span data-ttu-id="71b69-128">Scale （可选）</span><span class="sxs-lookup"><span data-stu-id="71b69-128">Scale (optional)</span></span> |<span data-ttu-id="71b69-p102">此可选属性定义数值字段的位数。如果未指定此值，数值将被截取为三位。精度不会受影响，但小数点之后的位数将截取为三位。</span><span class="sxs-lookup"><span data-stu-id="71b69-p102">This optional attribute defines the scale for numeric fields. If this value is not specified, numeric values will be truncated to a scale of three. Precision is not affected, but the number of digits following the decimal point will be truncated to three.</span></span>|

## <a name="remarks"></a><span data-ttu-id="71b69-132">说明</span><span class="sxs-lookup"><span data-stu-id="71b69-132">Remarks</span></span>

<span data-ttu-id="71b69-133">服务器端业务对象可以使用来自非 OLE DB 数据提供程序（例如，包含股票报价的操作系统文件）的数据来填充生成的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="71b69-133">The server-side business object can populate the resulting **Recordset** with data from a non-OLE DB data provider, such as an operating system file containing stock quotes.</span></span>

<span data-ttu-id="71b69-p103">下表列出了 [CreateRecordset](datatypeenum.md) 方法支持的 **DataTypeEnum** 值。所列的数字是用于定义字段的引用编号。</span><span class="sxs-lookup"><span data-stu-id="71b69-p103">The following table lists the [DataTypeEnum](datatypeenum.md) values supported by the **CreateRecordset** method. The number listed is the reference number used to define fields.</span></span>

<span data-ttu-id="71b69-p104">每种数据类型可能是固定长度，也可能是可变长度。固定长度的类型应使用大小 –1 来定义，由于该大小是预先确定的，因此仍然需要大小定义。可变长度的数据类型允许大小为 1 到 32767。</span><span class="sxs-lookup"><span data-stu-id="71b69-p104">Each of the data types is either fixed length or variable length. Fixed-length types should be defined with a size of –1, because the size is predetermined and a size definition is still required. Variable-length data types allow a size from 1 to 32767.</span></span>

<span data-ttu-id="71b69-p105">对于某些可变数据类型，类型可能会被强制为"替换"列中注明的类型。在创建并填充了 **Recordset** 之后，您才会看到替换内容。然后，可以根据需要检查实际的数据类型。</span><span class="sxs-lookup"><span data-stu-id="71b69-p105">For some of the variable data types, the type may be coerced to the type noted in the Substitution column. You won't see the substitutions until after the **Recordset** is created and filled. Then you can check for the actual data type, if necessary.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="71b69-142">长度</span><span class="sxs-lookup"><span data-stu-id="71b69-142">Length</span></span></p></th>
<th><p><span data-ttu-id="71b69-143">常量</span><span class="sxs-lookup"><span data-stu-id="71b69-143">Constant</span></span></p></th>
<th><p><span data-ttu-id="71b69-144">编号</span><span class="sxs-lookup"><span data-stu-id="71b69-144">Number</span></span></p></th>
<th><p><span data-ttu-id="71b69-145">替换</span><span class="sxs-lookup"><span data-stu-id="71b69-145">Substitution</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71b69-146">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-146">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-147"><strong>adTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-147"><strong>adTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-148">16</span><span class="sxs-lookup"><span data-stu-id="71b69-148">16</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-149">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-149">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-150"><strong>adSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-150"><strong>adSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-151">2</span><span class="sxs-lookup"><span data-stu-id="71b69-151">2</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-152">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-152">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-153"><strong>adInteger</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-153"><strong>adInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-154">3</span><span class="sxs-lookup"><span data-stu-id="71b69-154">3</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-155">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-155">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-156"><strong>adBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-156"><strong>adBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-157">20</span><span class="sxs-lookup"><span data-stu-id="71b69-157">20</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-158">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-158">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-159"><strong>adUnsignedTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-159"><strong>adUnsignedTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-160">17</span><span class="sxs-lookup"><span data-stu-id="71b69-160">17</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-161">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-161">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-162"><strong>adUnsignedSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-162"><strong>adUnsignedSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-163">18</span><span class="sxs-lookup"><span data-stu-id="71b69-163">18</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-164">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-164">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-165"><strong>adUnsignedInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-165"><strong>adUnsignedInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-166">19</span><span class="sxs-lookup"><span data-stu-id="71b69-166">19</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-167">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-167">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-168"><strong>adUnsignedBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-168"><strong>adUnsignedBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-169">21</span><span class="sxs-lookup"><span data-stu-id="71b69-169">21</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-170">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-170">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-171"><strong>adSingle</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-171"><strong>adSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-172">4</span><span class="sxs-lookup"><span data-stu-id="71b69-172">4</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-173">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-173">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-174"><strong>adDouble</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-174"><strong>adDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-175">5</span><span class="sxs-lookup"><span data-stu-id="71b69-175">5</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-176">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-176">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-177"><strong>adCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-177"><strong>adCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-178">6</span><span class="sxs-lookup"><span data-stu-id="71b69-178">6</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-179">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-179">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-180"><strong>为 adDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-180"><strong>adDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-181">14</span><span class="sxs-lookup"><span data-stu-id="71b69-181">14</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-182">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-182">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-183"><strong>adNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-183"><strong>adNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-184">131</span><span class="sxs-lookup"><span data-stu-id="71b69-184">131</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-185">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-185">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-186"><strong>adBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-186"><strong>adBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-187">11</span><span class="sxs-lookup"><span data-stu-id="71b69-187">11</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-188">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-188">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-189"><strong>adError</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-189"><strong>adError</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-190">10</span><span class="sxs-lookup"><span data-stu-id="71b69-190">10</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-191">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-191">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-192"><strong>adGuid</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-192"><strong>adGuid</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-193">72</span><span class="sxs-lookup"><span data-stu-id="71b69-193">72</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-194">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-194">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-195"><strong>adDate</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-195"><strong>adDate</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-196">7</span><span class="sxs-lookup"><span data-stu-id="71b69-196">7</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-197">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-197">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-198"><strong>adDBDate</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-198"><strong>adDBDate</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-199">133</span><span class="sxs-lookup"><span data-stu-id="71b69-199">133</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-200">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-200">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-201"><strong>adDBTime</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-201"><strong>adDBTime</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-202">134</span><span class="sxs-lookup"><span data-stu-id="71b69-202">134</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-203">固定</span><span class="sxs-lookup"><span data-stu-id="71b69-203">Fixed</span></span></p></td>
<td><p><span data-ttu-id="71b69-204"><strong>adDBTimestamp</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-204"><strong>adDBTimestamp</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-205">135</span><span class="sxs-lookup"><span data-stu-id="71b69-205">135</span></span></p></td>
<td><p><span data-ttu-id="71b69-206">7</span><span class="sxs-lookup"><span data-stu-id="71b69-206">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-207">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-207">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-208"><strong>adBSTR</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-208"><strong>adBSTR</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-209">8</span><span class="sxs-lookup"><span data-stu-id="71b69-209">8</span></span></p></td>
<td><p><span data-ttu-id="71b69-210">130</span><span class="sxs-lookup"><span data-stu-id="71b69-210">130</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-211">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-211">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-212"><strong>每</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-212"><strong>adChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-213">129</span><span class="sxs-lookup"><span data-stu-id="71b69-213">129</span></span></p></td>
<td><p><span data-ttu-id="71b69-214">200</span><span class="sxs-lookup"><span data-stu-id="71b69-214">200</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-215">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-215">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-216"><strong>以便您可以排除</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-216"><strong>adVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-217">200</span><span class="sxs-lookup"><span data-stu-id="71b69-217">200</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-218">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-218">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-219"><strong>adLongVarChar</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-219"><strong>adLongVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-220">201</span><span class="sxs-lookup"><span data-stu-id="71b69-220">201</span></span></p></td>
<td><p><span data-ttu-id="71b69-221">200</span><span class="sxs-lookup"><span data-stu-id="71b69-221">200</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-222">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-222">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-223"><strong>adWChar</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-223"><strong>adWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-224">130</span><span class="sxs-lookup"><span data-stu-id="71b69-224">130</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-225">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-225">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-226"><strong>adVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-226"><strong>adVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-227">202</span><span class="sxs-lookup"><span data-stu-id="71b69-227">202</span></span></p></td>
<td><p><span data-ttu-id="71b69-228">130</span><span class="sxs-lookup"><span data-stu-id="71b69-228">130</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-229">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-229">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-230"><strong>adLongVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-230"><strong>adLongVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-231">203</span><span class="sxs-lookup"><span data-stu-id="71b69-231">203</span></span></p></td>
<td><p><span data-ttu-id="71b69-232">130</span><span class="sxs-lookup"><span data-stu-id="71b69-232">130</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-233">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-233">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-234"><strong>adBinary</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-234"><strong>adBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-235">128</span><span class="sxs-lookup"><span data-stu-id="71b69-235">128</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b69-236">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-236">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-237"><strong>感</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-237"><strong>adVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-238">204</span><span class="sxs-lookup"><span data-stu-id="71b69-238">204</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b69-239">可变</span><span class="sxs-lookup"><span data-stu-id="71b69-239">Variable</span></span></p></td>
<td><p><span data-ttu-id="71b69-240"><strong>adLongVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="71b69-240"><strong>adLongVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="71b69-241">205</span><span class="sxs-lookup"><span data-stu-id="71b69-241">205</span></span></p></td>
<td><p><span data-ttu-id="71b69-242">204</span><span class="sxs-lookup"><span data-stu-id="71b69-242">204</span></span></p></td>
</tr>
</tbody>
</table>

