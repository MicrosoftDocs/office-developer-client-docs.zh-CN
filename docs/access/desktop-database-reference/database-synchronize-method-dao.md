---
title: Database.Synchronize Method (DAO)
TOCTitle: Synchronize Method
ms:assetid: 5e716a4a-2430-8106-5c34-a02dd28bc4f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194659(v=office.15)
ms:contentKeyID: 48545137
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053357
f1_categories:
- Office.Version=v15
ms.openlocfilehash: af280c1fca9465d9d8c02c2496ccc7b74e4d8b5d
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867516"
---
# <a name="databasesynchronize-method-dao"></a><span data-ttu-id="39357-102">Database.Synchronize Method (DAO)</span><span class="sxs-lookup"><span data-stu-id="39357-102">Database.Synchronize Method (DAO)</span></span>


<span data-ttu-id="39357-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="39357-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="39357-p101">同步两个副本。（仅适用于 Microsoft Access 工作区）。</span><span class="sxs-lookup"><span data-stu-id="39357-p101">Synchronizes two replicas. (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="39357-106">语法</span><span class="sxs-lookup"><span data-stu-id="39357-106">Syntax</span></span>

<span data-ttu-id="39357-107">*表达式*。同步 (***DbPathName***， ***ExchangeType***)</span><span class="sxs-lookup"><span data-stu-id="39357-107">*expression* .Synchronize(***DbPathName***, ***ExchangeType***)</span></span>

<span data-ttu-id="39357-108">*表达式*一个代表**Database**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="39357-108">*expression* A variable that represents a **Database** object.</span></span>

### <a name="parameters"></a><span data-ttu-id="39357-109">参数</span><span class="sxs-lookup"><span data-stu-id="39357-109">Parameters</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="39357-110">名称</span><span class="sxs-lookup"><span data-stu-id="39357-110">Name</span></span></p></th>
<th><p><span data-ttu-id="39357-111">必需/可选</span><span class="sxs-lookup"><span data-stu-id="39357-111">Required/Optional</span></span></p></th>
<th><p><span data-ttu-id="39357-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="39357-112">Data Type</span></span></p></th>
<th><p><span data-ttu-id="39357-113">说明</span><span class="sxs-lookup"><span data-stu-id="39357-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="39357-114">DbPathName</span><span class="sxs-lookup"><span data-stu-id="39357-114">DbPathName</span></span></p></td>
<td><p><span data-ttu-id="39357-115">必需</span><span class="sxs-lookup"><span data-stu-id="39357-115">Required</span></span></p></td>
<td><p><span data-ttu-id="39357-116"><strong>字符串</strong></span><span class="sxs-lookup"><span data-stu-id="39357-116"><strong>String</strong></span></span></p></td>
<td><p><span data-ttu-id="39357-117">指向数据库将与其同步的目标副本的路径。</span><span class="sxs-lookup"><span data-stu-id="39357-117">The path to the target replica with which database will be synchronized.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="39357-118">ExchangeType</span><span class="sxs-lookup"><span data-stu-id="39357-118">ExchangeType</span></span></p></td>
<td><p><span data-ttu-id="39357-119">可选</span><span class="sxs-lookup"><span data-stu-id="39357-119">Optional</span></span></p></td>
<td><p><span data-ttu-id="39357-120"><strong>Variant</strong></span><span class="sxs-lookup"><span data-stu-id="39357-120"><strong>Variant</strong></span></span></p></td>
<td><p><span data-ttu-id="39357-121">一个 <strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong> 常量，指示朝哪个方向同步两个数据库之间的更改。</span><span class="sxs-lookup"><span data-stu-id="39357-121">A <strong><a href="synchronizetypeenum-enumeration-dao.md">SynchronizeTypeEnum</a></strong> constant indicating which direction to synchronize changes between the two databases.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="39357-122">注解</span><span class="sxs-lookup"><span data-stu-id="39357-122">Remarks</span></span>

<span data-ttu-id="39357-123">可以使用 **Synchronize** 交换两个数据库之间的数据和设计更改。</span><span class="sxs-lookup"><span data-stu-id="39357-123">You use **Synchronize** to exchange data and design changes between two databases.</span></span> <span data-ttu-id="39357-124">始终先发生设计更改。</span><span class="sxs-lookup"><span data-stu-id="39357-124">Design changes always happen first.</span></span> <span data-ttu-id="39357-125">要交换数据，两个数据库必须在相同的设计级别。</span><span class="sxs-lookup"><span data-stu-id="39357-125">Both databases must be at the same design level before they can exchange data.</span></span> <span data-ttu-id="39357-126">例如，即使数据更改流只会从数据库为 DbPathName 类型**dbRepExportChanges** exchange 可能会导致在副本的设计更改。</span><span class="sxs-lookup"><span data-stu-id="39357-126">For example, an exchange of type **dbRepExportChanges** might cause design changes at a replica even though data changes flow only from the database to DbPathName.</span></span>

<span data-ttu-id="39357-127">DbPathName 中标识的副本必须是同一副本集中的一部分。</span><span class="sxs-lookup"><span data-stu-id="39357-127">The replica identified in DbPathName must be part of the same replica set.</span></span> <span data-ttu-id="39357-128">如果两个副本具有相同的 **ReplicaID** 属性设置或者是两个不同副本集的设计母版，则同步失败。</span><span class="sxs-lookup"><span data-stu-id="39357-128">If both replicas have the same **ReplicaID** property setting or are Design Masters for two different replica sets, the synchronization fails.</span></span>

<span data-ttu-id="39357-129">通过 Internet 同步两个副本时，必须使用 **dbRepSyncInternet** 常量。</span><span class="sxs-lookup"><span data-stu-id="39357-129">When you synchronize two replicas over the Internet, you must use the **dbRepSyncInternet** constant.</span></span> <span data-ttu-id="39357-130">在这种情况下，您指定为 DbPathName 参数而不是指定的本地网络路径的统一资源定位器 (URL) 地址。</span><span class="sxs-lookup"><span data-stu-id="39357-130">In this case, you specify a Uniform Resource Locator (URL) address for the DbPathName argument instead of specifying a local area network path.</span></span>


> [!NOTE]
> <span data-ttu-id="39357-p105">[!注释] 不能将部分副本与其他部分副本同步。有关详细信息，请参阅 [PopulatePartial](database-populatepartial-method-dao.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="39357-p105">You can't synchronize partial replicas with other partial replicas. See the [PopulatePartial](database-populatepartial-method-dao.md) method for more information.</span></span>


