---
title: DBEngine.Version 属性 (DAO)
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
ms.openlocfilehash: 1723deea7f29c59fb388a11acc5e5ffcced4abe1
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924594"
---
# <a name="dbengineversion-property-dao"></a><span data-ttu-id="bf034-102">DBEngine.Version 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bf034-102">DBEngine.Version property (DAO)</span></span>


<span data-ttu-id="bf034-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bf034-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bf034-p101">返回当前使用的 DAO 版本。只读 **String**。</span><span class="sxs-lookup"><span data-stu-id="bf034-p101">Rreturns the version of DAO currently in use. Read-only **String**.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf034-106">语法</span><span class="sxs-lookup"><span data-stu-id="bf034-106">Syntax</span></span>

<span data-ttu-id="bf034-107">*表达式*。版本</span><span class="sxs-lookup"><span data-stu-id="bf034-107">*expression* .Version</span></span>

<span data-ttu-id="bf034-108">*表达式*一个代表**DBEngine**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bf034-108">*expression* A variable that represents a **DBEngine** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bf034-109">说明</span><span class="sxs-lookup"><span data-stu-id="bf034-109">Remarks</span></span>

<span data-ttu-id="bf034-p102">该返回值为 String 类型，其计算结果为“major.minor”格式的版本号。例如，“3.0”。产品版本号由版本号 (3)、句点和发行版本号 (0) 组成。</span><span class="sxs-lookup"><span data-stu-id="bf034-p102">The return value is a String that evaluates to a version number in the form "major.minor". For example, "3.0". The product version number consists of the version number (3), a period, and the release number (0).</span></span>

