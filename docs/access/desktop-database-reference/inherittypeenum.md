---
title: InheritTypeEnum （访问桌面数据库参考 （英文）
TOCTitle: InheritTypeEnum
ms:assetid: aa505c66-5871-10a8-35a7-cb30bb5dc21a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249787(v=office.15)
ms:contentKeyID: 48546944
ms.date: 10/18/2018
mtps_version: v=office.15
ms.openlocfilehash: bf7d7ceac1e4822344ce4f7ad8a05e09c0429dff
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25860565"
---
# <a name="inherittypeenum"></a><span data-ttu-id="6fd64-102">InheritTypeEnum</span><span class="sxs-lookup"><span data-stu-id="6fd64-102">InheritTypeEnum</span></span>

<span data-ttu-id="6fd64-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6fd64-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6fd64-104">指定对象将如何继承通过 [SetPermissions](setpermissions-method-adox.md) 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="6fd64-104">Specifies how objects will inherit permissions set with [SetPermissions](setpermissions-method-adox.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6fd64-105">常量</span><span class="sxs-lookup"><span data-stu-id="6fd64-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="6fd64-106">值</span><span class="sxs-lookup"><span data-stu-id="6fd64-106">Value</span></span></p></th>
<th><p><span data-ttu-id="6fd64-107">说明</span><span class="sxs-lookup"><span data-stu-id="6fd64-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6fd64-108"><strong>adInheritBoth</strong></span><span class="sxs-lookup"><span data-stu-id="6fd64-108"><strong>adInheritBoth</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd64-109">3</span><span class="sxs-lookup"><span data-stu-id="6fd64-109">3</span></span></p></td>
<td><p><span data-ttu-id="6fd64-110">主对象包含的对象和其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="6fd64-110">Both objects and other containers contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd64-111"><strong>adInheritContainers</strong></span><span class="sxs-lookup"><span data-stu-id="6fd64-111"><strong>adInheritContainers</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd64-112">2</span><span class="sxs-lookup"><span data-stu-id="6fd64-112">2</span></span></p></td>
<td><p><span data-ttu-id="6fd64-113">主对象包含的其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="6fd64-113">Other containers that are contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd64-114"><strong>adInheritNone</strong></span><span class="sxs-lookup"><span data-stu-id="6fd64-114"><strong>adInheritNone</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd64-115">0</span><span class="sxs-lookup"><span data-stu-id="6fd64-115">0</span></span></p></td>
<td><p><span data-ttu-id="6fd64-p101">默认值。不发生继承。</span><span class="sxs-lookup"><span data-stu-id="6fd64-p101">Default. No inheritance occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6fd64-118"><strong>adInheritNoPropagate</strong></span><span class="sxs-lookup"><span data-stu-id="6fd64-118"><strong>adInheritNoPropagate</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd64-119">4</span><span class="sxs-lookup"><span data-stu-id="6fd64-119">4</span></span></p></td>
<td><p><span data-ttu-id="6fd64-120"><strong>adInheritObjects</strong> 和 <strong>adInheritContainers</strong> 标志不传播到继承的项。</span><span class="sxs-lookup"><span data-stu-id="6fd64-120">The <strong>adInheritObjects</strong> and <strong>adInheritContainers</strong> flags are not propagated to an inherited entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6fd64-121"><strong>adInheritObjects</strong></span><span class="sxs-lookup"><span data-stu-id="6fd64-121"><strong>adInheritObjects</strong></span></span></p></td>
<td><p><span data-ttu-id="6fd64-122">1</span><span class="sxs-lookup"><span data-stu-id="6fd64-122">1</span></span></p></td>
<td><p><span data-ttu-id="6fd64-123">容器中的非容器对象继承权限。</span><span class="sxs-lookup"><span data-stu-id="6fd64-123">Non-container objects in the container inherit the permissions.</span></span></p></td>
</tr>
</tbody>
</table>

