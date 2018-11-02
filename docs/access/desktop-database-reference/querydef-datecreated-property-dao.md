---
title: QueryDef.DateCreated 属性 (DAO)
TOCTitle: DateCreated Property
ms:assetid: f7585b34-8314-fb9f-daa6-cd1a8ad59d91
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836910(v=office.15)
ms:contentKeyID: 48548763
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3eb3d4664f6fce30812904612f458d24f3a8b159
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927023"
---
# <a name="querydefdatecreated-property-dao"></a><span data-ttu-id="4cc69-102">QueryDef.DateCreated 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="4cc69-102">QueryDef.DateCreated property (DAO)</span></span>


<span data-ttu-id="4cc69-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4cc69-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4cc69-p101">返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="4cc69-p101">Returns the date and time that an object was created (Microsoft Access workspaces only). Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="4cc69-106">语法</span><span class="sxs-lookup"><span data-stu-id="4cc69-106">Syntax</span></span>

<span data-ttu-id="4cc69-107">*表达式*。DateCreated</span><span class="sxs-lookup"><span data-stu-id="4cc69-107">*expression* .DateCreated</span></span>

<span data-ttu-id="4cc69-108">*表达式*一个代表**QueryDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="4cc69-108">*expression* A variable that represents a **QueryDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="4cc69-109">注解</span><span class="sxs-lookup"><span data-stu-id="4cc69-109">Remarks</span></span>

<span data-ttu-id="4cc69-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="4cc69-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

