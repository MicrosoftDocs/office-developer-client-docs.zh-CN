---
title: "Unique Table、Unique Schema、Unique Catalog 属性 \x97 动态 (ADO)"
TOCTitle: Unique Table, Unique Schema, Unique Catalog Properties--Dynamic (ADO)
ms:assetid: e6374782-755b-322b-21de-6d6a386dcd98
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250169(v=office.15)
ms:contentKeyID: 48548374
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: cd21c8b7c71f5fe1c95d347758e486f3854efab0
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466231"
---
# <a name="unique-table-unique-schema-unique-catalog-properties--dynamic-ado"></a><span data-ttu-id="4f612-102">Unique Table、Unique Schema、Unique Catalog 属性  动态 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4f612-102">Unique Table, Unique Schema, Unique Catalog Properties--Dynamic (ADO)</span></span>


<span data-ttu-id="4f612-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4f612-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4f612-104">支持对 [Recordset](recordset-object-ado.md)（通过多个基表上的 JOIN 操作形成）中特定基表的修改进行严密控制。</span><span class="sxs-lookup"><span data-stu-id="4f612-104">Enables you to closely control modifications to a particular base table in a [Recordset](recordset-object-ado.md) that was formed by a JOIN operation on multiple base tables.</span></span>

  - <span data-ttu-id="4f612-105">**Unique Table** 指定允许在其上进行更新、插入和删除的基表的名称。</span><span class="sxs-lookup"><span data-stu-id="4f612-105">**Unique Table** specifies the name of the base table upon which updates, insertions, and deletions are allowed.</span></span>

  - <span data-ttu-id="4f612-106">**Unique Schema** 指定该表的所有者的*架构*或名称。</span><span class="sxs-lookup"><span data-stu-id="4f612-106">**Unique Schema** specifies the *schema*, or name of the owner of the table.</span></span>

  - <span data-ttu-id="4f612-107">**Unique Catalog** 指定包含该表的数据库的*目录*或名称。</span><span class="sxs-lookup"><span data-stu-id="4f612-107">**Unique Catalog** specifies the *catalog*, or name of the database containing the table.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="4f612-108">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="4f612-108">Settings and Return Values</span></span>

<span data-ttu-id="4f612-109">设置或返回一个表示表、架构或目录的名称的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="4f612-109">Sets or returns a **String** value that is the name of a table, schema, or catalog.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f612-110">备注</span><span class="sxs-lookup"><span data-stu-id="4f612-110">Remarks</span></span>

<span data-ttu-id="4f612-p101">所需的基表由其目录、架构和表名称唯一标识。当设置了 **Unique Table** 属性时， **Unique Schema** 或 **Unique Catalog** 属性的值将用于查找基表。可以（但并不要求）在设置 **Unique Table** 属性前先设置 **Unique Schema** 和/或 **Unique Catalog** 属性。</span><span class="sxs-lookup"><span data-stu-id="4f612-p101">The desired base table is uniquely identified by its catalog, schema, and table names. When the **Unique Table** property is set, the values of the **Unique Schema** or **Unique Catalog** properties are used to find the base table. It is intended, but not required, that either or both the **Unique Schema** and **Unique Catalog** properties be set before the **Unique Table** property is set.</span></span>

<span data-ttu-id="4f612-p102">**Unique Table** 的主键将作为整个 **Recordset** 的主键处理。任何需要使用主键的方法都将使用此键。</span><span class="sxs-lookup"><span data-stu-id="4f612-p102">The primary key of the **Unique Table** is treated as the primary key of the entire **Recordset**. This is the key that is used for any method requiring a primary key.</span></span>

<span data-ttu-id="4f612-p103">设置 **Unique Table** 时， [Delete](delete-method-ado-recordset.md) 方法仅影响指定的表。 [AddNew](addnew-method-ado.md)、[Resync](resync-method-ado.md)、[Update](update-method-ado.md) 和 [UpdateBatch](updatebatch-method-ado.md) 方法会影响 **Recordset** 所有相关的基础基表。</span><span class="sxs-lookup"><span data-stu-id="4f612-p103">While **Unique Table** is set, the [Delete](delete-method-ado-recordset.md) method affects only the named table. The [AddNew](addnew-method-ado.md), [Resync](resync-method-ado.md), [Update](update-method-ado.md), and [UpdateBatch](updatebatch-method-ado.md) methods affect any appropriate underlying base tables of the **Recordset**.</span></span>

<span data-ttu-id="4f612-p104">在进行任何自定义的重新同步操作前，必须指定 **Unique Table** 。如果尚未指定 **Unique Table** ， [Resync Command](resync-command-property-dynamic-ado.md) 属性将不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="4f612-p104">**Unique Table** must be specified before doing any custom resynchronizations. If **Unique Table** has not been specified, the [Resync Command](resync-command-property-dynamic-ado.md) property will have no effect.</span></span>

<span data-ttu-id="4f612-120">如果不能找到唯一的基表，则将导致出现运行时错误。</span><span class="sxs-lookup"><span data-stu-id="4f612-120">A run-time error results if a unique base table cannot be found.</span></span>

<span data-ttu-id="4f612-121">这些动态属性都将在 **CursorLocation** 属性设置为 [adUseClient](properties-collection-ado.md) 时追加到 [Recordset](cursorlocation-property-ado.md) 对象的 **Properties** 集合中。</span><span class="sxs-lookup"><span data-stu-id="4f612-121">These dynamic properties are all appended to the **Recordset** object [Properties](properties-collection-ado.md) collection when the [CursorLocation](cursorlocation-property-ado.md) property is set to **adUseClient**.</span></span>
