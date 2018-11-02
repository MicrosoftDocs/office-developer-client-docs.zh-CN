---
title: Recordset.Cancel 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: 89acfbf1-b937-dc19-ada1-6f8f50489147
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197080(v=office.15)
ms:contentKeyID: 48546169
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 81b08472b46ab3a3d35d184e2f8b7be8673f7d1f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927260"
---
# <a name="recordsetcancel-method-dao"></a><span data-ttu-id="3246c-102">Recordset.Cancel 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="3246c-102">Recordset.Cancel method (DAO)</span></span>


<span data-ttu-id="3246c-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3246c-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="3246c-104">语法</span><span class="sxs-lookup"><span data-stu-id="3246c-104">Syntax</span></span>

<span data-ttu-id="3246c-105">*表达式*。取消</span><span class="sxs-lookup"><span data-stu-id="3246c-105">*expression* .Cancel</span></span>

<span data-ttu-id="3246c-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="3246c-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="3246c-107">说明</span><span class="sxs-lookup"><span data-stu-id="3246c-107">Remarks</span></span>

<span data-ttu-id="3246c-108">使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。</span><span class="sxs-lookup"><span data-stu-id="3246c-108">Use the **Cancel** method to terminate execution of an asynchronous **Execute** or **OpenConnection** method call (that is, the method was invoked with the dbRunAsync option).</span></span> <span data-ttu-id="3246c-109">如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="3246c-109">**Cancel** will return a run-time error if dbRunAsync was not used in the method you're trying to terminate.</span></span>

