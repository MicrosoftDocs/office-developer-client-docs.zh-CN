---
title: Append 方法 (ADOX Tables)
TOCTitle: Append Method (ADOX Tables)
ms:assetid: 9e9fd57c-a856-6179-013f-9f378c3b7df0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249726(v=office.15)
ms:contentKeyID: 48546664
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 296ac62c96c547a691244cf28b2ef7fd33da7daa
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466548"
---
# <a name="append-method-adox-tables"></a><span data-ttu-id="07a6d-102">Append 方法 (ADOX Tables)</span><span class="sxs-lookup"><span data-stu-id="07a6d-102">Append Method (ADOX Tables)</span></span>


<span data-ttu-id="07a6d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="07a6d-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="07a6d-104">将新的 [Table](table-object-adox.md) 对象添加到 [Tables](tables-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="07a6d-104">Adds a new [Table](table-object-adox.md) object to the [Tables](tables-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="07a6d-105">语法</span><span class="sxs-lookup"><span data-stu-id="07a6d-105">Syntax</span></span>

<span data-ttu-id="07a6d-106">*表*。追加*表*</span><span class="sxs-lookup"><span data-stu-id="07a6d-106">*Tables*.Append*Table*</span></span>

## <a name="parameters"></a><span data-ttu-id="07a6d-107">参数</span><span class="sxs-lookup"><span data-stu-id="07a6d-107">Parameters</span></span>

  - <span data-ttu-id="07a6d-108">*Table*</span><span class="sxs-lookup"><span data-stu-id="07a6d-108">*Table*</span></span>

  - <span data-ttu-id="07a6d-109">一个 **Variant** 值，包含对要追加的 **Table** 的引用，或者是要创建并追加的表的名称。</span><span class="sxs-lookup"><span data-stu-id="07a6d-109">A **Variant** value that contains a reference to the **Table** to append or the name of the table to create and append.</span></span>

## <a name="remarks"></a><span data-ttu-id="07a6d-110">说明</span><span class="sxs-lookup"><span data-stu-id="07a6d-110">Remarks</span></span>

<span data-ttu-id="07a6d-111">如果提供程序不支持创建表，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="07a6d-111">An error will occur if the provider does not support creating tables.</span></span>

