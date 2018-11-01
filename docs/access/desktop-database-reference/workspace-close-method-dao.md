---
title: Workspace.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: 9b3d28f9-5cde-0dd9-8a4a-d2efaec5fe5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198027(v=office.15)
ms:contentKeyID: 48546565
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 38f1a7a525a2cf57a98ee3fa015ce29b368aab9b
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884126"
---
# <a name="workspaceclose-method-dao"></a><span data-ttu-id="18262-102">Workspace.Close Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="18262-102">Workspace.Close Method (DAO)</span></span>


<span data-ttu-id="18262-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="18262-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="18262-104">关闭已打开的 **Workspace**。</span><span class="sxs-lookup"><span data-stu-id="18262-104">Closes an open **Workspace**.</span></span>

## <a name="syntax"></a><span data-ttu-id="18262-105">语法</span><span class="sxs-lookup"><span data-stu-id="18262-105">Syntax</span></span>

<span data-ttu-id="18262-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="18262-106">*expression* .Close</span></span>

<span data-ttu-id="18262-107">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="18262-107">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="18262-108">注解</span><span class="sxs-lookup"><span data-stu-id="18262-108">Remarks</span></span>

<span data-ttu-id="18262-109">如果在使用 **Close** 时 **Workspace** 对象已关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="18262-109">If the **Workspace** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="18262-110">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="18262-110">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

