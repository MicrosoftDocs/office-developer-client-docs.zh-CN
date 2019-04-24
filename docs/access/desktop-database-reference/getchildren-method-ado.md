---
title: GetChildren 方法 (ADO)
TOCTitle: GetChildren method (ADO)
ms:assetid: 998cf640-ffc7-51e1-4d1e-4797f7cdea4a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249687(v=office.15)
ms:contentKeyID: 48546515
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 4ca8c113a377543ea8624972adb5958612a3fc72
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292305"
---
# <a name="getchildren-method-ado"></a><span data-ttu-id="fd87b-102">GetChildren 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="fd87b-102">GetChildren method (ADO)</span></span>


<span data-ttu-id="fd87b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fd87b-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="fd87b-104">用于返回一个 [Recordset](recordset-object-ado.md)，该记录集的行代表 [Record](record-object-ado.md) 集合的子级。</span><span class="sxs-lookup"><span data-stu-id="fd87b-104">Returns a [Recordset](recordset-object-ado.md) whose rows represent the children of a collection [Record](record-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="fd87b-105">语法</span><span class="sxs-lookup"><span data-stu-id="fd87b-105">Syntax</span></span>

<span data-ttu-id="fd87b-106">\**Set\*\*\*recordset* = *记录*。GetChildren</span><span class="sxs-lookup"><span data-stu-id="fd87b-106">**Set** *recordset* = *record*.GetChildren</span></span>

## <a name="return-value"></a><span data-ttu-id="fd87b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="fd87b-107">Return value</span></span>

<span data-ttu-id="fd87b-p101">**Recordset** 对象，其每一行代表当前 **Record** 对象的一个子级。例如，代表目录的 **Record** 的子级应为包含在父目录中的文件和子目录。</span><span class="sxs-lookup"><span data-stu-id="fd87b-p101">A **Recordset** object for which each row represents a child of the current **Record** object. For example, the children of a **Record** that represents a directory would be the files and subdirectories contained within the parent directory.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd87b-110">注解</span><span class="sxs-lookup"><span data-stu-id="fd87b-110">Remarks</span></span>

<span data-ttu-id="fd87b-p102">提供程序确定返回的 **Recordset** 中存在哪些列。例如，文档源提供程序始终返回一个资源 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="fd87b-p102">The provider determines what columns exist in the returned **Recordset**. For example, a document source provider always returns a resource **Recordset**.</span></span>

