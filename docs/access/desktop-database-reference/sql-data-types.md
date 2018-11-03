---
title: SQL 数据类型 （访问桌面数据库参考 （英文）
TOCTitle: SQL Data Types
ms:assetid: 4fc2dc8c-7825-8fbb-ff91-a0f39ef90115
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193793(v=office.15)
ms:contentKeyID: 48544783
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277590
f1_categories:
- Office.Version=v15
ms.openlocfilehash: cfaecd26ebd3f747a0e2db2ec530c151928fec74
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936908"
---
# <a name="sql-data-types"></a><span data-ttu-id="01cea-102">SQL 数据类型</span><span class="sxs-lookup"><span data-stu-id="01cea-102">SQL Data Types</span></span>


<span data-ttu-id="01cea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="01cea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="01cea-104">Microsoft Access 数据库引擎 SQL 数据类型包括由 Microsoft Jet 数据库引擎定义的 13 主要数据类型以及若干可识别为这些数据类型的有效同义词。</span><span class="sxs-lookup"><span data-stu-id="01cea-104">The Microsoft Access database engine SQL data types consist of 13 primary data types defined by the Microsoft Jet database engine and several valid synonyms recognized for these data types.</span></span>

<span data-ttu-id="01cea-p101">下表列出了主要数据类型。同义词是在 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)中标识的。</span><span class="sxs-lookup"><span data-stu-id="01cea-p101">The following table lists the primary data types. The synonyms are identified in [Microsoft Access Database Engine SQL Reserved Words](sql-reserved-words.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="01cea-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="01cea-107">Data type</span></span></p></th>
<th><p><span data-ttu-id="01cea-108">存储空间大小</span><span class="sxs-lookup"><span data-stu-id="01cea-108">Storage size</span></span></p></th>
<th><p><span data-ttu-id="01cea-109">说明</span><span class="sxs-lookup"><span data-stu-id="01cea-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01cea-110">BINARY</span><span class="sxs-lookup"><span data-stu-id="01cea-110">BINARY</span></span></p></td>
<td><p><span data-ttu-id="01cea-111">每个字符占 1 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-111">1 byte per character</span></span></p></td>
<td><p><span data-ttu-id="01cea-p102">任何类型的数据都可以存储在这种类型的字段中。不进行数据转换（例如，转换成文本）。数据怎样输入到二进制字段就怎样作为输出显示，</span><span class="sxs-lookup"><span data-stu-id="01cea-p102">Any type of data may be stored in a field of this type. No translation of the data (for example, to text) is made. How the data is input in a binary field dictates how it will appear as output.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-115">BIT</span><span class="sxs-lookup"><span data-stu-id="01cea-115">BIT</span></span></p></td>
<td><p><span data-ttu-id="01cea-116">1 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-116">1 byte</span></span></p></td>
<td><p><span data-ttu-id="01cea-117">值为 Yes 和 No，并且该字段只能取这两个值中的一个。</span><span class="sxs-lookup"><span data-stu-id="01cea-117">Yes and No values and fields that contain only one of two values.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-118">TINYINT</span><span class="sxs-lookup"><span data-stu-id="01cea-118">TINYINT</span></span></p></td>
<td><p><span data-ttu-id="01cea-119">1 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-119">1 byte</span></span></p></td>
<td><p><span data-ttu-id="01cea-120">在 0 和 255 之间的整数值。</span><span class="sxs-lookup"><span data-stu-id="01cea-120">An integer value between 0 and 255.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-121">MONEY</span><span class="sxs-lookup"><span data-stu-id="01cea-121">MONEY</span></span></p></td>
<td><p><span data-ttu-id="01cea-122">8 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-122">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-123">在 – 922,337,203,685,477.5808 和 922,337,203,685,477.5807 之间的依比例调整整数。</span><span class="sxs-lookup"><span data-stu-id="01cea-123">A scaled integer between – 922,337,203,685,477.5808 and 922,337,203,685,477.5807.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-124">DATETIME （请参阅 DOUBLE）</span><span class="sxs-lookup"><span data-stu-id="01cea-124">DATETIME (See DOUBLE)</span></span></p></td>
<td><p><span data-ttu-id="01cea-125">8 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-125">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-126">在 100 年和 9999 年之间的日期或时间值。</span><span class="sxs-lookup"><span data-stu-id="01cea-126">A date or time value between the years 100 and 9999.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-127">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="01cea-127">UNIQUEIDENTIFIER</span></span></p></td>
<td><p><span data-ttu-id="01cea-128">128 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-128">128 bits</span></span></p></td>
<td><p><span data-ttu-id="01cea-129">用于远程过程调用的唯一标识数字。</span><span class="sxs-lookup"><span data-stu-id="01cea-129">A unique identification number used with remote procedure calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-130">REAL</span><span class="sxs-lookup"><span data-stu-id="01cea-130">REAL</span></span></p></td>
<td><p><span data-ttu-id="01cea-131">4 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-131">4 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-132">单精度浮点值，负数值从 – 3.402823E38 到 – 1.401298E-45，正数值从 1.401298E-45 到 3.402823E38，包括零。</span><span class="sxs-lookup"><span data-stu-id="01cea-132">A single-precision floating-point value with a range of – 3.402823E38 to – 1.401298E-45 for negative values, 1.401298E-45 to 3.402823E38 for positive values, and 0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="01cea-133">FLOAT</span></span></p></td>
<td><p><span data-ttu-id="01cea-134">8 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-134">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-135">双精度浮点值，负数值从 – 1.79769313486232E308 到 – 4.94065645841247E-324，正数值从 4.94065645841247E-324 到 1.79769313486232E308，包括零。</span><span class="sxs-lookup"><span data-stu-id="01cea-135">A double-precision floating-point value with a range of – 1.79769313486232E308 to – 4.94065645841247E-324 for negative values, 4.94065645841247E-324 to 1.79769313486232E308 for positive values, and 0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-136">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="01cea-136">SMALLINT</span></span></p></td>
<td><p><span data-ttu-id="01cea-137">2 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-137">2 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-p103">介于 – 32,768 和 32,767 之间的短整型。（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="01cea-p103">A short integer between – 32,768 and 32,767. (See Notes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-140">INTEGER</span><span class="sxs-lookup"><span data-stu-id="01cea-140">INTEGER</span></span></p></td>
<td><p><span data-ttu-id="01cea-141">4 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-141">4 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-p104">介于 – 2,147,483,648 和 2,147,483,647 之间的长整型。（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="01cea-p104">A long integer between – 2,147,483,648 and 2,147,483,647. (See Notes)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-144">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="01cea-144">DECIMAL</span></span></p></td>
<td><p><span data-ttu-id="01cea-145">17 个字节</span><span class="sxs-lookup"><span data-stu-id="01cea-145">17 bytes</span></span></p></td>
<td><p><span data-ttu-id="01cea-p105">精确的数字数据类型，取值范围从 1028 - 1 到 - 1028 - 1. 可以定义精度 (1 - 28) 和大小（0 -- 定义精度）。默认的精度和大小分别为 18 和 0。</span><span class="sxs-lookup"><span data-stu-id="01cea-p105">An exact numeric data type that holds values from 1028 - 1 through - 1028 - 1. You can define both precision (1 - 28) and scale (0 - defined precision). The default precision and scale are 18 and 0, respectively.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-149">TEXT</span><span class="sxs-lookup"><span data-stu-id="01cea-149">TEXT</span></span></p></td>
<td><p><span data-ttu-id="01cea-150">每个字符占 2 个字节（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="01cea-150">2 bytes per character (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="01cea-151">从零到最大值 2.14 吉字节。</span><span class="sxs-lookup"><span data-stu-id="01cea-151">Zero to a maximum of 2.14 gigabytes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01cea-152">IMAGE</span><span class="sxs-lookup"><span data-stu-id="01cea-152">IMAGE</span></span></p></td>
<td><p><span data-ttu-id="01cea-153">根据需要</span><span class="sxs-lookup"><span data-stu-id="01cea-153">As required</span></span></p></td>
<td><p><span data-ttu-id="01cea-p106">从零到最大值 2.14 吉字节。用于 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="01cea-p106">Zero to a maximum of 2.14 gigabytes. Used for OLE objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01cea-156">CHARACTER</span><span class="sxs-lookup"><span data-stu-id="01cea-156">CHARACTER</span></span></p></td>
<td><p><span data-ttu-id="01cea-157">每个字符占 2 个字节（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="01cea-157">2 bytes per character (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="01cea-158">从零到 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="01cea-158">Zero to 255 characters.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="01cea-p107">种子和增量都能够通过 <A href="alter-table-statement-microsoft-access-sql.md">ALTER TABLE 语句</A>进行修改。根据自动为列生成的新种子和增量值，插入表中的新行会具有值。如果新种子和增量产生的值与根据先前的种子和增量所产生的值相匹配，将产生重复值。如果该列是一个主键，那么生成重复值时插入新行就会产生错误。</span><span class="sxs-lookup"><span data-stu-id="01cea-p107">Both the seed and the increment can be modified using an <A href="alter-table-statement-microsoft-access-sql.md">ALTER TABLE statement</A>. New rows inserted into the table will have values, based on the new seed and increment values, that are automatically generated for the column. If the new seed and increment can yield values that match values generated based on the preceding seed and increment, duplicates will be generated. If the column is a primary key, then inserting new rows may result in errors when duplicate values are generated.</span></span></P>
> <LI>
> <P><span data-ttu-id="01cea-p108">若要查找用于自动增量列的最后一个值，可以使用以下语句：SELECT @@IDENTITY。不能指定表名。返回的值来自更新的最后一个表（其中包含一个自动增加列）。</span><span class="sxs-lookup"><span data-stu-id="01cea-p108">To find the last value that was used for an auto-increment column, you can use the following statement: SELECT @@IDENTITY. You cannot specify a table name. The value returned is from the last table, containing an auto-increment column, that was updated.</span></span></P></LI></UL>


