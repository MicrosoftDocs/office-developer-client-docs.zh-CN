---
title: Index.Required Property (DAO)
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
ms.openlocfilehash: 71ea383cbf1c55fb15b484fea039c71c44a4e470
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25881410"
---
# <a name="indexrequired-property-dao"></a><span data-ttu-id="57b14-102">Index.Required Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="57b14-102">Index.Required Property (DAO)</span></span>


<span data-ttu-id="57b14-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="57b14-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="57b14-104">设置或返回一个值，该值指示 **[Field](field-object-dao.md)** 对象是否需要一个非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="57b14-104">Sets or returns a value that indicates whether a **[Field](field-object-dao.md)** object requires a non-Null value.</span></span>

## <a name="syntax"></a><span data-ttu-id="57b14-105">语法</span><span class="sxs-lookup"><span data-stu-id="57b14-105">Syntax</span></span>

<span data-ttu-id="57b14-106">*表达式*。必填</span><span class="sxs-lookup"><span data-stu-id="57b14-106">*expression* .Required</span></span>

<span data-ttu-id="57b14-107">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="57b14-107">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="57b14-108">注解</span><span class="sxs-lookup"><span data-stu-id="57b14-108">Remarks</span></span>


> [!NOTE]
> <P><span data-ttu-id="57b14-p101">[!注释] 在您可以为 <STRONG>Index</STRONG> 对象或 <STRONG>Field</STRONG> 对象设置该属性时，请为 <STRONG>Field</STRONG> 对象设置该属性。这是因为需要先检查 <STRONG>Field</STRONG> 对象属性设置的有效性，然后检查 <STRONG>Index</STRONG> 对象属性设置的有效性。</span><span class="sxs-lookup"><span data-stu-id="57b14-p101">When you can set this property for either an <STRONG>Index</STRONG> object or a <STRONG>Field</STRONG> object, set it for the <STRONG>Field</STRONG> object. The validity of the property setting for a <STRONG>Field</STRONG> object is checked before that of an <STRONG>Index</STRONG> object.</span></span></P>



<span data-ttu-id="57b14-111">**Required** 属性的可用性取决于包含 [Fields](fields-collection-dao.md) 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="57b14-111">The availability of the **Required** property depends on the object that contains the [Fields](fields-collection-dao.md) collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="57b14-112">如果 Fields 集合属于</span><span class="sxs-lookup"><span data-stu-id="57b14-112">If the Fields collection belongs to a</span></span></p></th>
<th><p><span data-ttu-id="57b14-113">则 Required</span><span class="sxs-lookup"><span data-stu-id="57b14-113">Then Required is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57b14-114"><strong>Index</strong> 对象</span><span class="sxs-lookup"><span data-stu-id="57b14-114"><strong>Index</strong> object</span></span></p></td>
<td><p><span data-ttu-id="57b14-115">不支持</span><span class="sxs-lookup"><span data-stu-id="57b14-115">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57b14-116"><strong>QueryDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="57b14-116"><strong>QueryDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="57b14-117">只读</span><span class="sxs-lookup"><span data-stu-id="57b14-117">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57b14-118"><strong>Recordset</strong>对象</span><span class="sxs-lookup"><span data-stu-id="57b14-118"><strong>Recordset</strong> object</span></span></p></td>
<td><p><span data-ttu-id="57b14-119">只读</span><span class="sxs-lookup"><span data-stu-id="57b14-119">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57b14-120"><strong>Relation</strong>对象</span><span class="sxs-lookup"><span data-stu-id="57b14-120"><strong>Relation</strong> object</span></span></p></td>
<td><p><span data-ttu-id="57b14-121">不支持</span><span class="sxs-lookup"><span data-stu-id="57b14-121">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57b14-122"><strong>TableDef</strong>对象</span><span class="sxs-lookup"><span data-stu-id="57b14-122"><strong>TableDef</strong> object</span></span></p></td>
<td><p><span data-ttu-id="57b14-123">读/写</span><span class="sxs-lookup"><span data-stu-id="57b14-123">Read/write</span></span></p></td>
</tr>
</tbody>
</table>

