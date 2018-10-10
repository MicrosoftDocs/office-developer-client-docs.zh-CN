---
title: GetChildren 方法 (ADO)
TOCTitle: GetChildren Method (ADO)
ms:assetid: 998cf640-ffc7-51e1-4d1e-4797f7cdea4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249687(v=office.15)
ms:contentKeyID: 48546515
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a11f3e34f8dcb45bab88d8ff87e69067103e4640
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466049"
---
# <a name="getchildren-method-ado"></a><span data-ttu-id="ec5a9-102">GetChildren 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="ec5a9-102">GetChildren Method (ADO)</span></span>


<span data-ttu-id="ec5a9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ec5a9-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="ec5a9-104">用于返回一个 [Recordset](recordset-object-ado.md)，该记录集的行代表 [Record](record-object-ado.md) 集合的子级。</span><span class="sxs-lookup"><span data-stu-id="ec5a9-104">Returns a [Recordset](recordset-object-ado.md) whose rows represent the children of a collection [Record](record-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="ec5a9-105">语法</span><span class="sxs-lookup"><span data-stu-id="ec5a9-105">Syntax</span></span>

<span data-ttu-id="ec5a9-106">\**设置\*\*\*记录集* = *记录*。GetChildren</span><span class="sxs-lookup"><span data-stu-id="ec5a9-106">**Set** *recordset* = *record*.GetChildren</span></span>

## <a name="return-value"></a><span data-ttu-id="ec5a9-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ec5a9-107">Return Value</span></span>

<span data-ttu-id="ec5a9-p101">**Recordset** 对象，其每一行代表当前 **Record** 对象的一个子级。例如，代表目录的 **Record** 的子级应为包含在父目录中的文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="ec5a9-p101">A **Recordset** object for which each row represents a child of the current **Record** object. For example, the children of a **Record** that represents a directory would be the files and subdirectories contained within the parent directory.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec5a9-110">备注</span><span class="sxs-lookup"><span data-stu-id="ec5a9-110">Remarks</span></span>

<span data-ttu-id="ec5a9-p102">提供程序确定返回的 **Recordset** 中存在哪些列。例如，文档源提供程序始终返回一个资源 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="ec5a9-p102">The provider determines what columns exist in the returned **Recordset**. For example, a document source provider always returns a resource **Recordset**.</span></span>

