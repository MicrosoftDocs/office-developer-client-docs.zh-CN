---
title: QueryDef.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: b2b63462-453d-9e2b-0bb3-69a4a7a6ecef
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822031(v=office.15)
ms:contentKeyID: 48547179
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052976
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 874e4148bc23130a7b7cd952f8ea008c41f26ca5
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868572"
---
# <a name="querydefclose-method-dao"></a><span data-ttu-id="c5e0d-102">QueryDef.Close Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="c5e0d-102">QueryDef.Close Method (DAO)</span></span>


<span data-ttu-id="c5e0d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5e0d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c5e0d-104">关闭已打开的 **QueryDef**。</span><span class="sxs-lookup"><span data-stu-id="c5e0d-104">Closes an open **QueryDef**.</span></span>

## <a name="syntax"></a><span data-ttu-id="c5e0d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c5e0d-105">Syntax</span></span>

<span data-ttu-id="c5e0d-106">*表达式*。关闭</span><span class="sxs-lookup"><span data-stu-id="c5e0d-106">*expression* .Close</span></span>

<span data-ttu-id="c5e0d-107">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="c5e0d-107">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5e0d-108">注解</span><span class="sxs-lookup"><span data-stu-id="c5e0d-108">Remarks</span></span>

<span data-ttu-id="c5e0d-109">如果在使用 **Close** 时 **QueryDef** 对象已关闭，将发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="c5e0d-109">If the **QueryDef** object is already closed when you use **Close**, a run-time error occurs.</span></span>

<span data-ttu-id="c5e0d-110">**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。</span><span class="sxs-lookup"><span data-stu-id="c5e0d-110">An alternative to the **Close** method is to set the value of an object variable to **Nothing** (Set dbsTemp = Nothing).</span></span>

