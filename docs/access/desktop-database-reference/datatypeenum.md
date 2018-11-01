---
title: DataTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: DataTypeEnum
ms:assetid: a8ab7616-552f-ed5f-ed55-95254cfb374a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249780(v=office.15)
ms:contentKeyID: 48546904
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: 7d1cbc0964c4e980c1dd5216431c5efd0c467dc4
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25878260"
---
# <a name="datatypeenum"></a><span data-ttu-id="7fc66-102">DataTypeEnum</span><span class="sxs-lookup"><span data-stu-id="7fc66-102">DataTypeEnum</span></span>

<span data-ttu-id="7fc66-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="7fc66-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7fc66-p101">用于指定 [Field](field-object-ado.md)、[Parameter](parameter-object-ado.md) 或 [Property](property-object-ado.md) 的数据类型。下表的说明列的圆括号中显示了对应的 OLE DB 类型指示器。有关 OLE DB 数据类型的详细信息，请参阅 *《OLE DB 程序员参考》* 的第 13 章和附录 A。</span><span class="sxs-lookup"><span data-stu-id="7fc66-p101">Specifies the data type of a [Field](field-object-ado.md), [Parameter](parameter-object-ado.md), or [Property](property-object-ado.md). The corresponding OLE DB type indicator is shown in parentheses in the description column of the following table. For more information about OLE DB data types, see Chapter 13 and Appendix A of the *OLE DB Programmer's Reference*.</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7fc66-107">常量</span><span class="sxs-lookup"><span data-stu-id="7fc66-107">Constant</span></span></p></th>
<th><p><span data-ttu-id="7fc66-108">值</span><span class="sxs-lookup"><span data-stu-id="7fc66-108">Value</span></span></p></th>
<th><p><span data-ttu-id="7fc66-109">说明</span><span class="sxs-lookup"><span data-stu-id="7fc66-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-110"><strong>AdArray</span><span class="sxs-lookup"><span data-stu-id="7fc66-110"><strong>AdArray</span></span><br /><span data-ttu-id="7fc66-111">
</strong>（不适用于 ADOX。）</span><span class="sxs-lookup"><span data-stu-id="7fc66-111">
</strong>(Does not apply to ADOX.)</span></span></p></td>
<td><p><span data-ttu-id="7fc66-112">0x2000</span><span class="sxs-lookup"><span data-stu-id="7fc66-112">0x2000</span></span></p></td>
<td><p><span data-ttu-id="7fc66-113">标志值，始终与另一个数据类型常量组合使用，以指示该数据类型的数组。</span><span class="sxs-lookup"><span data-stu-id="7fc66-113">A flag value, always combined with another data type constant, that indicates an array of that other data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-114"><strong>adBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-114"><strong>adBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-115">20</span><span class="sxs-lookup"><span data-stu-id="7fc66-115">20</span></span></p></td>
<td><p><span data-ttu-id="7fc66-116">指示八字节有符号整数 (DBTYPE_I8)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-116">Indicates an eight-byte signed integer (DBTYPE_I8).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-117"><strong>adBinary</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-117"><strong>adBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-118">128</span><span class="sxs-lookup"><span data-stu-id="7fc66-118">128</span></span></p></td>
<td><p><span data-ttu-id="7fc66-119">指示二进制值 (DBTYPE_BYTES)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-119">Indicates a binary value (DBTYPE_BYTES).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-120"><strong>adBoolean</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-120"><strong>adBoolean</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-121">11</span><span class="sxs-lookup"><span data-stu-id="7fc66-121">11</span></span></p></td>
<td><p><span data-ttu-id="7fc66-122">指示布尔型值 (DBTYPE_BOOL)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-122">Indicates a boolean value (DBTYPE_BOOL).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-123"><strong>adBSTR</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-123"><strong>adBSTR</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-124">8</span><span class="sxs-lookup"><span data-stu-id="7fc66-124">8</span></span></p></td>
<td><p><span data-ttu-id="7fc66-125">指示空结尾字符串 (Unicode) (DBTYPE_BSTR)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-125">Indicates a null-terminated character string (Unicode) (DBTYPE_BSTR).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-126"><strong>adChapter</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-126"><strong>adChapter</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-127">136</span><span class="sxs-lookup"><span data-stu-id="7fc66-127">136</span></span></p></td>
<td><p><span data-ttu-id="7fc66-128">指示四字节章节值（标识子行集中的行）(DBTYPE_HCHAPTER)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-128">Indicates a four-byte chapter value that identifies rows in a child rowset (DBTYPE_HCHAPTER).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-129"><strong>每</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-129"><strong>adChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-130">129</span><span class="sxs-lookup"><span data-stu-id="7fc66-130">129</span></span></p></td>
<td><p><span data-ttu-id="7fc66-131">指示字符串值 (DBTYPE_STR)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-131">Indicates a string value (DBTYPE_STR).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-132"><strong>adCurrency</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-132"><strong>adCurrency</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-133">6</span><span class="sxs-lookup"><span data-stu-id="7fc66-133">6</span></span></p></td>
<td><p><span data-ttu-id="7fc66-p102">指示货币值 (DBTYPE_CY)。货币是小数位数固定的数字（小数点右侧保留四位）。以八字节有符号整数（以 10,000 为比例）存储。</span><span class="sxs-lookup"><span data-stu-id="7fc66-p102">Indicates a currency value (DBTYPE_CY). Currency is a fixed-point number with four digits to the right of the decimal point. It is stored in an eight-byte signed integer scaled by 10,000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-137"><strong>adDate</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-137"><strong>adDate</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-138">7</span><span class="sxs-lookup"><span data-stu-id="7fc66-138">7</span></span></p></td>
<td><p><span data-ttu-id="7fc66-p103">指示日期值 (DBTYPE_DATE)。日期存储为双精度型，其整数部分是 1899 年 12 月 30 日以后的天数，小数部分是某一天内的时间。</span><span class="sxs-lookup"><span data-stu-id="7fc66-p103">Indicates a date value (DBTYPE_DATE). A date is stored as a double, the whole part of which is the number of days since December 30, 1899, and the fractional part of which is the fraction of a day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-141"><strong>adDBDate</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-141"><strong>adDBDate</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-142">133</span><span class="sxs-lookup"><span data-stu-id="7fc66-142">133</span></span></p></td>
<td><p><span data-ttu-id="7fc66-143">指示日期值（年月日）(DBTYPE_DBDATE)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-143">Indicates a date value (yyyymmdd) (DBTYPE_DBDATE).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-144"><strong>adDBTime</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-144"><strong>adDBTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-145">134</span><span class="sxs-lookup"><span data-stu-id="7fc66-145">134</span></span></p></td>
<td><p><span data-ttu-id="7fc66-146">指示时间值（小时分秒）(DBTYPE_DBTIME)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-146">Indicates a time value (hhmmss) (DBTYPE_DBTIME).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-147"><strong>adDBTimeStamp</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-147"><strong>adDBTimeStamp</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-148">135</span><span class="sxs-lookup"><span data-stu-id="7fc66-148">135</span></span></p></td>
<td><p><span data-ttu-id="7fc66-149">指示日期/时间戳（年月日小时分秒加上分数，单位：十亿分之一）(DBTYPE_DBTIMESTAMP)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-149">Indicates a date/time stamp (yyyymmddhhmmss plus a fraction in billionths) (DBTYPE_DBTIMESTAMP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-150"><strong>为 adDecimal</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-150"><strong>adDecimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-151">14</span><span class="sxs-lookup"><span data-stu-id="7fc66-151">14</span></span></p></td>
<td><p><span data-ttu-id="7fc66-152">指示具有固定精度和范围的确切数值 (DBTYPE_DECIMAL)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-152">Indicates an exact numeric value with a fixed precision and scale (DBTYPE_DECIMAL).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-153"><strong>adDouble</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-153"><strong>adDouble</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-154">5</span><span class="sxs-lookup"><span data-stu-id="7fc66-154">5</span></span></p></td>
<td><p><span data-ttu-id="7fc66-155">指示双精度浮点值 (DBTYPE_R8)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-155">Indicates a double-precision floating-point value (DBTYPE_R8).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-156"><strong>adEmpty</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-156"><strong>adEmpty</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-157">0</span><span class="sxs-lookup"><span data-stu-id="7fc66-157">0</span></span></p></td>
<td><p><span data-ttu-id="7fc66-158">不指定值 (DBTYPE_EMPTY)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-158">Specifies no value (DBTYPE_EMPTY).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-159"><strong>adError</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-159"><strong>adError</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-160">10</span><span class="sxs-lookup"><span data-stu-id="7fc66-160">10</span></span></p></td>
<td><p><span data-ttu-id="7fc66-161">指示 32 位错误代码 (DBTYPE_ERROR)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-161">Indicates a 32-bit error code (DBTYPE_ERROR).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-162"><strong>adFileTime</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-162"><strong>adFileTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-163">64</span><span class="sxs-lookup"><span data-stu-id="7fc66-163">64</span></span></p></td>
<td><p><span data-ttu-id="7fc66-164">指示 64 位值，该值表示自 1601 年 1 月 1 日以来的 100 纳秒间隔的数量 (DBTYPE_FILETIME)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-164">Indicates a 64-bit value representing the number of 100-nanosecond intervals since January 1, 1601 (DBTYPE_FILETIME).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-165"><strong>adGUID</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-165"><strong>adGUID</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-166">72</span><span class="sxs-lookup"><span data-stu-id="7fc66-166">72</span></span></p></td>
<td><p><span data-ttu-id="7fc66-167">指示全局唯一标识符 (GUID) (DBTYPE_GUID)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-167">Indicates a globally unique identifier (GUID) (DBTYPE_GUID).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-168"><strong>adIDispatch</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-168"><strong>adIDispatch</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-169">9</span><span class="sxs-lookup"><span data-stu-id="7fc66-169">9</span></span></p></td>
<td><p><span data-ttu-id="7fc66-170">指示指向 COM 对象上的 <strong>IDispatch</strong> 接口的指针 (DBTYPE_IDISPATCH)。
</span><span class="sxs-lookup"><span data-stu-id="7fc66-170">Indicates a pointer to an <strong>IDispatch</strong> interface on a COM object (DBTYPE_IDISPATCH).</span></span></p><p><span data-ttu-id="7fc66-171"><strong>注意</strong>： ADO 当前不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="7fc66-171"><strong>NOTE</strong>: This data type is currently not supported by ADO.</span></span> <span data-ttu-id="7fc66-172">使用情况可能会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="7fc66-172">Usage may cause unpredictable results.</span></span></p>
</td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-173"><strong>adInteger</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-173"><strong>adInteger</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-174">3</span><span class="sxs-lookup"><span data-stu-id="7fc66-174">3</span></span></p></td>
<td><p><span data-ttu-id="7fc66-175">指示四字节有符号整数 (DBTYPE_I4)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-175">Indicates a four-byte signed integer (DBTYPE_I4).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-176"><strong>adIUnknown</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-176"><strong>adIUnknown</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-177">13</span><span class="sxs-lookup"><span data-stu-id="7fc66-177">13</span></span></p></td>
<td><p><span data-ttu-id="7fc66-178">指示指向 COM 对象上的 <strong>IUnknown</strong> 接口的指针 (DBTYPE_IUNKNOWN)。
</span><span class="sxs-lookup"><span data-stu-id="7fc66-178">Indicates a pointer to an <strong>IUnknown</strong> interface on a COM object (DBTYPE_IUNKNOWN).</span></span></p><p><span data-ttu-id="7fc66-179"><strong>注意</strong>： ADO 当前不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="7fc66-179"><strong>NOTE</strong>: This data type is currently not supported by ADO.</span></span> <span data-ttu-id="7fc66-180">使用情况可能会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="7fc66-180">Usage may cause unpredictable results.</span></span>
</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-181"><strong>adLongVarBinary</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-181"><strong>adLongVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-182">205</span><span class="sxs-lookup"><span data-stu-id="7fc66-182">205</span></span></p></td>
<td><p><span data-ttu-id="7fc66-183">指示长二进制值。</span><span class="sxs-lookup"><span data-stu-id="7fc66-183">Indicates a long binary value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-184"><strong>adLongVarChar</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-184"><strong>adLongVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-185">201</span><span class="sxs-lookup"><span data-stu-id="7fc66-185">201</span></span></p></td>
<td><p><span data-ttu-id="7fc66-186">指示长字符串值。</span><span class="sxs-lookup"><span data-stu-id="7fc66-186">Indicates a long string value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-187"><strong>adLongVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-187"><strong>adLongVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-188">203</span><span class="sxs-lookup"><span data-stu-id="7fc66-188">203</span></span></p></td>
<td><p><span data-ttu-id="7fc66-189">指示长空结尾 Unicode 字符串值。</span><span class="sxs-lookup"><span data-stu-id="7fc66-189">Indicates a long null-terminated Unicode string value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-190"><strong>adNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-190"><strong>adNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-191">131</span><span class="sxs-lookup"><span data-stu-id="7fc66-191">131</span></span></p></td>
<td><p><span data-ttu-id="7fc66-192">指示具有固定精度和范围的确切数值 (DBTYPE_NUMERIC)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-192">Indicates an exact numeric value with a fixed precision and scale (DBTYPE_NUMERIC).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-193"><strong>adPropVariant</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-193"><strong>adPropVariant</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-194">138</span><span class="sxs-lookup"><span data-stu-id="7fc66-194">138</span></span></p></td>
<td><p><span data-ttu-id="7fc66-195">指示 Automation PROPVARIANT 类型 (DBTYPE_PROP_VARIANT)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-195">Indicates an Automation PROPVARIANT (DBTYPE_PROP_VARIANT).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-196"><strong>adSingle</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-196"><strong>adSingle</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-197">4</span><span class="sxs-lookup"><span data-stu-id="7fc66-197">4</span></span></p></td>
<td><p><span data-ttu-id="7fc66-198">指示单精度浮点值 (DBTYPE_R4)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-198">Indicates a single-precision floating-point value (DBTYPE_R4).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-199"><strong>adSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-199"><strong>adSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-200">2</span><span class="sxs-lookup"><span data-stu-id="7fc66-200">2</span></span></p></td>
<td><p><span data-ttu-id="7fc66-201">指示双字节有符号整数 (DBTYPE_I2)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-201">Indicates a two-byte signed integer (DBTYPE_I2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-202"><strong>adTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-202"><strong>adTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-203">16</span><span class="sxs-lookup"><span data-stu-id="7fc66-203">16</span></span></p></td>
<td><p><span data-ttu-id="7fc66-204">指示单字节有符号整数 (DBTYPE_I1)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-204">Indicates a one-byte signed integer (DBTYPE_I1).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-205"><strong>adUnsignedBigInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-205"><strong>adUnsignedBigInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-206">21</span><span class="sxs-lookup"><span data-stu-id="7fc66-206">21</span></span></p></td>
<td><p><span data-ttu-id="7fc66-207">指示八字节无符号整数 (DBTYPE_UI8)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-207">Indicates an eight-byte unsigned integer (DBTYPE_UI8).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-208"><strong>adUnsignedInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-208"><strong>adUnsignedInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-209">19</span><span class="sxs-lookup"><span data-stu-id="7fc66-209">19</span></span></p></td>
<td><p><span data-ttu-id="7fc66-210">指示四字节无符号整数 (DBTYPE_UI4)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-210">Indicates a four-byte unsigned integer (DBTYPE_UI4).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-211"><strong>adUnsignedSmallInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-211"><strong>adUnsignedSmallInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-212">18</span><span class="sxs-lookup"><span data-stu-id="7fc66-212">18</span></span></p></td>
<td><p><span data-ttu-id="7fc66-213">指示双字节无符号整数 (DBTYPE_UI2)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-213">Indicates a two-byte unsigned integer (DBTYPE_UI2).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-214"><strong>adUnsignedTinyInt</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-214"><strong>adUnsignedTinyInt</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-215">17</span><span class="sxs-lookup"><span data-stu-id="7fc66-215">17</span></span></p></td>
<td><p><span data-ttu-id="7fc66-216">指示单字节无符号整数 (DBTYPE_UI1)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-216">Indicates a one-byte unsigned integer (DBTYPE_UI1).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-217"><strong>adUserDefined</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-217"><strong>adUserDefined</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-218">132</span><span class="sxs-lookup"><span data-stu-id="7fc66-218">132</span></span></p></td>
<td><p><span data-ttu-id="7fc66-219">指示用户定义的变量 (DBTYPE_UDT)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-219">Indicates a user-defined variable (DBTYPE_UDT).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-220"><strong>感</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-220"><strong>adVarBinary</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-221">204</span><span class="sxs-lookup"><span data-stu-id="7fc66-221">204</span></span></p></td>
<td><p><span data-ttu-id="7fc66-222">指示二进制值（仅限 <strong>Parameter</strong> 对象）。</span><span class="sxs-lookup"><span data-stu-id="7fc66-222">Indicates a binary value (<strong>Parameter</strong> object only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-223"><strong>以便您可以排除</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-223"><strong>adVarChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-224">200</span><span class="sxs-lookup"><span data-stu-id="7fc66-224">200</span></span></p></td>
<td><p><span data-ttu-id="7fc66-225">指示字符串值。</span><span class="sxs-lookup"><span data-stu-id="7fc66-225">Indicates a string value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-226"><strong>adVariant</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-226"><strong>adVariant</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-227">12</span><span class="sxs-lookup"><span data-stu-id="7fc66-227">12</span></span></p></td>
<td><p><span data-ttu-id="7fc66-228">指示自动化<strong>变量型</strong> (DBTYPE_VARIANT)。
</span><span class="sxs-lookup"><span data-stu-id="7fc66-228">Indicates an Automation <strong>Variant</strong> (DBTYPE_VARIANT).</span></span></p><p><span data-ttu-id="7fc66-229"><strong>注意</strong>： ADO 当前不支持此数据类型。</span><span class="sxs-lookup"><span data-stu-id="7fc66-229"><strong>NOTE</strong>: This data type is currently not supported by ADO.</span></span> <span data-ttu-id="7fc66-230">使用情况可能会导致无法预料的结果。</span><span class="sxs-lookup"><span data-stu-id="7fc66-230">Usage may cause unpredictable results.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-231"><strong>adVarNumeric</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-231"><strong>adVarNumeric</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-232">139</span><span class="sxs-lookup"><span data-stu-id="7fc66-232">139</span></span></p></td>
<td><p><span data-ttu-id="7fc66-233">指示数字值（仅限 <strong>Parameter</strong> 对象）。</span><span class="sxs-lookup"><span data-stu-id="7fc66-233">Indicates a numeric value (<strong>Parameter</strong> object only).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-234"><strong>adVarWChar</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-234"><strong>adVarWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-235">202</span><span class="sxs-lookup"><span data-stu-id="7fc66-235">202</span></span></p></td>
<td><p><span data-ttu-id="7fc66-236">指示空结尾 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="7fc66-236">Indicates a null-terminated Unicode character string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-237"><strong>adWChar</strong></span><span class="sxs-lookup"><span data-stu-id="7fc66-237"><strong>adWChar</strong></span></span></p></td>
<td><p><span data-ttu-id="7fc66-238">130</span><span class="sxs-lookup"><span data-stu-id="7fc66-238">130</span></span></p></td>
<td><p><span data-ttu-id="7fc66-239">指示空结尾 Unicode 字符串 (DBTYPE_WSTR)。</span><span class="sxs-lookup"><span data-stu-id="7fc66-239">Indicates a null-terminated Unicode character string (DBTYPE_WSTR).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="adowfc-equivalent"></a><span data-ttu-id="7fc66-240">ADO/WFC 等效值</span><span class="sxs-lookup"><span data-stu-id="7fc66-240">ADO/WFC equivalent</span></span>

<span data-ttu-id="7fc66-241">包： **com.ms.wfc.data**</span><span class="sxs-lookup"><span data-stu-id="7fc66-241">Package: **com.ms.wfc.data**</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7fc66-242">常量</span><span class="sxs-lookup"><span data-stu-id="7fc66-242">Constant</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-243">AdoEnums.DataType.ARRAY</span><span class="sxs-lookup"><span data-stu-id="7fc66-243">AdoEnums.DataType.ARRAY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-244">AdoEnums.DataType.BIGINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-244">AdoEnums.DataType.BIGINT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-245">AdoEnums.DataType.BINARY</span><span class="sxs-lookup"><span data-stu-id="7fc66-245">AdoEnums.DataType.BINARY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-246">AdoEnums.DataType.BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="7fc66-246">AdoEnums.DataType.BOOLEAN</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-247">AdoEnums.DataType.BSTR</span><span class="sxs-lookup"><span data-stu-id="7fc66-247">AdoEnums.DataType.BSTR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-248">AdoEnums.DataType.CHAPTER</span><span class="sxs-lookup"><span data-stu-id="7fc66-248">AdoEnums.DataType.CHAPTER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-249">AdoEnums.DataType.CHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-249">AdoEnums.DataType.CHAR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-250">AdoEnums.DataType.CURRENCY</span><span class="sxs-lookup"><span data-stu-id="7fc66-250">AdoEnums.DataType.CURRENCY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-251">AdoEnums.DataType.DATE</span><span class="sxs-lookup"><span data-stu-id="7fc66-251">AdoEnums.DataType.DATE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-252">AdoEnums.DataType.DBDATE</span><span class="sxs-lookup"><span data-stu-id="7fc66-252">AdoEnums.DataType.DBDATE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-253">AdoEnums.DataType.DBTIME</span><span class="sxs-lookup"><span data-stu-id="7fc66-253">AdoEnums.DataType.DBTIME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-254">AdoEnums.DataType.DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="7fc66-254">AdoEnums.DataType.DBTIMESTAMP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-255">AdoEnums.DataType.DECIMAL</span><span class="sxs-lookup"><span data-stu-id="7fc66-255">AdoEnums.DataType.DECIMAL</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-256">AdoEnums.DataType.DOUBLE</span><span class="sxs-lookup"><span data-stu-id="7fc66-256">AdoEnums.DataType.DOUBLE</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-257">AdoEnums.DataType.EMPTY</span><span class="sxs-lookup"><span data-stu-id="7fc66-257">AdoEnums.DataType.EMPTY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-258">AdoEnums.DataType.ERROR</span><span class="sxs-lookup"><span data-stu-id="7fc66-258">AdoEnums.DataType.ERROR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-259">AdoEnums.DataType.FILETIME</span><span class="sxs-lookup"><span data-stu-id="7fc66-259">AdoEnums.DataType.FILETIME</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-260">AdoEnums.DataType.GUID</span><span class="sxs-lookup"><span data-stu-id="7fc66-260">AdoEnums.DataType.GUID</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-261">AdoEnums.DataType.IDISPATCH</span><span class="sxs-lookup"><span data-stu-id="7fc66-261">AdoEnums.DataType.IDISPATCH</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-262">AdoEnums.DataType.INTEGER</span><span class="sxs-lookup"><span data-stu-id="7fc66-262">AdoEnums.DataType.INTEGER</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-263">AdoEnums.DataType.IUNKNOWN</span><span class="sxs-lookup"><span data-stu-id="7fc66-263">AdoEnums.DataType.IUNKNOWN</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-264">AdoEnums.DataType.LONGVARBINARY</span><span class="sxs-lookup"><span data-stu-id="7fc66-264">AdoEnums.DataType.LONGVARBINARY</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-265">AdoEnums.DataType.LONGVARCHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-265">AdoEnums.DataType.LONGVARCHAR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-266">AdoEnums.DataType.LONGVARWCHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-266">AdoEnums.DataType.LONGVARWCHAR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-267">AdoEnums.DataType.NUMERIC</span><span class="sxs-lookup"><span data-stu-id="7fc66-267">AdoEnums.DataType.NUMERIC</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-268">AdoEnums.DataType.PROPVARIANT</span><span class="sxs-lookup"><span data-stu-id="7fc66-268">AdoEnums.DataType.PROPVARIANT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-269">AdoEnums.DataType.SINGLE</span><span class="sxs-lookup"><span data-stu-id="7fc66-269">AdoEnums.DataType.SINGLE</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-270">AdoEnums.DataType.SMALLINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-270">AdoEnums.DataType.SMALLINT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-271">AdoEnums.DataType.TINYINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-271">AdoEnums.DataType.TINYINT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-272">AdoEnums.DataType.UNSIGNEDBIGINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-272">AdoEnums.DataType.UNSIGNEDBIGINT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-273">AdoEnums.DataType.UNSIGNEDINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-273">AdoEnums.DataType.UNSIGNEDINT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-274">AdoEnums.DataType.UNSIGNEDSMALLINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-274">AdoEnums.DataType.UNSIGNEDSMALLINT</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-275">AdoEnums.DataType.UNSIGNEDTINYINT</span><span class="sxs-lookup"><span data-stu-id="7fc66-275">AdoEnums.DataType.UNSIGNEDTINYINT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-276">AdoEnums.DataType.USERDEFINED</span><span class="sxs-lookup"><span data-stu-id="7fc66-276">AdoEnums.DataType.USERDEFINED</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-277">AdoEnums.DataType.VARBINARY</span><span class="sxs-lookup"><span data-stu-id="7fc66-277">AdoEnums.DataType.VARBINARY</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-278">AdoEnums.DataType.VARCHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-278">AdoEnums.DataType.VARCHAR</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-279">AdoEnums.DataType.VARIANT</span><span class="sxs-lookup"><span data-stu-id="7fc66-279">AdoEnums.DataType.VARIANT</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-280">AdoEnums.DataType.VARNUMERIC</span><span class="sxs-lookup"><span data-stu-id="7fc66-280">AdoEnums.DataType.VARNUMERIC</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fc66-281">AdoEnums.DataType.VARWCHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-281">AdoEnums.DataType.VARWCHAR</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fc66-282">AdoEnums.DataType.WCHAR</span><span class="sxs-lookup"><span data-stu-id="7fc66-282">AdoEnums.DataType.WCHAR</span></span></p></td>
</tr>
</tbody>
</table>

