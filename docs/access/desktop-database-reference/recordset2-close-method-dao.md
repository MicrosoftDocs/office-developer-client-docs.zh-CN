---
title: Recordset2.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: ef816969-9857-37cf-9562-d5c80d2815ea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836412(v=office.15)
ms:contentKeyID: 48548584
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f20c10ac6bb6fc313ffecb56b0d2852c3b488c26
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467579"
---
# <a name="recordset2close-method-dao"></a><span data-ttu-id="49292-102">Recordset2.Close Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="49292-102">Recordset2.Close Method (DAO)</span></span>


<span data-ttu-id="49292-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="49292-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="49292-104">关闭已打开的 **Recordset**。</span><span class="sxs-lookup"><span data-stu-id="49292-104">Closes an open **Recordset**.</span></span>

## <a name="syntax"></a><span data-ttu-id="49292-105">语法</span><span class="sxs-lookup"><span data-stu-id="49292-105">Syntax</span></span>

<span data-ttu-id="49292-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="49292-106">*expression* .Close</span></span>

<span data-ttu-id="49292-107">*表达式*一个表示**Recordset2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="49292-107">*expression* A variable that represents a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="49292-108">注解</span><span class="sxs-lookup"><span data-stu-id="49292-108">Remarks</span></span>

<span data-ttu-id="49292-109">如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="49292-109">If the **Recordset** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="49292-p101">如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="49292-p101">If you try to close a **Connection** object while it has any open **Recordset** objects, the **Recordset** objects will be closed and any pending updates or edits will be canceled. Similarly, if you try to close a **Workspace** object while it has any open **Connection** objects, those **Connection** objects will be closed, which will close their **Recordset** objects.</span></span>

<span data-ttu-id="49292-112">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="49292-112">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

