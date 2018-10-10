---
title: Document.LastUpdated Property (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 9307ceee-095f-0364-fd5b-905bc523b9c0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197661(v=office.15)
ms:contentKeyID: 48546388
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f8192dc32554b29c9fe024f34f08757cb512aa5b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468776"
---
# <a name="documentlastupdated-property-dao"></a><span data-ttu-id="cfcb4-102">Document.LastUpdated Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="cfcb4-102">Document.LastUpdated Property (DAO)</span></span>


<span data-ttu-id="cfcb4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cfcb4-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="cfcb4-p101">返回对象的最近更改日期和时间。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="cfcb4-p101">Returns the date and time of the most recent change made to an object. Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfcb4-106">语法</span><span class="sxs-lookup"><span data-stu-id="cfcb4-106">Syntax</span></span>

<span data-ttu-id="cfcb4-107">*表达式*。LastUpdated</span><span class="sxs-lookup"><span data-stu-id="cfcb4-107">*expression* .LastUpdated</span></span>

<span data-ttu-id="cfcb4-108">*表达式*一个代表**Document**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="cfcb4-108">*expression* A variable that represents a **Document** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfcb4-109">注解</span><span class="sxs-lookup"><span data-stu-id="cfcb4-109">Remarks</span></span>

<span data-ttu-id="cfcb4-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="cfcb4-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

