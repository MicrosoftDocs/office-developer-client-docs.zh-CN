---
title: Database.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: b777ee92-172a-3342-31fc-76e7361c47fd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822418(v=office.15)
ms:contentKeyID: 48547296
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 97246da6224ee04fa435638a0cb11d1bdac8859f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466242"
---
# <a name="databaseclose-method-dao"></a><span data-ttu-id="aab9e-102">Database.Close Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="aab9e-102">Database.Close Method (DAO)</span></span>


<span data-ttu-id="aab9e-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="aab9e-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="aab9e-104">关闭已打开的 **Database**。</span><span class="sxs-lookup"><span data-stu-id="aab9e-104">Closes an open **Database**.</span></span>

## <a name="syntax"></a><span data-ttu-id="aab9e-105">语法</span><span class="sxs-lookup"><span data-stu-id="aab9e-105">Syntax</span></span>

<span data-ttu-id="aab9e-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="aab9e-106">*expression* .Close</span></span>

<span data-ttu-id="aab9e-107">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="aab9e-107">*expression* A variable that represents a **Database** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="aab9e-108">注解</span><span class="sxs-lookup"><span data-stu-id="aab9e-108">Remarks</span></span>

<span data-ttu-id="aab9e-109">如果使用 **Close** 时 **Database** 对象已被关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="aab9e-109">If the **Database** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="aab9e-110">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="aab9e-110">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

