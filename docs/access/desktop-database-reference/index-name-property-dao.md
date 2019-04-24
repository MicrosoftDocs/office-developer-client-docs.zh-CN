---
title: Index.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 83cb72c8-068a-229d-c95d-ba16567505c5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196754(v=office.15)
ms:contentKeyID: 48546017
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 78bc22e424312f7d834b3a9ba389e3d82210dd6d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291808"
---
# <a name="indexname-property-dao"></a><span data-ttu-id="17db8-102">Index.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="17db8-102">Index.Name property (DAO)</span></span>


<span data-ttu-id="17db8-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="17db8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="17db8-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="17db8-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="17db8-107">语法</span><span class="sxs-lookup"><span data-stu-id="17db8-107">Syntax</span></span>

<span data-ttu-id="17db8-108">*表达式*。别名</span><span class="sxs-lookup"><span data-stu-id="17db8-108">*expression* .Name</span></span>

<span data-ttu-id="17db8-109">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="17db8-109">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="17db8-110">注解</span><span class="sxs-lookup"><span data-stu-id="17db8-110">Remarks</span></span>

<span data-ttu-id="17db8-111">**Index** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="17db8-111">The maximum length for the name of a **Index** object is 64 characters.</span></span>

