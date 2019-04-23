---
title: ActionEnum (Access desktop database reference)
TOCTitle: ActionEnum
ms:assetid: 225024c1-9088-b532-2a23-04c1aaaaa892
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248998(v=office.15)
ms:contentKeyID: 48543704
ms.date: 10/17/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f098adb42df39d1509a6d22decd8d2cead684f11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280654"
---
# <a name="actionenum"></a><span data-ttu-id="ba8a9-102">ActionEnum</span><span class="sxs-lookup"><span data-stu-id="ba8a9-102">ActionEnum</span></span>

<span data-ttu-id="ba8a9-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba8a9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ba8a9-104">指定调用 [SetPermissions](setpermissions-method-adox.md) 时要执行的操作的类型。</span><span class="sxs-lookup"><span data-stu-id="ba8a9-104">Specifies the type of action to be performed when [SetPermissions](setpermissions-method-adox.md) is called.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ba8a9-105">常量</span><span class="sxs-lookup"><span data-stu-id="ba8a9-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="ba8a9-106">值</span><span class="sxs-lookup"><span data-stu-id="ba8a9-106">Value</span></span></p></th>
<th><p><span data-ttu-id="ba8a9-107">说明</span><span class="sxs-lookup"><span data-stu-id="ba8a9-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba8a9-108"><strong>adAccessDeny</strong></span><span class="sxs-lookup"><span data-stu-id="ba8a9-108"><strong>adAccessDeny</strong></span></span></p></td>
<td><p><span data-ttu-id="ba8a9-109">第三章</span><span class="sxs-lookup"><span data-stu-id="ba8a9-109">3</span></span></p></td>
<td><p><span data-ttu-id="ba8a9-110">将拒绝组或用户的指定权限。</span><span class="sxs-lookup"><span data-stu-id="ba8a9-110">The group or user will be denied the specified permissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba8a9-111"><strong>adAccessGrant</strong></span><span class="sxs-lookup"><span data-stu-id="ba8a9-111"><strong>adAccessGrant</strong></span></span></p></td>
<td><p><span data-ttu-id="ba8a9-112">1</span><span class="sxs-lookup"><span data-stu-id="ba8a9-112">1</span></span></p></td>
<td><p><span data-ttu-id="ba8a9-113">组或用户将至少拥有所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="ba8a9-113">The group or user will have at least the requested permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba8a9-114"><strong>adAccessRevoke</strong></span><span class="sxs-lookup"><span data-stu-id="ba8a9-114"><strong>adAccessRevoke</strong></span></span></p></td>
<td><p><span data-ttu-id="ba8a9-115">4</span><span class="sxs-lookup"><span data-stu-id="ba8a9-115">4</span></span></p></td>
<td><p><span data-ttu-id="ba8a9-116">将撤消组或用户所拥有的任何显式访问权限。</span><span class="sxs-lookup"><span data-stu-id="ba8a9-116">Any explicit access rights the group or user has will be revoked.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba8a9-117"><strong>adAccessSet</strong></span><span class="sxs-lookup"><span data-stu-id="ba8a9-117"><strong>adAccessSet</strong></span></span></p></td>
<td><p><span data-ttu-id="ba8a9-118">双面</span><span class="sxs-lookup"><span data-stu-id="ba8a9-118">2</span></span></p></td>
<td><p><span data-ttu-id="ba8a9-119">组或用户将完全拥有所请求的权限。</span><span class="sxs-lookup"><span data-stu-id="ba8a9-119">The group or user will have exactly the requested permissions.</span></span></p></td>
</tr>
</tbody>
</table>

