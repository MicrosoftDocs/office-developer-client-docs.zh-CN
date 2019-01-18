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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718299"
---
# <a name="indexname-property-dao"></a><span data-ttu-id="cea9b-102">Index.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="cea9b-102">Index.Name property (DAO)</span></span>


<span data-ttu-id="cea9b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cea9b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cea9b-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="cea9b-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="cea9b-107">语法</span><span class="sxs-lookup"><span data-stu-id="cea9b-107">Syntax</span></span>

<span data-ttu-id="cea9b-108">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="cea9b-108">*expression* .Name</span></span>

<span data-ttu-id="cea9b-109">*表达式*一个代表**Index**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cea9b-109">*expression* A variable that represents an **Index** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cea9b-110">注解</span><span class="sxs-lookup"><span data-stu-id="cea9b-110">Remarks</span></span>

<span data-ttu-id="cea9b-111">**Index** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="cea9b-111">The maximum length for the name of a **Index** object is 64 characters.</span></span>

