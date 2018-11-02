---
title: QueryDef.LastUpdated 属性 (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 3b7818d4-054e-54e2-bf63-58b340bb4a90
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192665(v=office.15)
ms:contentKeyID: 48544287
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 98bb600e6f3f1c9587eca110269e8b6b3765e40f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25921269"
---
# <a name="querydeflastupdated-property-dao"></a><span data-ttu-id="4a6ea-102">QueryDef.LastUpdated 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4a6ea-102">QueryDef.LastUpdated property (DAO)</span></span>


<span data-ttu-id="4a6ea-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4a6ea-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4a6ea-p101">返回对象的最近更改日期和时间。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="4a6ea-p101">Returns the date and time of the most recent change made to an object. Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a6ea-106">语法</span><span class="sxs-lookup"><span data-stu-id="4a6ea-106">Syntax</span></span>

<span data-ttu-id="4a6ea-107">*表达式*。LastUpdated</span><span class="sxs-lookup"><span data-stu-id="4a6ea-107">*expression* .LastUpdated</span></span>

<span data-ttu-id="4a6ea-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4a6ea-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a6ea-109">注解</span><span class="sxs-lookup"><span data-stu-id="4a6ea-109">Remarks</span></span>

<span data-ttu-id="4a6ea-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="4a6ea-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

