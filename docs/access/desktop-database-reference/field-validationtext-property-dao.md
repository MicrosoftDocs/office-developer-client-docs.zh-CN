---
title: Field.ValidationText 属性 (DAO)
TOCTitle: ValidationText Property
ms:assetid: 6d9ec790-a9d2-84d7-ccba-57d738491e36
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195540(v=office.15)
ms:contentKeyID: 48545494
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3244c4e41761095378e3be3ad928effc6444f842
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930404"
---
# <a name="fieldvalidationtext-property-dao"></a><span data-ttu-id="6e61e-102">Field.ValidationText 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6e61e-102">Field.ValidationText property (DAO)</span></span>


<span data-ttu-id="6e61e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6e61e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6e61e-p101">设置或返回一个值，该值指定当 **Field** 对象的值不符合 **ValidationRule** 属性设置所指定的验证规则时应用程序显示的消息文本（仅适用于 Microsoft Access 工作区）。可读写 **String**。</span><span class="sxs-lookup"><span data-stu-id="6e61e-p101">Sets or returns a value that specifies the text of the message that your application displays if the value of a **Field** object doesn't satisfy the validation rule specified by the **ValidationRule** property setting (Microsoft Access workspaces only). Read/write **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e61e-106">语法</span><span class="sxs-lookup"><span data-stu-id="6e61e-106">Syntax</span></span>

<span data-ttu-id="6e61e-107">*表达式*。ValidationText</span><span class="sxs-lookup"><span data-stu-id="6e61e-107">*expression* .ValidationText</span></span>

<span data-ttu-id="6e61e-108">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6e61e-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e61e-109">注解</span><span class="sxs-lookup"><span data-stu-id="6e61e-109">Remarks</span></span>

<span data-ttu-id="6e61e-p102">设置或返回值是一个 **String**，用于指定当用户试图为字段输入无效值时显示的文本。对于尚未追加到集合中的对象，该属性是可读写的。</span><span class="sxs-lookup"><span data-stu-id="6e61e-p102">The setting or return value is a **String** that specifies the text displayed if a user tries to enter an invalid value for a field. For an object not yet appended to a collection, this property is read/write.</span></span>

<span data-ttu-id="6e61e-112">对于 **Field** 对象， **ValidationText** 属性的用法取决于包含 [Field](fields-collection-dao.md) 对象追加到的 \*\*\*\*Fields\*\*\*\* 集合的对象，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="6e61e-112">For a **Field** object, use of the **ValidationText** property depends on the object that contains the **[Fields](fields-collection-dao.md)** collection to which the **Field** object is appended, as the following table shows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6e61e-113">对象追加到</span><span class="sxs-lookup"><span data-stu-id="6e61e-113">Object appended to</span></span></p></th>
<th><p><span data-ttu-id="6e61e-114">用法</span><span class="sxs-lookup"><span data-stu-id="6e61e-114">Usage</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e61e-115"><strong>Index</strong></span><span class="sxs-lookup"><span data-stu-id="6e61e-115"><strong>Index</strong></span></span></p></td>
<td><p><span data-ttu-id="6e61e-116">不支持</span><span class="sxs-lookup"><span data-stu-id="6e61e-116">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e61e-117"><strong>QueryDef</strong></span><span class="sxs-lookup"><span data-stu-id="6e61e-117"><strong>QueryDef</strong></span></span></p></td>
<td><p><span data-ttu-id="6e61e-118">只读</span><span class="sxs-lookup"><span data-stu-id="6e61e-118">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e61e-119"><strong>Recordset</strong></span><span class="sxs-lookup"><span data-stu-id="6e61e-119"><strong>Recordset</strong></span></span></p></td>
<td><p><span data-ttu-id="6e61e-120">只读</span><span class="sxs-lookup"><span data-stu-id="6e61e-120">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e61e-121"><strong>Relation</strong></span><span class="sxs-lookup"><span data-stu-id="6e61e-121"><strong>Relation</strong></span></span></p></td>
<td><p><span data-ttu-id="6e61e-122">不支持</span><span class="sxs-lookup"><span data-stu-id="6e61e-122">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e61e-123"><strong>TableDef</strong></span><span class="sxs-lookup"><span data-stu-id="6e61e-123"><strong>TableDef</strong></span></span></p></td>
<td><p><span data-ttu-id="6e61e-124">读/写</span><span class="sxs-lookup"><span data-stu-id="6e61e-124">Read/write</span></span></p></td>
</tr>
</tbody>
</table>

