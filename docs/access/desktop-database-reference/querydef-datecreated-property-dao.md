---
title: DateCreated 属性 (DAO)
TOCTitle: DateCreated Property
ms:assetid: f7585b34-8314-fb9f-daa6-cd1a8ad59d91
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836910(v=office.15)
ms:contentKeyID: 48548763
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a4a120eed6c20db73e1c23f31ea9329d00da2f0d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301069"
---
# <a name="querydefdatecreated-property-dao"></a><span data-ttu-id="7145f-102">DateCreated 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="7145f-102">QueryDef.DateCreated property (DAO)</span></span>


<span data-ttu-id="7145f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7145f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7145f-104">返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="7145f-104">Returns the date and time that an object was created (Microsoft Access workspaces only).</span></span> <span data-ttu-id="7145f-105">只读 **Variant** 类型。</span><span class="sxs-lookup"><span data-stu-id="7145f-105">Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="7145f-106">语法</span><span class="sxs-lookup"><span data-stu-id="7145f-106">Syntax</span></span>

<span data-ttu-id="7145f-107">*表达式*。DateCreated</span><span class="sxs-lookup"><span data-stu-id="7145f-107">*expression* .DateCreated</span></span>

<span data-ttu-id="7145f-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="7145f-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7145f-109">注解</span><span class="sxs-lookup"><span data-stu-id="7145f-109">Remarks</span></span>

<span data-ttu-id="7145f-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="7145f-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

