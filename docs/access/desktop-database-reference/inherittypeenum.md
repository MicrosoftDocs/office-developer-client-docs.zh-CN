---
title: InheritTypeEnum (Access desktop database reference)
TOCTitle: InheritTypeEnum
ms:assetid: aa505c66-5871-10a8-35a7-cb30bb5dc21a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249787(v=office.15)
ms:contentKeyID: 48546944
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ba1a78e49d44bce0c489e4f5259ec9699543e231
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291412"
---
# <a name="inherittypeenum"></a><span data-ttu-id="1d67e-102">InheritTypeEnum</span><span class="sxs-lookup"><span data-stu-id="1d67e-102">InheritTypeEnum</span></span>

<span data-ttu-id="1d67e-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="1d67e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1d67e-104">指定对象将如何继承通过 [SetPermissions](setpermissions-method-adox.md) 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="1d67e-104">Specifies how objects will inherit permissions set with [SetPermissions](setpermissions-method-adox.md).</span></span>

<br/>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="1d67e-105">常量</span><span class="sxs-lookup"><span data-stu-id="1d67e-105">Constant</span></span></p></th>
<th><p><span data-ttu-id="1d67e-106">值</span><span class="sxs-lookup"><span data-stu-id="1d67e-106">Value</span></span></p></th>
<th><p><span data-ttu-id="1d67e-107">说明</span><span class="sxs-lookup"><span data-stu-id="1d67e-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d67e-108"><strong>adInheritBoth</strong></span><span class="sxs-lookup"><span data-stu-id="1d67e-108"><strong>adInheritBoth</strong></span></span></p></td>
<td><p><span data-ttu-id="1d67e-109">第三章</span><span class="sxs-lookup"><span data-stu-id="1d67e-109">3</span></span></p></td>
<td><p><span data-ttu-id="1d67e-110">主对象包含的对象和其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="1d67e-110">Both objects and other containers contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d67e-111"><strong>adInheritContainers</strong></span><span class="sxs-lookup"><span data-stu-id="1d67e-111"><strong>adInheritContainers</strong></span></span></p></td>
<td><p><span data-ttu-id="1d67e-112">双面</span><span class="sxs-lookup"><span data-stu-id="1d67e-112">2</span></span></p></td>
<td><p><span data-ttu-id="1d67e-113">主对象包含的其他容器继承该项。</span><span class="sxs-lookup"><span data-stu-id="1d67e-113">Other containers that are contained by the primary object inherit the entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d67e-114"><strong>adInheritNone</strong></span><span class="sxs-lookup"><span data-stu-id="1d67e-114"><strong>adInheritNone</strong></span></span></p></td>
<td><p><span data-ttu-id="1d67e-115">0</span><span class="sxs-lookup"><span data-stu-id="1d67e-115">0</span></span></p></td>
<td><p><span data-ttu-id="1d67e-p101">默认值。不发生继承。</span><span class="sxs-lookup"><span data-stu-id="1d67e-p101">Default. No inheritance occurs.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d67e-118"><strong>adInheritNoPropagate</strong></span><span class="sxs-lookup"><span data-stu-id="1d67e-118"><strong>adInheritNoPropagate</strong></span></span></p></td>
<td><p><span data-ttu-id="1d67e-119">4</span><span class="sxs-lookup"><span data-stu-id="1d67e-119">4</span></span></p></td>
<td><p><span data-ttu-id="1d67e-120"><strong>adInheritObjects</strong> 和 <strong>adInheritContainers</strong> 标志不传播到继承的项。</span><span class="sxs-lookup"><span data-stu-id="1d67e-120">The <strong>adInheritObjects</strong> and <strong>adInheritContainers</strong> flags are not propagated to an inherited entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d67e-121"><strong>adInheritObjects</strong></span><span class="sxs-lookup"><span data-stu-id="1d67e-121"><strong>adInheritObjects</strong></span></span></p></td>
<td><p><span data-ttu-id="1d67e-122">1</span><span class="sxs-lookup"><span data-stu-id="1d67e-122">1</span></span></p></td>
<td><p><span data-ttu-id="1d67e-123">容器中的非容器对象继承权限。</span><span class="sxs-lookup"><span data-stu-id="1d67e-123">Non-container objects in the container inherit the permissions.</span></span></p></td>
</tr>
</tbody>
</table>

