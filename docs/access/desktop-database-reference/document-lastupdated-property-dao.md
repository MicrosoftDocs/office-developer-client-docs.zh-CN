---
title: Document.LastUpdated Property (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 9307ceee-095f-0364-fd5b-905bc523b9c0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197661(v=office.15)
ms:contentKeyID: 48546388
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ad5a84dcc1765cc90fdfb08adfb6610be7057401
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879646"
---
# <a name="documentlastupdated-property-dao"></a><span data-ttu-id="6b305-102">Document.LastUpdated Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="6b305-102">Document.LastUpdated Property (DAO)</span></span>


<span data-ttu-id="6b305-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6b305-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6b305-p101">返回对象的最近更改日期和时间。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="6b305-p101">Returns the date and time of the most recent change made to an object. Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b305-106">语法</span><span class="sxs-lookup"><span data-stu-id="6b305-106">Syntax</span></span>

<span data-ttu-id="6b305-107">*表达式*。LastUpdated</span><span class="sxs-lookup"><span data-stu-id="6b305-107">*expression* .LastUpdated</span></span>

<span data-ttu-id="6b305-108">*表达式*一个代表**Document**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6b305-108">*expression* A variable that represents a **Document** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b305-109">注解</span><span class="sxs-lookup"><span data-stu-id="6b305-109">Remarks</span></span>

<span data-ttu-id="6b305-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="6b305-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

