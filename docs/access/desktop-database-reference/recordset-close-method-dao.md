---
title: Recordset.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: e76a81c6-ca0d-e310-c1dc-cbc5d6f6248b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836011(v=office.15)
ms:contentKeyID: 48548404
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b4b008676e9c2836238d146a55a472b8ee0590c3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884266"
---
# <a name="recordsetclose-method-dao"></a><span data-ttu-id="d24f9-102">Recordset.Close Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="d24f9-102">Recordset.Close Method (DAO)</span></span>


<span data-ttu-id="d24f9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d24f9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d24f9-104">关闭已打开的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="d24f9-104">Closes an open **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="d24f9-105">语法</span><span class="sxs-lookup"><span data-stu-id="d24f9-105">Syntax</span></span>

<span data-ttu-id="d24f9-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="d24f9-106">*expression* .Close</span></span>

<span data-ttu-id="d24f9-107">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="d24f9-107">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="d24f9-108">注解</span><span class="sxs-lookup"><span data-stu-id="d24f9-108">Remarks</span></span>

<span data-ttu-id="d24f9-109">如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="d24f9-109">If the **Recordset** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="d24f9-p101">如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="d24f9-p101">If you try to close a **Connection** object while it has any open **Recordset** objects, the **Recordset** objects will be closed and any pending updates or edits will be canceled. Similarly, if you try to close a **Workspace** object while it has any open **Connection** objects, those **Connection** objects will be closed, which will close their **Recordset** objects.</span></span>

<span data-ttu-id="d24f9-112">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="d24f9-112">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

