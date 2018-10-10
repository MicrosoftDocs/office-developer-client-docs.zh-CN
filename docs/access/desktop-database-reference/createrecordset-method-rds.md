---
title: CreateRecordset 方法 (RDS)
TOCTitle: CreateRecordset Method (RDS)
ms:assetid: 19524509-31da-9af1-4062-cd3c59b51278
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248940(v=office.15)
ms:contentKeyID: 48543497
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 696daaeb060387d5f3ca454ef665517a8ff7be74
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465775"
---
# <a name="createrecordset-method-rds"></a><span data-ttu-id="5fc8f-102">CreateRecordset 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="5fc8f-102">CreateRecordset Method (RDS)</span></span>


<span data-ttu-id="5fc8f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5fc8f-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="5fc8f-104">用于创建断开连接的空 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-104">Creates an empty, disconnected [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="5fc8f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5fc8f-105">Syntax</span></span>

<span data-ttu-id="5fc8f-106">*对象*。CreateRecordset (*ColumnInfos*)</span><span class="sxs-lookup"><span data-stu-id="5fc8f-106">*object*.CreateRecordset(*ColumnInfos*)</span></span>

## <a name="parameters"></a><span data-ttu-id="5fc8f-107">参数</span><span class="sxs-lookup"><span data-stu-id="5fc8f-107">Parameters</span></span>

  - <span data-ttu-id="5fc8f-108">*Object*</span><span class="sxs-lookup"><span data-stu-id="5fc8f-108">*Object*</span></span>

  - <span data-ttu-id="5fc8f-109">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-109">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) or [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="5fc8f-110">*ColumnsInfos*</span><span class="sxs-lookup"><span data-stu-id="5fc8f-110">*ColumnsInfos*</span></span>

  - <span data-ttu-id="5fc8f-p101">属性的 **变量型** 数组，用于定义所创建的 **Recordset** 中的各个列。每个列定义都包含一个数组，其中包含四个必需属性和一个可选属性。 列数组集合随后组合到定义 **Recordset** 的数组中。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p101">A **Variant** array of attributes that defines each column in the **Recordset** created. Each column definition contains an array of four required attributes and one optional attribute. The set of column arrays is then grouped into an array, which defines the **Recordset**.</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><span data-ttu-id="5fc8f-114">属性</span><span class="sxs-lookup"><span data-stu-id="5fc8f-114">Attribute</span></span></p></th>
    <th><p><span data-ttu-id="5fc8f-115">说明</span><span class="sxs-lookup"><span data-stu-id="5fc8f-115">Description</span></span></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5fc8f-116">Name</span><span class="sxs-lookup"><span data-stu-id="5fc8f-116">Name</span></span></p></td>
    <td><p><span data-ttu-id="5fc8f-117">列标题的名称。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-117">Name of the column header.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5fc8f-118">Type</span><span class="sxs-lookup"><span data-stu-id="5fc8f-118">Type</span></span></p></td>
    <td><p><span data-ttu-id="5fc8f-119">代表数据类型的整数。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-119">Integer of the data type.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5fc8f-120">Size</span><span class="sxs-lookup"><span data-stu-id="5fc8f-120">Size</span></span></p></td>
    <td><p><span data-ttu-id="5fc8f-121">代表宽度的整数（以字符为单位），与数据类型无关。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-121">Integer of the width in characters, regardless of data type.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5fc8f-122">Nullability</span><span class="sxs-lookup"><span data-stu-id="5fc8f-122">Nullability</span></span></p></td>
    <td><p><span data-ttu-id="5fc8f-123">布尔值。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-123">Boolean value.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5fc8f-124">Scale</span><span class="sxs-lookup"><span data-stu-id="5fc8f-124">Scale</span></span><br />
<span data-ttu-id="5fc8f-125">（可选）</span><span class="sxs-lookup"><span data-stu-id="5fc8f-125">(Optional)</span></span></p></td>
    <td><p><span data-ttu-id="5fc8f-p102">此可选属性定义数值字段的位数。如果未指定此值，数值将被截取为三位。精度不会受影响，但小数点之后的位数将截取为三位。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p102">This optional attribute defines the scale for numeric fields. If this value is not specified, numeric values will be truncated to a scale of three. Precision is not affected, but the number of digits following the decimal point will be truncated to three.</span></span></p></td>
    </tr>
    </tbody>
    </table>


## <a name="remarks"></a><span data-ttu-id="5fc8f-129">说明</span><span class="sxs-lookup"><span data-stu-id="5fc8f-129">Remarks</span></span>

<span data-ttu-id="5fc8f-130">服务器端业务对象可以使用来自非 OLE DB 数据提供程序（例如，包含股票报价的操作系统文件）的数据来填充生成的 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-130">The server-side business object can populate the resulting **Recordset** with data from a non-OLE DB data provider, such as an operating system file containing stock quotes.</span></span>

<span data-ttu-id="5fc8f-p103">下表列出了 [CreateRecordset](datatypeenum.md) 方法支持的 **DataTypeEnum** 值。所列的数字是用于定义字段的引用编号。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p103">The following table lists the [DataTypeEnum](datatypeenum.md) values supported by the **CreateRecordset** method. The number listed is the reference number used to define fields.</span></span>

<span data-ttu-id="5fc8f-p104">每种数据类型可能是固定长度，也可能是可变长度。固定长度的类型应使用大小 –1 来定义，由于该大小是预先确定的，因此仍然需要大小定义。可变长度的数据类型允许大小为 1 到 32767。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p104">Each of the data types is either fixed length or variable length. Fixed-length types should be defined with a size of –1, because the size is predetermined and a size definition is still required. Variable-length data types allow a size from 1 to 32767.</span></span>

<span data-ttu-id="5fc8f-p105">对于某些可变数据类型，类型可能会被强制为"替换"列中注明的类型。在创建并填充了 **Recordset** 之后，您才会看到替换内容。然后，可以根据需要检查实际的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5fc8f-p105">For some of the variable data types, the type may be coerced to the type noted in the Substitution column. You won't see the substitutions until after the **Recordset** is created and filled. Then you can check for the actual data type, if necessary.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5fc8f-139">长度</span><span class="sxs-lookup"><span data-stu-id="5fc8f-139">Length</span></span></p></th>
<th><p><span data-ttu-id="5fc8f-140">常量</span><span class="sxs-lookup"><span data-stu-id="5fc8f-140">Constant</span></span></p></th>
<th><p><span data-ttu-id="5fc8f-141">编号</span><span class="sxs-lookup"><span data-stu-id="5fc8f-141">Number</span></span></p></th>
<th><p><span data-ttu-id="5fc8f-142">替换</span><span class="sxs-lookup"><span data-stu-id="5fc8f-142">Substitution</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-143">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-143">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-144"><strong>adTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-144"><strong>adTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-145">16</span><span class="sxs-lookup"><span data-stu-id="5fc8f-145">16</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-146">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-146">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-147"><strong>adSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-147"><strong>adSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-148">2</span><span class="sxs-lookup"><span data-stu-id="5fc8f-148">2</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-149">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-149">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-150"><strong>adInteger</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-150"><strong>adInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-151">3</span><span class="sxs-lookup"><span data-stu-id="5fc8f-151">3</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-152">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-152">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-153"><strong>adBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-153"><strong>adBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-154">20</span><span class="sxs-lookup"><span data-stu-id="5fc8f-154">20</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-155">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-155">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-156"><strong>adUnsignedTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-156"><strong>adUnsignedTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-157">17</span><span class="sxs-lookup"><span data-stu-id="5fc8f-157">17</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-158">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-158">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-159"><strong>adUnsignedSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-159"><strong>adUnsignedSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-160">18</span><span class="sxs-lookup"><span data-stu-id="5fc8f-160">18</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-161">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-161">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-162"><strong>adUnsignedInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-162"><strong>adUnsignedInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-163">19</span><span class="sxs-lookup"><span data-stu-id="5fc8f-163">19</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-164">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-164">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-165"><strong>adUnsignedBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-165"><strong>adUnsignedBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-166">21</span><span class="sxs-lookup"><span data-stu-id="5fc8f-166">21</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-167">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-167">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-168"><strong>adSingle</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-168"><strong>adSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-169">4</span><span class="sxs-lookup"><span data-stu-id="5fc8f-169">4</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-170">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-170">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-171"><strong>adDouble</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-171"><strong>adDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-172">5</span><span class="sxs-lookup"><span data-stu-id="5fc8f-172">5</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-173">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-173">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-174"><strong>adCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-174"><strong>adCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-175">6</span><span class="sxs-lookup"><span data-stu-id="5fc8f-175">6</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-176">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-176">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-177"><strong>为 adDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-177"><strong>adDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-178">14</span><span class="sxs-lookup"><span data-stu-id="5fc8f-178">14</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-179">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-179">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-180"><strong>adNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-180"><strong>adNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-181">131</span><span class="sxs-lookup"><span data-stu-id="5fc8f-181">131</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-182">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-182">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-183"><strong>adBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-183"><strong>adBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-184">11</span><span class="sxs-lookup"><span data-stu-id="5fc8f-184">11</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-185">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-185">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-186"><strong>adError</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-186"><strong>adError</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-187">10</span><span class="sxs-lookup"><span data-stu-id="5fc8f-187">10</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-188">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-188">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-189"><strong>adGuid</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-189"><strong>adGuid</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-190">72</span><span class="sxs-lookup"><span data-stu-id="5fc8f-190">72</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-191">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-191">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-192"><strong>adDate</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-192"><strong>adDate</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-193">7</span><span class="sxs-lookup"><span data-stu-id="5fc8f-193">7</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-194">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-194">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-195"><strong>adDBDate</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-195"><strong>adDBDate</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-196">133</span><span class="sxs-lookup"><span data-stu-id="5fc8f-196">133</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-197">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-197">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-198"><strong>adDBTime</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-198"><strong>adDBTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-199">134</span><span class="sxs-lookup"><span data-stu-id="5fc8f-199">134</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-200">固定</span><span class="sxs-lookup"><span data-stu-id="5fc8f-200">Fixed</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-201"><strong>adDBTimestamp</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-201"><strong>adDBTimestamp</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-202">135</span><span class="sxs-lookup"><span data-stu-id="5fc8f-202">135</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-203">7</span><span class="sxs-lookup"><span data-stu-id="5fc8f-203">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-204">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-204">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-205"><strong>adBSTR</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-205"><strong>adBSTR</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-206">8</span><span class="sxs-lookup"><span data-stu-id="5fc8f-206">8</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-207">130</span><span class="sxs-lookup"><span data-stu-id="5fc8f-207">130</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-208">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-208">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-209"><strong>每</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-209"><strong>adChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-210">129</span><span class="sxs-lookup"><span data-stu-id="5fc8f-210">129</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-211">200</span><span class="sxs-lookup"><span data-stu-id="5fc8f-211">200</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-212">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-212">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-213"><strong>以便您可以排除</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-213"><strong>adVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-214">200</span><span class="sxs-lookup"><span data-stu-id="5fc8f-214">200</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-215">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-215">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-216"><strong>adLongVarChar</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-216"><strong>adLongVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-217">201</span><span class="sxs-lookup"><span data-stu-id="5fc8f-217">201</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-218">200</span><span class="sxs-lookup"><span data-stu-id="5fc8f-218">200</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-219">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-219">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-220"><strong>adWChar</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-220"><strong>adWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-221">130</span><span class="sxs-lookup"><span data-stu-id="5fc8f-221">130</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-222">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-222">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-223"><strong>adVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-223"><strong>adVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-224">202</span><span class="sxs-lookup"><span data-stu-id="5fc8f-224">202</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-225">130</span><span class="sxs-lookup"><span data-stu-id="5fc8f-225">130</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-226">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-226">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-227"><strong>adLongVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-227"><strong>adLongVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-228">203</span><span class="sxs-lookup"><span data-stu-id="5fc8f-228">203</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-229">130</span><span class="sxs-lookup"><span data-stu-id="5fc8f-229">130</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-230">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-230">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-231"><strong>adBinary</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-231"><strong>adBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-232">128</span><span class="sxs-lookup"><span data-stu-id="5fc8f-232">128</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fc8f-233">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-233">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-234"><strong>感</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-234"><strong>adVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-235">204</span><span class="sxs-lookup"><span data-stu-id="5fc8f-235">204</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fc8f-236">可变</span><span class="sxs-lookup"><span data-stu-id="5fc8f-236">Variable</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-237"><strong>adLongVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="5fc8f-237"><strong>adLongVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="5fc8f-238">205</span><span class="sxs-lookup"><span data-stu-id="5fc8f-238">205</span></span></p></td>
<td><p><span data-ttu-id="5fc8f-239">204</span><span class="sxs-lookup"><span data-stu-id="5fc8f-239">204</span></span></p></td>
</tr>
</tbody>
</table>

