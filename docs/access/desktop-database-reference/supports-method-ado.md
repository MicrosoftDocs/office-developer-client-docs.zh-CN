---
title: Supports 方法 (ADO)
TOCTitle: Supports Method (ADO)
ms:assetid: 2b4062ce-44df-4e84-1ce9-d6618c10c2af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249059(v=office.15)
ms:contentKeyID: 48543924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ceeab22cda05738fdcec090acb5b4a2d6fc88a5b
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25604258"
---
# <a name="supports-method-ado"></a><span data-ttu-id="67862-102">Supports 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="67862-102">Supports Method (ADO)</span></span>


<span data-ttu-id="67862-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="67862-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="67862-104">用于确定指定的 [Recordset](recordset-object-ado.md) 对象是否支持特定类型的功能。</span><span class="sxs-lookup"><span data-stu-id="67862-104">Determines whether a specified [Recordset](recordset-object-ado.md) object supports a particular type of functionality.</span></span>

## <a name="syntax"></a><span data-ttu-id="67862-105">语法</span><span class="sxs-lookup"><span data-stu-id="67862-105">Syntax</span></span>

<span data-ttu-id="67862-106">*boolean* = *recordset*。支持 (*CursorOptions*)</span><span class="sxs-lookup"><span data-stu-id="67862-106">*boolean* = *recordset*.Supports (*CursorOptions*)</span></span>

<span data-ttu-id="67862-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="67862-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="67862-108">返回值</span><span class="sxs-lookup"><span data-stu-id="67862-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="67862-109">返回值</span><span class="sxs-lookup"><span data-stu-id="67862-109">Return value</span></span>
>>>>>>> <span data-ttu-id="67862-110">master</span><span class="sxs-lookup"><span data-stu-id="67862-110">master</span></span>

<span data-ttu-id="67862-111">返回一个**Boolean**值，指示是否*CursorOptions*参数标识的功能的所有支持的提供程序。</span><span class="sxs-lookup"><span data-stu-id="67862-111">Returns a **Boolean** value that indicates whether all of the features identified by the *CursorOptions* argument are supported by the provider.</span></span>

## <a name="parameters"></a><span data-ttu-id="67862-112">参数</span><span class="sxs-lookup"><span data-stu-id="67862-112">Parameters</span></span>

  - <span data-ttu-id="67862-113">*CursorOptions*</span><span class="sxs-lookup"><span data-stu-id="67862-113">*CursorOptions*</span></span>

  - <span data-ttu-id="67862-114">**长整型** 表达式，由一个或多个 [CursorOptionEnum](cursoroptionenum.md) 值组成。</span><span class="sxs-lookup"><span data-stu-id="67862-114">A **Long** expression that consists of one or more [CursorOptionEnum](cursoroptionenum.md) values.</span></span>

## <a name="remarks"></a><span data-ttu-id="67862-115">备注</span><span class="sxs-lookup"><span data-stu-id="67862-115">Remarks</span></span>

<span data-ttu-id="67862-p101">使用 **Supports** 方法可确定 **Recordset** 对象所支持的功能类型。如果 **Recordset** 对象支持与 *CursorOptions* 中的常量相对应的功能，则 **Supports** 方法会返回 **True**，否则返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="67862-p101">Use the **Supports** method to determine what types of functionality a **Recordset** object supports. If the **Recordset** object supports the features whose corresponding constants are in *CursorOptions*, the **Supports** method returns **True**. Otherwise, it returns **False**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="67862-p102">[!注释] 尽管针对给定功能 <STRONG>Supports</STRONG> 方法可能返回 <STRONG>True</STRONG> ，但这并不保证提供程序在所有情况下都支持该功能。 <STRONG>Supports</STRONG> 方法只是返回一个值来说明在特定条件满足时提供程序是否可以支持指定的功能。例如，即使游标基于多个表联接，其中某些列无法更新， <STRONG>Supports</STRONG> 方法也可能指示 <STRONG>Recordset</STRONG> 对象支持更新。</span><span class="sxs-lookup"><span data-stu-id="67862-p102">Although the <STRONG>Supports</STRONG> method may return <STRONG>True</STRONG> for a given functionality, it does not guarantee that the provider can make the feature available under all circumstances. The <STRONG>Supports</STRONG> method simply returns whether the provider can support the specified functionality, assuming certain conditions are met. For example, the <STRONG>Supports</STRONG> method may indicate that a <STRONG>Recordset</STRONG> object supports updates even though the cursor is based on a multiple table join, some columns of which are not updatable.</span></span></P>


