---
title: Connection.Close 方法 (DAO)
TOCTitle: Close Method
ms:assetid: 9b1a77cb-da12-24d6-892f-a56be103d51d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198015(v=office.15)
ms:contentKeyID: 48546559
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bf99abf97a2eb1b88e7056a36c160eb774959719
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28717214"
---
# <a name="connectionclose-method-dao"></a><span data-ttu-id="22975-102">Connection.Close 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="22975-102">Connection.Close method (DAO)</span></span>


<span data-ttu-id="22975-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="22975-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="22975-104">关闭已打开的 **Connection**。</span><span class="sxs-lookup"><span data-stu-id="22975-104">Closes an open **Connection**.</span></span>

## <a name="syntax"></a><span data-ttu-id="22975-105">语法</span><span class="sxs-lookup"><span data-stu-id="22975-105">Syntax</span></span>

<span data-ttu-id="22975-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="22975-106">*expression* .Close</span></span>

<span data-ttu-id="22975-107">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="22975-107">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="22975-108">注解</span><span class="sxs-lookup"><span data-stu-id="22975-108">Remarks</span></span>

<span data-ttu-id="22975-109">如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="22975-109">If the **Recordset** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="22975-p101">如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="22975-p101">If you try to close a **Connection** object while it has any open **Recordset** objects, the **Recordset** objects will be closed and any pending updates or edits will be canceled. Similarly, if you try to close a **Workspace** object while it has any open **Connection** objects, those **Connection** objects will be closed, which will close their **Recordset** objects.</span></span>

<span data-ttu-id="22975-112">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="22975-112">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

