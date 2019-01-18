---
title: Recordset.Cancel 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: 89acfbf1-b937-dc19-ada1-6f8f50489147
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197080(v=office.15)
ms:contentKeyID: 48546169
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 102511575770ceb38cf682d5e627fb7e64faa1ff
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716710"
---
# <a name="recordsetcancel-method-dao"></a><span data-ttu-id="fd230-102">Recordset.Cancel 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="fd230-102">Recordset.Cancel method (DAO)</span></span>


<span data-ttu-id="fd230-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="fd230-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="fd230-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd230-104">Syntax</span></span>

<span data-ttu-id="fd230-105">*表达式*。取消</span><span class="sxs-lookup"><span data-stu-id="fd230-105">*expression* .Cancel</span></span>

<span data-ttu-id="fd230-106">*表达式*一个表示**Recordset**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="fd230-106">*expression* A variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd230-107">备注</span><span class="sxs-lookup"><span data-stu-id="fd230-107">Remarks</span></span>

<span data-ttu-id="fd230-108">使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。</span><span class="sxs-lookup"><span data-stu-id="fd230-108">Use the **Cancel** method to terminate execution of an asynchronous **Execute** or **OpenConnection** method call (that is, the method was invoked with the dbRunAsync option).</span></span> <span data-ttu-id="fd230-109">如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="fd230-109">**Cancel** will return a run-time error if dbRunAsync was not used in the method you're trying to terminate.</span></span>

