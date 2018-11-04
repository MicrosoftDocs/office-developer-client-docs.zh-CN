---
title: Supports 方法 (ADO)
TOCTitle: Supports method (ADO)
ms:assetid: 2b4062ce-44df-4e84-1ce9-d6618c10c2af
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249059(v=office.15)
ms:contentKeyID: 48543924
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4aa04cf3d04b71e0a84279bfc5340e7ee326de48
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949622"
---
# <a name="supports-method-ado"></a><span data-ttu-id="6ae43-102">Supports 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="6ae43-102">Supports method (ADO)</span></span>

<span data-ttu-id="6ae43-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6ae43-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6ae43-104">用于确定指定的 [Recordset](recordset-object-ado.md) 对象是否支持特定类型的功能。</span><span class="sxs-lookup"><span data-stu-id="6ae43-104">Determines whether a specified [Recordset](recordset-object-ado.md) object supports a particular type of functionality.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ae43-105">语法</span><span class="sxs-lookup"><span data-stu-id="6ae43-105">Syntax</span></span>

<span data-ttu-id="6ae43-106">*boolean* = *recordset*。支持 (*CursorOptions*)</span><span class="sxs-lookup"><span data-stu-id="6ae43-106">*boolean* = *recordset*.Supports (*CursorOptions*)</span></span>

## <a name="return-value"></a><span data-ttu-id="6ae43-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6ae43-107">Return value</span></span>

<span data-ttu-id="6ae43-108">返回一个**Boolean**值，指示是否*CursorOptions*参数标识的功能的所有支持的提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ae43-108">Returns a **Boolean** value that indicates whether all of the features identified by the *CursorOptions* argument are supported by the provider.</span></span>

## <a name="parameters"></a><span data-ttu-id="6ae43-109">参数</span><span class="sxs-lookup"><span data-stu-id="6ae43-109">Parameters</span></span>

|<span data-ttu-id="6ae43-110">参数</span><span class="sxs-lookup"><span data-stu-id="6ae43-110">Parameter</span></span>|<span data-ttu-id="6ae43-111">说明</span><span class="sxs-lookup"><span data-stu-id="6ae43-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="6ae43-112">*CursorOptions*</span><span class="sxs-lookup"><span data-stu-id="6ae43-112">*CursorOptions*</span></span> |<span data-ttu-id="6ae43-113">**长整型** 表达式，由一个或多个 [CursorOptionEnum](cursoroptionenum.md) 值组成。</span><span class="sxs-lookup"><span data-stu-id="6ae43-113">A **Long** expression that consists of one or more [CursorOptionEnum](cursoroptionenum.md) values.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ae43-114">备注</span><span class="sxs-lookup"><span data-stu-id="6ae43-114">Remarks</span></span>

<span data-ttu-id="6ae43-p101">使用 **Supports** 方法可确定 **Recordset** 对象所支持的功能类型。如果 **Recordset** 对象支持与 *CursorOptions* 中的常量相对应的功能，则 **Supports** 方法会返回 **True**，否则返回 **False**。</span><span class="sxs-lookup"><span data-stu-id="6ae43-p101">Use the **Supports** method to determine what types of functionality a **Recordset** object supports. If the **Recordset** object supports the features whose corresponding constants are in *CursorOptions*, the **Supports** method returns **True**. Otherwise, it returns **False**.</span></span>


> [!NOTE]
> <span data-ttu-id="6ae43-p102">[!注释] 尽管针对给定功能 **Supports** 方法可能返回 **True** ，但这并不保证提供程序在所有情况下都支持该功能。 **Supports** 方法只是返回一个值来说明在特定条件满足时提供程序是否可以支持指定的功能。例如，即使游标基于多个表联接，其中某些列无法更新， **Supports** 方法也可能指示 **Recordset** 对象支持更新。</span><span class="sxs-lookup"><span data-stu-id="6ae43-p102">Although the **Supports** method may return **True** for a given functionality, it does not guarantee that the provider can make the feature available under all circumstances. The **Supports** method simply returns whether the provider can support the specified functionality, assuming certain conditions are met. For example, the **Supports** method may indicate that a **Recordset** object supports updates even though the cursor is based on a multiple table join, some columns of which are not updatable.</span></span>


