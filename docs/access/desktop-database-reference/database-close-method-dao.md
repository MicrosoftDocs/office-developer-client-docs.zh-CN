---
title: Database Close 方法 (DAO)
TOCTitle: Close Method
ms:assetid: b777ee92-172a-3342-31fc-76e7361c47fd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822418(v=office.15)
ms:contentKeyID: 48547296
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 190b47b59bd9781553912f91156c74a3fd09c2d5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295021"
---
# <a name="databaseclose-method-dao"></a><span data-ttu-id="e5ed1-102">Database Close 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="e5ed1-102">Database.Close method (DAO)</span></span>


<span data-ttu-id="e5ed1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5ed1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e5ed1-104">关闭已打开的 **Database**。</span><span class="sxs-lookup"><span data-stu-id="e5ed1-104">Closes an open **Database**.</span></span>

## <a name="syntax"></a><span data-ttu-id="e5ed1-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5ed1-105">Syntax</span></span>

<span data-ttu-id="e5ed1-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="e5ed1-106">*expression* .Close</span></span>

<span data-ttu-id="e5ed1-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="e5ed1-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="e5ed1-108">注解</span><span class="sxs-lookup"><span data-stu-id="e5ed1-108">Remarks</span></span>

<span data-ttu-id="e5ed1-109">如果使用 **Close** 时 **Database** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="e5ed1-109">If the **Database** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="e5ed1-110">**Close**方法的替代方法是将对象变量的值设置为**nothing** (set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="e5ed1-110">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

