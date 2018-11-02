---
title: Document.LastUpdated 属性 (DAO)
TOCTitle: LastUpdated Property
ms:assetid: 9307ceee-095f-0364-fd5b-905bc523b9c0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197661(v=office.15)
ms:contentKeyID: 48546388
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 57fb558330c602206831c1c72f09a13094eba799
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927310"
---
# <a name="documentlastupdated-property-dao"></a><span data-ttu-id="6c1ff-102">Document.LastUpdated 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="6c1ff-102">Document.LastUpdated property (DAO)</span></span>


<span data-ttu-id="6c1ff-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6c1ff-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6c1ff-p101">返回对象的最近更改日期和时间。只读 **Variant**。</span><span class="sxs-lookup"><span data-stu-id="6c1ff-p101">Returns the date and time of the most recent change made to an object. Read-only **Variant**.</span></span>

## <a name="syntax"></a><span data-ttu-id="6c1ff-106">语法</span><span class="sxs-lookup"><span data-stu-id="6c1ff-106">Syntax</span></span>

<span data-ttu-id="6c1ff-107">*表达式*。LastUpdated</span><span class="sxs-lookup"><span data-stu-id="6c1ff-107">*expression* .LastUpdated</span></span>

<span data-ttu-id="6c1ff-108">*表达式*一个代表**Document**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="6c1ff-108">*expression* A variable that represents a **Document** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c1ff-109">注解</span><span class="sxs-lookup"><span data-stu-id="6c1ff-109">Remarks</span></span>

<span data-ttu-id="6c1ff-p102">**DateCreated** 和 **LastUpdated** 返回创建或上次更新对象的日期和时间。在多用户环境中，用户应当直接从文件服务器获取这些设置，以避免在 DateCreated 和 LastUpdated 属性设置中出现差异。</span><span class="sxs-lookup"><span data-stu-id="6c1ff-p102">**DateCreated** and **LastUpdated** return the date and time that the object was created or last updated. In a multiuser environment, users should get these settings directly from the file server to avoid discrepancies in the DateCreated and LastUpdated property settings.</span></span>

