---
title: InheritTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: InheritTypeEnum
ms:assetid: aa505c66-5871-10a8-35a7-cb30bb5dc21a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249787(v=office.15)
ms:contentKeyID: 48546944
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: df631319abc1eba06d7ac804b6d8dbdaf5fc9b18
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25888047"
---
# <a name="inherittypeenum"></a><span data-ttu-id="3fca7-102">InheritTypeEnum</span><span class="sxs-lookup"><span data-stu-id="3fca7-102">InheritTypeEnum</span></span>

<span data-ttu-id="3fca7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3fca7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3fca7-104">指定对象将如何继承通过 [SetPermissions](setpermissions-method-adox.md) 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="3fca7-104">Specifies how objects will inherit permissions set with [SetPermissions](setpermissions-method-adox.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="3fca7-105">常量</span><span class="sxs-lookup"><span data-stu-id="3fca7-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="3fca7-106">值</span><span class="sxs-lookup"><span data-stu-id="3fca7-106">Value</span></span></p></th>
<th><p><span data-ttu-id="3fca7-107">说明</span><span class="sxs-lookup"><span data-stu-id="3fca7-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fca7-108"><strong>adInheritBoth</strong></span><span class="sxs-lookup"><span data-stu-id="3fca7-108"><strong>adInheritBoth</strong></span></span></p></td>
<td><p><span data-ttu-id="3fca7-109">3</span><span class="sxs-lookup"><span data-stu-id="3fca7-109">3</span></span></p></td>
<td><p><span data-ttu-id="3fca7-110">主对象包含的对象和其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="3fca7-110">Both objects and other containers contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fca7-111"><strong>adInheritContainers</strong></span><span class="sxs-lookup"><span data-stu-id="3fca7-111"><strong>adInheritContainers</strong></span></span></p></td>
<td><p><span data-ttu-id="3fca7-112">2</span><span class="sxs-lookup"><span data-stu-id="3fca7-112">2</span></span></p></td>
<td><p><span data-ttu-id="3fca7-113">主对象包含的其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="3fca7-113">Other containers that are contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fca7-114"><strong>adInheritNone</strong></span><span class="sxs-lookup"><span data-stu-id="3fca7-114"><strong>adInheritNone</strong></span></span></p></td>
<td><p><span data-ttu-id="3fca7-115">0</span><span class="sxs-lookup"><span data-stu-id="3fca7-115">0</span></span></p></td>
<td><p><span data-ttu-id="3fca7-p101">默认值。不发生继承。</span><span class="sxs-lookup"><span data-stu-id="3fca7-p101">Default. No inheritance occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fca7-118"><strong>adInheritNoPropagate</strong></span><span class="sxs-lookup"><span data-stu-id="3fca7-118"><strong>adInheritNoPropagate</strong></span></span></p></td>
<td><p><span data-ttu-id="3fca7-119">4</span><span class="sxs-lookup"><span data-stu-id="3fca7-119">4</span></span></p></td>
<td><p><span data-ttu-id="3fca7-120"><strong>adInheritObjects</strong> 和 <strong>adInheritContainers</strong> 标志不传播到继承的项。</span><span class="sxs-lookup"><span data-stu-id="3fca7-120">The <strong>adInheritObjects</strong> and <strong>adInheritContainers</strong> flags are not propagated to an inherited entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fca7-121"><strong>adInheritObjects</strong></span><span class="sxs-lookup"><span data-stu-id="3fca7-121"><strong>adInheritObjects</strong></span></span></p></td>
<td><p><span data-ttu-id="3fca7-122">1</span><span class="sxs-lookup"><span data-stu-id="3fca7-122">1</span></span></p></td>
<td><p><span data-ttu-id="3fca7-123">容器中的非容器对象继承权限。</span><span class="sxs-lookup"><span data-stu-id="3fca7-123">Non-container objects in the container inherit the permissions.</span></span></p></td>
</tr>
</tbody>
</table>

