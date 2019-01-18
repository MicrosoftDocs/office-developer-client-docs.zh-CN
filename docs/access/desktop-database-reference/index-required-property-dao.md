---
title: Index.Required 属性 (DAO)
TOCTitle: Required Property
ms:assetid: ec8fafc4-8155-c48e-b3c8-2d9be425175a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836310(v=office.15)
ms:contentKeyID: 48548518
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052963
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a2660a4cb422d91cf46b98a8d3870d2ab2db73fc
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28703130"
---
# <a name="indexrequired-property-dao"></a><span data-ttu-id="fba39-102">Index.Required 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fba39-102">Index.Required property (DAO)</span></span>

<span data-ttu-id="fba39-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fba39-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fba39-104">设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象是否需要一个非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="fba39-104">Sets or returns a value that indicates whether a **[Field](field-object-dao.md)** object requires a non-Null value.</span></span>

## <a name="syntax"></a><span data-ttu-id="fba39-105">语法</span><span class="sxs-lookup"><span data-stu-id="fba39-105">Syntax</span></span>

<span data-ttu-id="fba39-106">*表达式*。必填</span><span class="sxs-lookup"><span data-stu-id="fba39-106">*expression* .Required</span></span>

<span data-ttu-id="fba39-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fba39-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fba39-108">注解</span><span class="sxs-lookup"><span data-stu-id="fba39-108">Remarks</span></span>

> [!NOTE]
> <span data-ttu-id="fba39-p101">[!注释] 在您可以为 **Index** 对象或 **Field** 对象设置该属性时，请为 **Field** 对象设置该属性。这是因为需要先检查 **Field** 对象属性设置的有效性，然后检查 **Index** 对象属性设置的有效性。</span><span class="sxs-lookup"><span data-stu-id="fba39-p101">When you can set this property for either an **Index** object or a **Field** object, set it for the **Field** object. The validity of the property setting for a **Field** object is checked before that of an **Index** object.</span></span>

<span data-ttu-id="fba39-111">**Required** 属性的可用性取决于包含 [Fields](fields-collection-dao.md) 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="fba39-111">The availability of the **Required** property depends on the object that contains the [Fields](fields-collection-dao.md) collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fba39-112">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="fba39-112">If the Fields collection belongs to a</span></span></p></th>
<th><p><span data-ttu-id="fba39-113">则 Required</span><span class="sxs-lookup"><span data-stu-id="fba39-113">Then Required is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fba39-114"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="fba39-114"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fba39-115">不支持</span><span class="sxs-lookup"><span data-stu-id="fba39-115">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-116"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fba39-116"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fba39-117">只读</span><span class="sxs-lookup"><span data-stu-id="fba39-117">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba39-118"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fba39-118"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fba39-119">只读</span><span class="sxs-lookup"><span data-stu-id="fba39-119">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fba39-120"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fba39-120"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fba39-121">不支持</span><span class="sxs-lookup"><span data-stu-id="fba39-121">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fba39-122"><strong>TableDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="fba39-122"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="fba39-123">读/写</span><span class="sxs-lookup"><span data-stu-id="fba39-123">Read/write</span></span></p></td>
</tr>
</tbody>
</table>

