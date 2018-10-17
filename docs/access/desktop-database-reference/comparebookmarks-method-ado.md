---
title: CompareBookmarks 方法 (ADO)
TOCTitle: CompareBookmarks Method (ADO)
ms:assetid: 826cb3c7-2f5c-284f-421d-6b7b07f14dec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249564(v=office.15)
ms:contentKeyID: 48545977
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd6949c74e27cfb961b2a8731030b0af3b14ceb8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466126"
---
# <a name="comparebookmarks-method-ado"></a><span data-ttu-id="dcf37-102">CompareBookmarks 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="dcf37-102">CompareBookmarks Method (ADO)</span></span>


<span data-ttu-id="dcf37-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="dcf37-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="dcf37-104">用于比较两个书签，并返回其相对值的指示。</span><span class="sxs-lookup"><span data-stu-id="dcf37-104">Compares two bookmarks and returns an indication of their relative values.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcf37-105">语法</span><span class="sxs-lookup"><span data-stu-id="dcf37-105">Syntax</span></span>

<span data-ttu-id="dcf37-106">*结果* = *recordset*。CompareBookmarks （*Bookmark1*、 *Bookmark2*）</span><span class="sxs-lookup"><span data-stu-id="dcf37-106">*result* = *recordset*.CompareBookmarks(*Bookmark1*, *Bookmark2*)</span></span>

## <a name="return-value"></a><span data-ttu-id="dcf37-107">返回值</span><span class="sxs-lookup"><span data-stu-id="dcf37-107">Return Value</span></span>

<span data-ttu-id="dcf37-108">返回一个 [CompareEnum](compareenum.md) 值，指示用书签所表示的两个记录的行相对位置。</span><span class="sxs-lookup"><span data-stu-id="dcf37-108">Returns a [CompareEnum](compareenum.md) value that indicates the relative row position of two records represented by their bookmarks.</span></span>

## <a name="parameters"></a><span data-ttu-id="dcf37-109">参数</span><span class="sxs-lookup"><span data-stu-id="dcf37-109">Parameters</span></span>

  - <span data-ttu-id="dcf37-110">*Bookmark1*</span><span class="sxs-lookup"><span data-stu-id="dcf37-110">*Bookmark1*</span></span>

  - <span data-ttu-id="dcf37-111">第一行的书签。</span><span class="sxs-lookup"><span data-stu-id="dcf37-111">The bookmark of the first row.</span></span>

  - <span data-ttu-id="dcf37-112">*Bookmark2*</span><span class="sxs-lookup"><span data-stu-id="dcf37-112">*Bookmark2*</span></span>

  - <span data-ttu-id="dcf37-113">第二行的书签。</span><span class="sxs-lookup"><span data-stu-id="dcf37-113">The bookmark of the second row.</span></span>

## <a name="remarks"></a><span data-ttu-id="dcf37-114">备注</span><span class="sxs-lookup"><span data-stu-id="dcf37-114">Remarks</span></span>

<span data-ttu-id="dcf37-p101">书签必须应用于相同的 [Recordset](recordset-object-ado.md) 对象，或 **Recordset** 对象及其 [克隆](clone-method-ado.md)。来自不同 **Recordset** 对象的书签无法进行可靠地比较，即使书签创建自相同的源或命令。如果 **Recordset** 对象的基础提供程序不支持比较，则其书签也无法进行比较。</span><span class="sxs-lookup"><span data-stu-id="dcf37-p101">The bookmarks must apply to the same [Recordset](recordset-object-ado.md) object, or a **Recordset** object and its [clone](clone-method-ado.md). You cannot reliably compare bookmarks from different **Recordset** objects, even if they were created from the same source or command. Nor can you compare bookmarks for a **Recordset** object whose underlying provider does not support comparisons.</span></span>

<span data-ttu-id="dcf37-p102">书签唯一标识 **Recordset** 对象中的行。使用当前行的 [Bookmark](bookmark-property-ado.md) 属性可以获取其书签。</span><span class="sxs-lookup"><span data-stu-id="dcf37-p102">A bookmark uniquely identifies a row in a **Recordset** object. Use the current row's [Bookmark](bookmark-property-ado.md) property to obtain its bookmark.</span></span>

<span data-ttu-id="dcf37-120">由于书签的数据类型取决于提供程序，ADO 将其公开为变量型。</span><span class="sxs-lookup"><span data-stu-id="dcf37-120">Because the data type of a bookmark is provider specific, ADO exposes it as a Variant.</span></span> <span data-ttu-id="dcf37-121">例如，SQL Server 书签是类型 DBTYPE 的\_R8 (Double)。</span><span class="sxs-lookup"><span data-stu-id="dcf37-121">For example, SQL Server bookmarks are of type DBTYPE\_R8 (Double).</span></span> <span data-ttu-id="dcf37-122">ADO 将此类型公开为具双精度子类型的变量型。</span><span class="sxs-lookup"><span data-stu-id="dcf37-122">ADO would expose this type as a Variant with a subtype of Double.</span></span>

<span data-ttu-id="dcf37-p104">在比较书签时，ADO 不会尝试进行任何类型的强制转换。只是在进行比较的地方将值传递给提供程序。如果传递给 **CompareBookmarks** 方法的书签存储在不同类型的变量中，则将产生类型不匹配错误："Arguments are of the wrong type, are out of the acceptable range, or are in conflict with each other"。</span><span class="sxs-lookup"><span data-stu-id="dcf37-p104">When comparing bookmarks, ADO does not attempt any type of coercion. The values are simply passed to the provider where the compare occurs. If bookmarks passed to the **CompareBookmarks** method are stored in variables of differing types, it can generate the type mismatch error, "Arguments are of the wrong type, are out of the acceptable range, or are in conflict with each other."</span></span>

<span data-ttu-id="dcf37-126">无效的书签或格式不正确的书签将引发错误。</span><span class="sxs-lookup"><span data-stu-id="dcf37-126">A bookmark that is not valid or incorrectly formed will cause an error.</span></span>
