---
title: Close 方法 (ADO MD)
TOCTitle: Close Method (ADO MD)
ms:assetid: 683788b0-0a96-a165-6b49-8d7036850756
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249406(v=office.15)
ms:contentKeyID: 48545382
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 39059a684a2a64574fc270f3fbd3797a00f66b96
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468707"
---
# <a name="close-method-ado-md"></a><span data-ttu-id="e7201-102">Close 方法 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="e7201-102">Close Method (ADO MD)</span></span>


<span data-ttu-id="e7201-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e7201-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e7201-104">关闭打开的单元格集。</span><span class="sxs-lookup"><span data-stu-id="e7201-104">Closes an open cellset.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7201-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7201-105">Syntax</span></span>

<span data-ttu-id="e7201-106">*单元格集*。关闭</span><span class="sxs-lookup"><span data-stu-id="e7201-106">*Cellset*.Close</span></span>

## <a name="remarks"></a><span data-ttu-id="e7201-107">说明</span><span class="sxs-lookup"><span data-stu-id="e7201-107">Remarks</span></span>

<span data-ttu-id="e7201-p101">使用 **Close** 方法关闭 [Cellset](cellset-object-ado-md.md) 对象会释放关联的数据，包括任何相关的 [Cell](cell-object-ado-md.md)、[Axis](axis-object-ado-md.md)、[Position](position-object-ado-md.md) 或 [Member](member-object-ado-md.md) 对象中的数据。关闭 **Cellset** 不会将其从内存中删除；您可以更改其属性设置，以便以后再打开它。若要从内存中完全消除对象，请将对象变量设置为 **Nothing** 。</span><span class="sxs-lookup"><span data-stu-id="e7201-p101">Using the **Close** method to close a [Cellset](cellset-object-ado-md.md) object will release the associated data, including data in any related [Cell](cell-object-ado-md.md), [Axis](axis-object-ado-md.md), [Position](position-object-ado-md.md), or [Member](member-object-ado-md.md) objects. Closing a **Cellset** does not remove it from memory; you can change its property settings and open it again later. To completely eliminate an object from memory, set the object variable to **Nothing**.</span></span>

<span data-ttu-id="e7201-p102">您可在以后使用相同的源字符串或其他源字符串调用 [Open](open-method-ado-md.md) 方法，以重新打开 **Cellset** 。在 **Cellset** 对象关闭后，检索或调用引用基础数据或元数据的任何属性或方法都会生成错误。</span><span class="sxs-lookup"><span data-stu-id="e7201-p102">You can later call the [Open](open-method-ado-md.md) method to reopen the **Cellset** using the same or another source string. While the **Cellset** object is closed, retrieving any properties or calling any methods that reference the underlying data or metadata generates an error.</span></span>

