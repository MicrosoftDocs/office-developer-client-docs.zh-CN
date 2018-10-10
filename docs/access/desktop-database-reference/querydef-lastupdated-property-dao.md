---
title: QueryDef.LastUpdated Property (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 3b7818d4-054e-54e2-bf63-58b340bb4a90
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192665(v=office.15)
ms:contentKeyID: 48544287
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 37a95cefb5af5070470fb5973076e230d76c3d98
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468923"
---
# <a name="querydeflastupdated-property-dao"></a><span data-ttu-id="f9d9a-102">QueryDef.LastUpdated Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f9d9a-102">QueryDef.LastUpdated Property (DAO)</span></span>


<span data-ttu-id="f9d9a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f9d9a-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="f9d9a-p101">返回对象的最近更改日期和时间。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="f9d9a-p101">Returns the date and time of the most recent change made to an object. Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9d9a-106">语法</span><span class="sxs-lookup"><span data-stu-id="f9d9a-106">Syntax</span></span>

<span data-ttu-id="f9d9a-107">*表达式*。LastUpdated</span><span class="sxs-lookup"><span data-stu-id="f9d9a-107">*expression* .LastUpdated</span></span>

<span data-ttu-id="f9d9a-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f9d9a-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f9d9a-109">注解</span><span class="sxs-lookup"><span data-stu-id="f9d9a-109">Remarks</span></span>

<span data-ttu-id="f9d9a-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="f9d9a-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

