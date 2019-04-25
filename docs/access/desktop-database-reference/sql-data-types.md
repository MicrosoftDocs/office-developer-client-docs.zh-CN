---
title: SQL 数据类型（Access 桌面数据库参考）
TOCTitle: SQL data types
ms:assetid: 4fc2dc8c-7825-8fbb-ff91-a0f39ef90115
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193793(v=office.15)
ms:contentKeyID: 48544783
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- jetsql40.chm5277590
f1_categories:
- Office.Version=v15
localization_priority: Priority
ms.openlocfilehash: fb72a0090550692e7cf5028a6a58a078fc5d9d32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308579"
---
# <a name="sql-data-types"></a><span data-ttu-id="e4c86-102">SQL 数据类型</span><span class="sxs-lookup"><span data-stu-id="e4c86-102">SQL data types</span></span>

<span data-ttu-id="e4c86-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e4c86-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e4c86-104">Microsoft Access 数据库引擎 SQL 数据类型包含由 Microsoft Jet 数据库引擎定义的 13 种主要数据类型，以及若干可识别为这些数据类型的有效同义词。</span><span class="sxs-lookup"><span data-stu-id="e4c86-104">The Microsoft Access database engine SQL data types consist of 13 primary data types defined by the Microsoft® Jet database engine and several valid synonyms recognized for these data types.</span></span>

<span data-ttu-id="e4c86-105">下表列出了主要的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e4c86-105">The following table lists the primary data types.</span></span> <span data-ttu-id="e4c86-106">同义词是在 [Microsoft Access 数据库引擎 SQL 保留字](sql-reserved-words.md)中标识的。</span><span class="sxs-lookup"><span data-stu-id="e4c86-106">The synonyms are identified in [Microsoft Access Database Engine SQL Reserved Words](sql-reserved-words.md).</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e4c86-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e4c86-107">Data type</span></span></p></th>
<th><p><span data-ttu-id="e4c86-108">存储空间大小</span><span class="sxs-lookup"><span data-stu-id="e4c86-108">Storage size</span></span></p></th>
<th><p><span data-ttu-id="e4c86-109">说明</span><span class="sxs-lookup"><span data-stu-id="e4c86-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-110">BINARY</span><span class="sxs-lookup"><span data-stu-id="e4c86-110">Binary</span></span></p></td>
<td><p><span data-ttu-id="e4c86-111">每个字符 1 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-111">1 byte per character</span></span></p></td>
<td><p><span data-ttu-id="e4c86-p102">任何类型的数据都可能存储在此类型的字段中。没有进行数据转换（如转换为文本）。数据在二进制字段中的输入方式决定其作为输出的显示方式。</span><span class="sxs-lookup"><span data-stu-id="e4c86-p102">Any type of data may be stored in a field of this type. No translation of the data (for example, to text) is made. How the data is input in a binary field dictates how it will appear as output.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-115">BIT</span><span class="sxs-lookup"><span data-stu-id="e4c86-115">BIT</span></span></p></td>
<td><p><span data-ttu-id="e4c86-116">1 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-116">1 byte</span></span></p></td>
<td><p><span data-ttu-id="e4c86-117">Yes 和 No 值，以及只包含这两值之一的字段。</span><span class="sxs-lookup"><span data-stu-id="e4c86-117">Yes and No values and fields that contain only one of two values.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-118">TINYINT</span><span class="sxs-lookup"><span data-stu-id="e4c86-118">TINYINT</span></span></p></td>
<td><p><span data-ttu-id="e4c86-119">1 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-119">1 byte</span></span></p></td>
<td><p><span data-ttu-id="e4c86-120">0 和 255 之间的一个整数值。</span><span class="sxs-lookup"><span data-stu-id="e4c86-120">An integer value between 0 and 255.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-121">MONEY</span><span class="sxs-lookup"><span data-stu-id="e4c86-121">MONEY</span></span></p></td>
<td><p><span data-ttu-id="e4c86-122">8 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-122">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-123">在 – 922,337,203,685,477.5808 和 922,337,203,685,477.5807 之间的依比例调整整数。</span><span class="sxs-lookup"><span data-stu-id="e4c86-123">A scaled integer between – 922,337,203,685,477.5808 and 922,337,203,685,477.5807.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-124">DATETIME（请参阅 DOUBLE）</span><span class="sxs-lookup"><span data-stu-id="e4c86-124">DATETIME
(See DOUBLE)</span></span></p></td>
<td><p><span data-ttu-id="e4c86-125">8 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-125">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-126">100 年和 9999 年之间的日期或时间值。</span><span class="sxs-lookup"><span data-stu-id="e4c86-126">A date or time value between the years 100 and 9999.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-127">UNIQUEIDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="e4c86-127">UNIQUEIDENTIFIER</span></span></p></td>
<td><p><span data-ttu-id="e4c86-128">128 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-128">128 bits</span></span></p></td>
<td><p><span data-ttu-id="e4c86-129">用于远程过程调用的唯一识别号。</span><span class="sxs-lookup"><span data-stu-id="e4c86-129">A unique identification number used with remote procedure calls.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-130">REAL</span><span class="sxs-lookup"><span data-stu-id="e4c86-130">REAL</span></span></p></td>
<td><p><span data-ttu-id="e4c86-131">4 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-131">4 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-132">单精度浮点值，可以是任何从 -3.402823E38 到 -1.401298E-45 的负数、从 1.401298E-45 到 3.402823E38 的正数，还可以是 0。</span><span class="sxs-lookup"><span data-stu-id="e4c86-132">A single-precision floating-point value with a range of – 3.402823E38 to – 1.401298E-45 for negative values, 1.401298E-45 to 3.402823E38 for positive values, and 0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="e4c86-133">FLOAT</span></span></p></td>
<td><p><span data-ttu-id="e4c86-134">8 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-134">8 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-135">双精度浮点值，可以是任何从 -1.79769313486232E308 到 -4.94065645841247E-324 的负数、从 4.94065645841247E-324 到 1.79769313486232E308 的正数，还可以是 0。</span><span class="sxs-lookup"><span data-stu-id="e4c86-135">A double-precision floating-point value with a range of – 1.79769313486232E308 to – 4.94065645841247E-324 for negative values, 4.94065645841247E-324 to 1.79769313486232E308 for positive values, and 0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-136">SMALLINT</span><span class="sxs-lookup"><span data-stu-id="e4c86-136">SMALLINT</span></span></p></td>
<td><p><span data-ttu-id="e4c86-137">2 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-137">2 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-p103">介于 – 32,768 和 32,767 之间的短整型。（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="e4c86-p103">A short integer between – 32,768 and 32,767. (See Notes)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-140">INTEGER</span><span class="sxs-lookup"><span data-stu-id="e4c86-140">Integer</span></span></p></td>
<td><p><span data-ttu-id="e4c86-141">4 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-141">4 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-p104">介于 – 2,147,483,648 和 2,147,483,647 之间的长整型。（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="e4c86-p104">A long integer between – 2,147,483,648 and 2,147,483,647. (See Notes)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-144">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="e4c86-144">DECIMAL</span></span></p></td>
<td><p><span data-ttu-id="e4c86-145">17 个字节</span><span class="sxs-lookup"><span data-stu-id="e4c86-145">17 bytes</span></span></p></td>
<td><p><span data-ttu-id="e4c86-p105">包含从 1028 - 1 直到 -1028 - 1 范围内的值的准确数字数据类型。可以定义精度 (1 - 28) 和小数位数（0 - 指定精度）。默认精度和小数位数分别为 18 和 0。</span><span class="sxs-lookup"><span data-stu-id="e4c86-p105">An exact numeric data type that holds values from 1028 - 1 through - 1028 - 1. You can define both precision (1 - 28) and scale (0 - defined precision). The default precision and scale are 18 and 0, respectively.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-149">TEXT</span><span class="sxs-lookup"><span data-stu-id="e4c86-149">TEXT</span></span></p></td>
<td><p><span data-ttu-id="e4c86-150">每个字符占 2 个字节（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="e4c86-150">2 bytes per character (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="e4c86-151">0 至 2.14 GB（至多）。</span><span class="sxs-lookup"><span data-stu-id="e4c86-151">Zero to a maximum of 2.14 gigabytes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4c86-152">IMAGE</span><span class="sxs-lookup"><span data-stu-id="e4c86-152">Image</span></span></p></td>
<td><p><span data-ttu-id="e4c86-153">根据需要确定</span><span class="sxs-lookup"><span data-stu-id="e4c86-153">As required</span></span></p></td>
<td><p><span data-ttu-id="e4c86-p106">0 至 2.14 GB（至多）。用于 OLE 对象。</span><span class="sxs-lookup"><span data-stu-id="e4c86-p106">Zero to a maximum of 2.14 gigabytes. Used for OLE objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4c86-156">CHARACTER</span><span class="sxs-lookup"><span data-stu-id="e4c86-156">Character</span></span></p></td>
<td><p><span data-ttu-id="e4c86-157">每个字符占 2 个字节（请参阅“注释”）</span><span class="sxs-lookup"><span data-stu-id="e4c86-157">2 bytes per character (See Notes)</span></span></p></td>
<td><p><span data-ttu-id="e4c86-158">0 至 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="e4c86-158">Zero to 255 characters.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> - <span data-ttu-id="e4c86-p107">种子和增量都能够通过 [ALTER TABLE 语句](alter-table-statement-microsoft-access-sql.md)进行修改。根据自动为列生成的新种子和增量值，插入表中的新行会具有值。如果新种子和增量产生的值与根据先前的种子和增量所产生的值相匹配，将产生重复值。如果该列是一个主键，那么生成重复值时插入新行就会产生错误。</span><span class="sxs-lookup"><span data-stu-id="e4c86-p107">Both the seed and the increment can be modified using an [ALTER TABLE statement](alter-table-statement-microsoft-access-sql.md). New rows inserted into the table will have values, based on the new seed and increment values, that are automatically generated for the column. If the new seed and increment can yield values that match values generated based on the preceding seed and increment, duplicates will be generated. If the column is a primary key, then inserting new rows may result in errors when duplicate values are generated.</span></span>
> - <span data-ttu-id="e4c86-p108">若要查找用于自动增量列的最后一个值，可以使用以下语句：SELECT @@IDENTITY。不能指定表名。返回的值来自更新的最后一个表（其中包含一个自动增加列）。</span><span class="sxs-lookup"><span data-stu-id="e4c86-p108">To find the last value that was used for an auto-increment column, you can use the following statement: SELECT @@IDENTITY. You cannot specify a table name. The value returned is from the last table, containing an auto-increment column, that was updated.</span></span>
