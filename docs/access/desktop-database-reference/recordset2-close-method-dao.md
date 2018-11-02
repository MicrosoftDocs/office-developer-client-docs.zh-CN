---
title: Recordset2.Close 方法 (DAO)
TOCTitle: Close Method
ms:assetid: ef816969-9857-37cf-9562-d5c80d2815ea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836412(v=office.15)
ms:contentKeyID: 48548584
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e0ad367ce37a33bb90eb193266d203450fa9d543
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924692"
---
# <a name="recordset2close-method-dao"></a><span data-ttu-id="bdde2-102">Recordset2.Close 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bdde2-102">Recordset2.Close method (DAO)</span></span>


<span data-ttu-id="bdde2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bdde2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bdde2-104">关闭已打开的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="bdde2-104">Closes an open **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="bdde2-105">语法</span><span class="sxs-lookup"><span data-stu-id="bdde2-105">Syntax</span></span>

<span data-ttu-id="bdde2-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="bdde2-106">*expression* .Close</span></span>

<span data-ttu-id="bdde2-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bdde2-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdde2-108">注解</span><span class="sxs-lookup"><span data-stu-id="bdde2-108">Remarks</span></span>

<span data-ttu-id="bdde2-109">如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="bdde2-109">If the **Recordset** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="bdde2-p101">如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="bdde2-p101">If you try to close a **Connection** object while it has any open **Recordset** objects, the **Recordset** objects will be closed and any pending updates or edits will be canceled. Similarly, if you try to close a **Workspace** object while it has any open **Connection** objects, those **Connection** objects will be closed, which will close their **Recordset** objects.</span></span>

<span data-ttu-id="bdde2-112">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="bdde2-112">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

