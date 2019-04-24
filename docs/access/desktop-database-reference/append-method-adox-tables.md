---
title: Append 方法（ADOX 表）
TOCTitle: Append method (ADOX Tables)
ms:assetid: 9e9fd57c-a856-6179-013f-9f378c3b7df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249726(v=office.15)
ms:contentKeyID: 48546664
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d2bf2479c2a34291f245783ebaecd75ba31d2ac8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32297072"
---
# <a name="append-method-adox-tables"></a><span data-ttu-id="e9e85-102">Append 方法（ADOX 表）</span><span class="sxs-lookup"><span data-stu-id="e9e85-102">Append method (ADOX Tables)</span></span>

<span data-ttu-id="e9e85-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e9e85-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e9e85-104">将新的 [Table](table-object-adox.md) 对象添加到 [Tables](tables-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="e9e85-104">Adds a new [Table](table-object-adox.md) object to the [Tables](tables-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="e9e85-105">语法</span><span class="sxs-lookup"><span data-stu-id="e9e85-105">Syntax</span></span>

<span data-ttu-id="e9e85-106">*表格*。追加*表格*</span><span class="sxs-lookup"><span data-stu-id="e9e85-106">*Tables*.Append*Table*</span></span>

## <a name="parameters"></a><span data-ttu-id="e9e85-107">参数</span><span class="sxs-lookup"><span data-stu-id="e9e85-107">Parameters</span></span>

|<span data-ttu-id="e9e85-108">参数</span><span class="sxs-lookup"><span data-stu-id="e9e85-108">Parameter</span></span>|<span data-ttu-id="e9e85-109">描述</span><span class="sxs-lookup"><span data-stu-id="e9e85-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="e9e85-110">*Table*</span><span class="sxs-lookup"><span data-stu-id="e9e85-110">*Table*</span></span> | <span data-ttu-id="e9e85-111">一个 **Variant** 值，包含对要追加的 **Table** 的引用，或者是要创建并追加的表的名称。</span><span class="sxs-lookup"><span data-stu-id="e9e85-111">A **Variant** value that contains a reference to the **Table** to append or the name of the table to create and append.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e9e85-112">注解</span><span class="sxs-lookup"><span data-stu-id="e9e85-112">Remarks</span></span>

<span data-ttu-id="e9e85-113">如果提供程序不支持创建表，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="e9e85-113">An error will occur if the provider does not support creating tables.</span></span>

