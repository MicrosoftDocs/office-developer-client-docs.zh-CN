---
title: CancelUpdate 方法 (RDS)
TOCTitle: CancelUpdate Method (RDS)
ms:assetid: 373a3feb-125d-915a-fd56-d4b04b20db54
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249130(v=office.15)
ms:contentKeyID: 48544188
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ea646f2412ec078f3a45334ec2b1cdbe449285b6
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466794"
---
# <a name="cancelupdate-method-rds"></a><span data-ttu-id="cabac-102">CancelUpdate 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="cabac-102">CancelUpdate Method (RDS)</span></span>


<span data-ttu-id="cabac-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cabac-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="cabac-104">用于取消对 [Recordset](recordset-object-ado.md) 对象的当前行或新行所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="cabac-104">Cancels any changes made to the current or new row of a [Recordset](recordset-object-ado.md) object.</span></span>

## <a name="syntax"></a><span data-ttu-id="cabac-105">语法</span><span class="sxs-lookup"><span data-stu-id="cabac-105">Syntax</span></span>

<span data-ttu-id="cabac-106">*DataControl*。CancelUpdate</span><span class="sxs-lookup"><span data-stu-id="cabac-106">*DataControl*.CancelUpdate</span></span>

## <a name="parameters"></a><span data-ttu-id="cabac-107">参数</span><span class="sxs-lookup"><span data-stu-id="cabac-107">Parameters</span></span>

  - <span data-ttu-id="cabac-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="cabac-108">*DataControl*</span></span>

  - <span data-ttu-id="cabac-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="cabac-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cabac-110">备注</span><span class="sxs-lookup"><span data-stu-id="cabac-110">Remarks</span></span>

<span data-ttu-id="cabac-p101">Cursor Service for OLE DB 同时保留原始值的副本和所做更改的缓存。在调用 **CancelUpdate** 时，所做更改的缓存会重置为空，且任何绑定控件都用原始数据进行刷新。</span><span class="sxs-lookup"><span data-stu-id="cabac-p101">The Cursor Service for OLE DB keeps both a copy of the original values and a cache of changes. When you call **CancelUpdate**, the cache of changes is reset to empty, and any bound controls are refreshed with the original data.</span></span>

