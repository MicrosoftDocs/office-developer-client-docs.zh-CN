---
title: Recordset2.Cancel Method (DAO)
TOCTitle: Cancel Method
ms:assetid: cae49f36-3aad-80d8-c15f-a7a584aa2e9b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834366(v=office.15)
ms:contentKeyID: 48547703
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d3b943bed5abdd057b21e8a1380a68231d20e00
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467369"
---
# <a name="recordset2cancel-method-dao"></a><span data-ttu-id="281cb-102">Recordset2.Cancel Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="281cb-102">Recordset2.Cancel Method (DAO)</span></span>


<span data-ttu-id="281cb-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="281cb-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="281cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="281cb-104">Syntax</span></span>

<span data-ttu-id="281cb-105">*表达式*。取消</span><span class="sxs-lookup"><span data-stu-id="281cb-105">*expression* .Cancel</span></span>

<span data-ttu-id="281cb-106">*表达式*一个返回**Recordset2**对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="281cb-106">*expression* An expression that returns a **Recordset2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="281cb-107">说明</span><span class="sxs-lookup"><span data-stu-id="281cb-107">Remarks</span></span>

<span data-ttu-id="281cb-108">使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。</span><span class="sxs-lookup"><span data-stu-id="281cb-108">Use the **Cancel** method to terminate execution of an asynchronous **Execute** or **OpenConnection** method call (that is, the method was invoked with the dbRunAsync option).</span></span> <span data-ttu-id="281cb-109">如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。</span><span class="sxs-lookup"><span data-stu-id="281cb-109">**Cancel** will return a run-time error if dbRunAsync was not used in the method you're trying to terminate.</span></span>

