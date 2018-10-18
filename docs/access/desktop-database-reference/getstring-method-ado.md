---
title: GetString 方法 (ADO)
TOCTitle: GetString Method (ADO)
ms:assetid: f496305e-a1f5-7014-7808-7e4961e5f0fa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250242(v=office.15)
ms:contentKeyID: 48548693
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ba235094aa7f491cbd86bf753713d50f01009d47
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605399"
---
# <a name="getstring-method-ado"></a><span data-ttu-id="8649c-102">GetString 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8649c-102">GetString Method (ADO)</span></span>


<span data-ttu-id="8649c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8649c-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="8649c-104">将 [Recordset](recordset-object-ado.md) 作为字符串返回。</span><span class="sxs-lookup"><span data-stu-id="8649c-104">Returns the [Recordset](recordset-object-ado.md) as a string.</span></span>

## <a name="syntax"></a><span data-ttu-id="8649c-105">语法</span><span class="sxs-lookup"><span data-stu-id="8649c-105">Syntax</span></span>

<span data-ttu-id="8649c-106">*Variant* = *recordset*。GetString （*StringFormat*、 *NumRows*、 *ColumnDelimiter*、 *RowDelimiter*、 *NullExpr*）</span><span class="sxs-lookup"><span data-stu-id="8649c-106">*Variant* = *recordset*.GetString(*StringFormat*, *NumRows*, *ColumnDelimiter*, *RowDelimiter*, *NullExpr*)</span></span>

<span data-ttu-id="8649c-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="8649c-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="8649c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8649c-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="8649c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8649c-109">Return value</span></span>
>>>>>>> <span data-ttu-id="8649c-110">master</span><span class="sxs-lookup"><span data-stu-id="8649c-110">master</span></span>

<span data-ttu-id="8649c-111">将 **Recordset** 作为值为字符串的 **变量型** (BSTR) 返回。</span><span class="sxs-lookup"><span data-stu-id="8649c-111">Returns the **Recordset** as a string-valued **Variant** (BSTR).</span></span>

## <a name="parameters"></a><span data-ttu-id="8649c-112">参数</span><span class="sxs-lookup"><span data-stu-id="8649c-112">Parameters</span></span>

  - <span data-ttu-id="8649c-113">*StringFormat*</span><span class="sxs-lookup"><span data-stu-id="8649c-113">*StringFormat*</span></span>

  - <span data-ttu-id="8649c-p101">[StringFormatEnum](stringformatenum.md) 值，指定应如何将 **Recordset** 转换为字符串。*RowDelimiter*、*ColumnDelimiter* 和 *NullExpr* 参数仅与 **adClipString** 的 *StringFormat* 一起使用。</span><span class="sxs-lookup"><span data-stu-id="8649c-p101">A [StringFormatEnum](stringformatenum.md) value that specifies how the **Recordset** should be converted to a string. The *RowDelimiter*, *ColumnDelimiter*, and *NullExpr* parameters are used only with a *StringFormat* of **adClipString**.</span></span>

  - <span data-ttu-id="8649c-116">*NumRows*</span><span class="sxs-lookup"><span data-stu-id="8649c-116">*NumRows*</span></span>

  - <span data-ttu-id="8649c-117">可选。</span><span class="sxs-lookup"><span data-stu-id="8649c-117">Optional.</span></span> <span data-ttu-id="8649c-118">**Recordset** 中要转换的行数。</span><span class="sxs-lookup"><span data-stu-id="8649c-118">The number of rows to be converted in the **Recordset**.</span></span> <span data-ttu-id="8649c-119">如果未指定*NumRows* ，或者大于**Recordset**中的行的总数，会转换**Recordset**中的所有行。</span><span class="sxs-lookup"><span data-stu-id="8649c-119">If *NumRows* is not specified, or if it is greater than the total number of rows in the **Recordset**, then all the rows in the **Recordset** are converted.</span></span>

  - <span data-ttu-id="8649c-120">*ColumnDelimiter*</span><span class="sxs-lookup"><span data-stu-id="8649c-120">*ColumnDelimiter*</span></span>

  - <span data-ttu-id="8649c-p103">可选。如果指定，则在列之间使用的分隔符，否则为 TAB 字符。</span><span class="sxs-lookup"><span data-stu-id="8649c-p103">Optional. A delimiter used between columns, if specified, otherwise the TAB character.</span></span>

  - <span data-ttu-id="8649c-123">*RowDelimiter*</span><span class="sxs-lookup"><span data-stu-id="8649c-123">*RowDelimiter*</span></span>

  - <span data-ttu-id="8649c-p104">可选。如果指定，则在行之间使用的分隔符，否则为 CARRIAGE RETURN 字符。</span><span class="sxs-lookup"><span data-stu-id="8649c-p104">Optional. A delimiter used between rows, if specified, otherwise the CARRIAGE RETURN character.</span></span>

  - <span data-ttu-id="8649c-126">*NullExpr*</span><span class="sxs-lookup"><span data-stu-id="8649c-126">*NullExpr*</span></span>

  - <span data-ttu-id="8649c-p105">可选。如果指定，则用表达式替代 Null 值，否则为空字符串。</span><span class="sxs-lookup"><span data-stu-id="8649c-p105">Optional. An expression used in place of a null value, if specified, otherwise the empty string.</span></span>

## <a name="remarks"></a><span data-ttu-id="8649c-129">备注</span><span class="sxs-lookup"><span data-stu-id="8649c-129">Remarks</span></span>

<span data-ttu-id="8649c-p106">保存到字符串的是行数据，而不是架构数据。因此，不能使用该字符串重新打开 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="8649c-p106">Row data, but no schema data, is saved to the string. Therefore, a **Recordset** cannot be reopened using this string.</span></span>

<span data-ttu-id="8649c-132">此方法等效于 RDO 的 **GetClipString** 方法。</span><span class="sxs-lookup"><span data-stu-id="8649c-132">This method is equivalent to the RDO **GetClipString** method.</span></span>

