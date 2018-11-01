---
title: TableDef.DateCreated Property (DAO)
TOCTitle: DateCreated Property
ms:assetid: fedd28e9-41a4-db7f-9ba9-6ada350d594a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837292(v=office.15)
ms:contentKeyID: 48548947
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2cf97df5d5861a3bb0fdac34ceabc8f732a87d5c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885596"
---
# <a name="tabledefdatecreated-property-dao"></a><span data-ttu-id="30b2d-102">TableDef.DateCreated Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="30b2d-102">TableDef.DateCreated Property (DAO)</span></span>


<span data-ttu-id="30b2d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="30b2d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="30b2d-p101">返回对象的创建日期和时间（仅适用于 Microsoft Access 工作区）。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="30b2d-p101">Returns the date and time that an object was created (Microsoft Access workspaces only). Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="30b2d-106">语法</span><span class="sxs-lookup"><span data-stu-id="30b2d-106">Syntax</span></span>

<span data-ttu-id="30b2d-107">*表达式*。DateCreated</span><span class="sxs-lookup"><span data-stu-id="30b2d-107">*expression* .DateCreated</span></span>

<span data-ttu-id="30b2d-108">*表达式*一个代表**TableDef**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="30b2d-108">*expression* A variable that represents a **TableDef** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="30b2d-109">注解</span><span class="sxs-lookup"><span data-stu-id="30b2d-109">Remarks</span></span>

<span data-ttu-id="30b2d-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="30b2d-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

