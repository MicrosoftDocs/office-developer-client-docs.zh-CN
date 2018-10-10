---
title: DBEngine.Version Property (DAO)
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
ms.openlocfilehash: 3516a25623b6838286969c51f2d9346321f3326e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465734"
---
# <a name="dbengineversion-property-dao"></a><span data-ttu-id="0b609-102">DBEngine.Version Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="0b609-102">DBEngine.Version Property (DAO)</span></span>


<span data-ttu-id="0b609-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0b609-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0b609-p101">返回当前使用的 DAO 版本。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="0b609-p101">Rreturns the version of DAO currently in use. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b609-106">语法</span><span class="sxs-lookup"><span data-stu-id="0b609-106">Syntax</span></span>

<span data-ttu-id="0b609-107">*表达式*。版本</span><span class="sxs-lookup"><span data-stu-id="0b609-107">*expression* .Version</span></span>

<span data-ttu-id="0b609-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="0b609-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b609-109">说明</span><span class="sxs-lookup"><span data-stu-id="0b609-109">Remarks</span></span>

<span data-ttu-id="0b609-p102">该返回值为 String 类型，其计算结果为“major.minor”格式的版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。</span><span class="sxs-lookup"><span data-stu-id="0b609-p102">The return value is a String that evaluates to a version number in the form "major.minor". For example, "3.0". The product version number consists of the version number (3), a period, and the release number (0).</span></span>

