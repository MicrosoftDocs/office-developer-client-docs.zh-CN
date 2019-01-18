---
title: Append 方法（ADOX 组）
TOCTitle: Append method (ADOX Groups)
ms:assetid: c3245a24-55b8-3f3f-1c4a-43a119d84dc8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249954(v=office.15)
ms:contentKeyID: 48547567
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9f0e7731777e3d82e3746c3886bdbddb3e43db66
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709024"
---
# <a name="append-method-adox-groups"></a><span data-ttu-id="d10b1-102">Append 方法（ADOX 组）</span><span class="sxs-lookup"><span data-stu-id="d10b1-102">Append method (ADOX Groups)</span></span>

<span data-ttu-id="d10b1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d10b1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d10b1-104">将新的 [Group](group-object-adox.md) 对象添加到 [Groups](groups-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="d10b1-104">Adds a new [Group](group-object-adox.md) object to the [Groups](groups-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="d10b1-105">语法</span><span class="sxs-lookup"><span data-stu-id="d10b1-105">Syntax</span></span>

<span data-ttu-id="d10b1-106">*组*。追加*组*</span><span class="sxs-lookup"><span data-stu-id="d10b1-106">*Groups*.Append*Group*</span></span>

## <a name="parameters"></a><span data-ttu-id="d10b1-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="d10b1-107">Parameters</span></span>

|<span data-ttu-id="d10b1-108">参数</span><span class="sxs-lookup"><span data-stu-id="d10b1-108">Parameter</span></span>|<span data-ttu-id="d10b1-109">说明</span><span class="sxs-lookup"><span data-stu-id="d10b1-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="d10b1-110">*Group*</span><span class="sxs-lookup"><span data-stu-id="d10b1-110">*Group*</span></span> |<span data-ttu-id="d10b1-111">要追加的 **Group** 对象，或者要创建并追加的组的名称。</span><span class="sxs-lookup"><span data-stu-id="d10b1-111">The **Group** object to append or the name of the group to create and append.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d10b1-112">备注</span><span class="sxs-lookup"><span data-stu-id="d10b1-112">Remarks</span></span>

<span data-ttu-id="d10b1-p101">**Catalog** 的 [Groups](catalog-object-adox.md) 集合表示该目录的所有组帐户。 **User** 的 [Groups](user-object-adox.md) 集合仅表示该用户所属的组。</span><span class="sxs-lookup"><span data-stu-id="d10b1-p101">The **Groups** collection of a [Catalog](catalog-object-adox.md) represents all of the catalog's group accounts. The **Groups** collection for a [User](user-object-adox.md) represents only the group to which the user belongs.</span></span>

<span data-ttu-id="d10b1-115">如果提供程序不支持创建组，则会发生错误。</span><span class="sxs-lookup"><span data-stu-id="d10b1-115">An error will occur if the provider does not support creating groups.</span></span>

> [!NOTE]
> <span data-ttu-id="d10b1-116">[!注释] 在将 **Group** 对象追加到 **User** 对象的 **Groups** 集合之前， **Catalog** 的 [Groups](name-property-adox.md) 集合中必须存在具有与要追加的 **Group** 对象相同 **Name** 的 Group 对象。</span><span class="sxs-lookup"><span data-stu-id="d10b1-116">Before appending a **Group** object to the **Groups** collection of a **User** object, a **Group** object with the same [Name](name-property-adox.md) as the one to be appended must already exist in the **Groups** collection of the **Catalog**.</span></span>


