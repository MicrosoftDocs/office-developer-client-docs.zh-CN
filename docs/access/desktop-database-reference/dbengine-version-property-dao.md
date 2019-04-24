---
title: DBEngine 属性 (DAO)
TOCTitle: Version Property
ms:assetid: b2807dc1-604f-4423-289a-ff38a3d9f31b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822024(v=office.15)
ms:contentKeyID: 48547171
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052986
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7e22645127f18ad815c398fd38f9ac4615dfadc9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294188"
---
# <a name="dbengineversion-property-dao"></a><span data-ttu-id="73b49-102">DBEngine 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="73b49-102">DBEngine.Version property (DAO)</span></span>


<span data-ttu-id="73b49-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="73b49-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="73b49-104">返回当前使用的 DAO 版本。</span><span class="sxs-lookup"><span data-stu-id="73b49-104">Rreturns the version of DAO currently in use.</span></span> <span data-ttu-id="73b49-105">只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="73b49-105">Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="73b49-106">语法</span><span class="sxs-lookup"><span data-stu-id="73b49-106">Syntax</span></span>

<span data-ttu-id="73b49-107">*表达式*。版本</span><span class="sxs-lookup"><span data-stu-id="73b49-107">*expression* .Version</span></span>

<span data-ttu-id="73b49-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="73b49-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="73b49-109">注解</span><span class="sxs-lookup"><span data-stu-id="73b49-109">Remarks</span></span>

<span data-ttu-id="73b49-110">该返回值为 String 类型，其计算结果为“major.minor”格式的版本号。</span><span class="sxs-lookup"><span data-stu-id="73b49-110">The return value is a String that evaluates to a version number in the form "major.minor".</span></span> <span data-ttu-id="73b49-111">例如，"3.0"。</span><span class="sxs-lookup"><span data-stu-id="73b49-111">For example, "3.0".</span></span> <span data-ttu-id="73b49-112">产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。</span><span class="sxs-lookup"><span data-stu-id="73b49-112">The product version number consists of the version number (3), a period, and the release number (0).</span></span>

