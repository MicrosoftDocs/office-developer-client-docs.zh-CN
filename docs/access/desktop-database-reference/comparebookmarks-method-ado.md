---
title: CompareBookmarks 方法 (ADO)
TOCTitle: CompareBookmarks Method (ADO)
ms:assetid: 826cb3c7-2f5c-284f-421d-6b7b07f14dec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249564(v=office.15)
ms:contentKeyID: 48545977
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9fc4cf3540d22d3981bb13a7af3251dd625c2c99
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25606246"
---
# <a name="comparebookmarks-method-ado"></a><span data-ttu-id="7b56a-102">CompareBookmarks 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7b56a-102">CompareBookmarks Method (ADO)</span></span>


<span data-ttu-id="7b56a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7b56a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="7b56a-104">用于比较两个书签，并返回其相对值的指示。</span><span class="sxs-lookup"><span data-stu-id="7b56a-104">Compares two bookmarks and returns an indication of their relative values.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b56a-105">语法</span><span class="sxs-lookup"><span data-stu-id="7b56a-105">Syntax</span></span>

<span data-ttu-id="7b56a-106">*结果* = *recordset*。CompareBookmarks （*Bookmark1*、 *Bookmark2*）</span><span class="sxs-lookup"><span data-stu-id="7b56a-106">*result* = *recordset*.CompareBookmarks(*Bookmark1*, *Bookmark2*)</span></span>

<span data-ttu-id="7b56a-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="7b56a-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="7b56a-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7b56a-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="7b56a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7b56a-109">Return value</span></span>
>>>>>>> <span data-ttu-id="7b56a-110">master</span><span class="sxs-lookup"><span data-stu-id="7b56a-110">master</span></span>

<span data-ttu-id="7b56a-111">返回一个 [CompareEnum](compareenum.md) 值，指示用书签所表示的两个记录的行相对位置。</span><span class="sxs-lookup"><span data-stu-id="7b56a-111">Returns a [CompareEnum](compareenum.md) value that indicates the relative row position of two records represented by their bookmarks.</span></span>

## <a name="parameters"></a><span data-ttu-id="7b56a-112">参数</span><span class="sxs-lookup"><span data-stu-id="7b56a-112">Parameters</span></span>

  - <span data-ttu-id="7b56a-113">*Bookmark1*</span><span class="sxs-lookup"><span data-stu-id="7b56a-113">*Bookmark1*</span></span>

  - <span data-ttu-id="7b56a-114">第一行的书签。</span><span class="sxs-lookup"><span data-stu-id="7b56a-114">The bookmark of the first row.</span></span>

  - <span data-ttu-id="7b56a-115">*Bookmark2*</span><span class="sxs-lookup"><span data-stu-id="7b56a-115">*Bookmark2*</span></span>

  - <span data-ttu-id="7b56a-116">第二行的书签。</span><span class="sxs-lookup"><span data-stu-id="7b56a-116">The bookmark of the second row.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b56a-117">备注</span><span class="sxs-lookup"><span data-stu-id="7b56a-117">Remarks</span></span>

<span data-ttu-id="7b56a-p101">书签必须应用于相同的 [Recordset](recordset-object-ado.md) 对象，或 **Recordset** 对象及其 [克隆](clone-method-ado.md)。来自不同 **Recordset** 对象的书签无法进行可靠地比较，即使书签创建自相同的源或命令。如果 **Recordset** 对象的基础提供程序不支持比较，则其书签也无法进行比较。</span><span class="sxs-lookup"><span data-stu-id="7b56a-p101">The bookmarks must apply to the same [Recordset](recordset-object-ado.md) object, or a **Recordset** object and its [clone](clone-method-ado.md). You cannot reliably compare bookmarks from different **Recordset** objects, even if they were created from the same source or command. Nor can you compare bookmarks for a **Recordset** object whose underlying provider does not support comparisons.</span></span>

<span data-ttu-id="7b56a-p102">书签唯一标识 **Recordset** 对象中的行。使用当前行的 [Bookmark](bookmark-property-ado.md) 属性可以获取其书签。</span><span class="sxs-lookup"><span data-stu-id="7b56a-p102">A bookmark uniquely identifies a row in a **Recordset** object. Use the current row's [Bookmark](bookmark-property-ado.md) property to obtain its bookmark.</span></span>

<span data-ttu-id="7b56a-123">由于书签的数据类型取决于提供程序，ADO 将其公开为变量型。</span><span class="sxs-lookup"><span data-stu-id="7b56a-123">Because the data type of a bookmark is provider specific, ADO exposes it as a Variant.</span></span> <span data-ttu-id="7b56a-124">例如，SQL Server 书签是类型 DBTYPE 的\_R8 (Double)。</span><span class="sxs-lookup"><span data-stu-id="7b56a-124">For example, SQL Server bookmarks are of type DBTYPE\_R8 (Double).</span></span> <span data-ttu-id="7b56a-125">ADO 将此类型公开为具双精度子类型的变量型。</span><span class="sxs-lookup"><span data-stu-id="7b56a-125">ADO would expose this type as a Variant with a subtype of Double.</span></span>

<span data-ttu-id="7b56a-p104">在比较书签时，ADO 不会尝试进行任何类型的强制转换。只是在进行比较的地方将值传递给提供程序。如果传递给 **CompareBookmarks** 方法的书签存储在不同类型的变量中，则将产生类型不匹配错误："Arguments are of the wrong type, are out of the acceptable range, or are in conflict with each other"。</span><span class="sxs-lookup"><span data-stu-id="7b56a-p104">When comparing bookmarks, ADO does not attempt any type of coercion. The values are simply passed to the provider where the compare occurs. If bookmarks passed to the **CompareBookmarks** method are stored in variables of differing types, it can generate the type mismatch error, "Arguments are of the wrong type, are out of the acceptable range, or are in conflict with each other."</span></span>

<span data-ttu-id="7b56a-129">无效的书签或格式不正确的书签将引发错误。</span><span class="sxs-lookup"><span data-stu-id="7b56a-129">A bookmark that is not valid or incorrectly formed will cause an error.</span></span>

