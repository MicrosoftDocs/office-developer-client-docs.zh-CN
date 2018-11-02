---
title: GetString 方法 (ADO)
TOCTitle: GetString method (ADO)
ms:assetid: f496305e-a1f5-7014-7808-7e4961e5f0fa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250242(v=office.15)
ms:contentKeyID: 48548693
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2c6524c52ad3c4821d5b7987415f8a9c2dcb1b1d
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919022"
---
# <a name="getstring-method-ado"></a><span data-ttu-id="e7758-102">GetString 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="e7758-102">GetString method (ADO)</span></span>


<span data-ttu-id="e7758-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e7758-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="e7758-104">将 [Recordset](recordset-object-ado.md) 作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="e7758-104">Returns the [Recordset](recordset-object-ado.md) as a string.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7758-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7758-105">Syntax</span></span>

<span data-ttu-id="e7758-106">*Variant* = *recordset*。GetString （*StringFormat*、 *NumRows*、 *ColumnDelimiter*、 *RowDelimiter*、 *NullExpr*）</span><span class="sxs-lookup"><span data-stu-id="e7758-106">*Variant* = *recordset*.GetString(*StringFormat*, *NumRows*, *ColumnDelimiter*, *RowDelimiter*, *NullExpr*)</span></span>

## <a name="return-value"></a><span data-ttu-id="e7758-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e7758-107">Return value</span></span>

<span data-ttu-id="e7758-108">将 **Recordset** 作为值为字符串的 **变量型** (BSTR) 返回。</span><span class="sxs-lookup"><span data-stu-id="e7758-108">Returns the **Recordset** as a string-valued **Variant** (BSTR).</span></span>

## <a name="parameters"></a><span data-ttu-id="e7758-109">参数</span><span class="sxs-lookup"><span data-stu-id="e7758-109">Parameters</span></span>

  - <span data-ttu-id="e7758-110">*StringFormat*</span><span class="sxs-lookup"><span data-stu-id="e7758-110">*StringFormat*</span></span>

  - <span data-ttu-id="e7758-p101">[StringFormatEnum](stringformatenum.md) 值，指定应如何将 **Recordset** 转换为字符串。*RowDelimiter*、*ColumnDelimiter* 和 *NullExpr* 参数仅与 **adClipString** 的 *StringFormat* 一起使用。</span><span class="sxs-lookup"><span data-stu-id="e7758-p101">A [StringFormatEnum](stringformatenum.md) value that specifies how the **Recordset** should be converted to a string. The *RowDelimiter*, *ColumnDelimiter*, and *NullExpr* parameters are used only with a *StringFormat* of **adClipString**.</span></span>

  - <span data-ttu-id="e7758-113">*NumRows*</span><span class="sxs-lookup"><span data-stu-id="e7758-113">*NumRows*</span></span>

  - <span data-ttu-id="e7758-114">可选。</span><span class="sxs-lookup"><span data-stu-id="e7758-114">Optional.</span></span> <span data-ttu-id="e7758-115">**Recordset** 中要转换的行数。</span><span class="sxs-lookup"><span data-stu-id="e7758-115">The number of rows to be converted in the **Recordset**.</span></span> <span data-ttu-id="e7758-116">如果未指定*NumRows* ，或者大于**Recordset**中的行的总数，会转换**Recordset**中的所有行。</span><span class="sxs-lookup"><span data-stu-id="e7758-116">If *NumRows* is not specified, or if it is greater than the total number of rows in the **Recordset**, then all the rows in the **Recordset** are converted.</span></span>

  - <span data-ttu-id="e7758-117">*ColumnDelimiter*</span><span class="sxs-lookup"><span data-stu-id="e7758-117">*ColumnDelimiter*</span></span>

  - <span data-ttu-id="e7758-p103">可选。如果指定，则在列之间使用的分隔符，否则为 TAB 字符。</span><span class="sxs-lookup"><span data-stu-id="e7758-p103">Optional. A delimiter used between columns, if specified, otherwise the TAB character.</span></span>

  - <span data-ttu-id="e7758-120">*RowDelimiter*</span><span class="sxs-lookup"><span data-stu-id="e7758-120">*RowDelimiter*</span></span>

  - <span data-ttu-id="e7758-p104">可选。如果指定，则在行之间使用的分隔符，否则为 CARRIAGE RETURN 字符。</span><span class="sxs-lookup"><span data-stu-id="e7758-p104">Optional. A delimiter used between rows, if specified, otherwise the CARRIAGE RETURN character.</span></span>

  - <span data-ttu-id="e7758-123">*NullExpr*</span><span class="sxs-lookup"><span data-stu-id="e7758-123">*NullExpr*</span></span>

  - <span data-ttu-id="e7758-p105">可选。如果指定，则用表达式替代 Null 值，否则为空字符串。</span><span class="sxs-lookup"><span data-stu-id="e7758-p105">Optional. An expression used in place of a null value, if specified, otherwise the empty string.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7758-126">备注</span><span class="sxs-lookup"><span data-stu-id="e7758-126">Remarks</span></span>

<span data-ttu-id="e7758-p106">保存到字符串的是行数据，而不是架构数据。因此，不能使用该字符串重新打开 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="e7758-p106">Row data, but no schema data, is saved to the string. Therefore, a **Recordset** cannot be reopened using this string.</span></span>

<span data-ttu-id="e7758-129">此方法等效于 RDO 的 **GetClipString** 方法。</span><span class="sxs-lookup"><span data-stu-id="e7758-129">This method is equivalent to the RDO **GetClipString** method.</span></span>

