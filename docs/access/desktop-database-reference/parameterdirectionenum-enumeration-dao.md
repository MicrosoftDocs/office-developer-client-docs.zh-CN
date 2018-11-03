---
title: ParameterDirectionEnum 枚举 (DAO)
TOCTitle: ParameterDirectionEnum Enumeration
ms:assetid: 3f2b91f4-a932-aca5-34a0-4002c27d6b3b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192844(v=office.15)
ms:contentKeyID: 48544389
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bca1a7cc2d01c6664a5200325a93dd242deb6eff
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25944843"
---
# <a name="parameterdirectionenum-enumeration-dao"></a><span data-ttu-id="97f1f-102">ParameterDirectionEnum 枚举 (DAO)</span><span class="sxs-lookup"><span data-stu-id="97f1f-102">ParameterDirectionEnum enumeration (DAO)</span></span>


<span data-ttu-id="97f1f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="97f1f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="97f1f-104">与 **Direction** 属性一起用来指定 **Parameter** 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="97f1f-104">Used with the **Direction** property to specify the type for a **Parameter** object.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="97f1f-105">名称</span><span class="sxs-lookup"><span data-stu-id="97f1f-105">Name</span></span></p></th>
<th><p><span data-ttu-id="97f1f-106">值</span><span class="sxs-lookup"><span data-stu-id="97f1f-106">Value</span></span></p></th>
<th><p><span data-ttu-id="97f1f-107">说明</span><span class="sxs-lookup"><span data-stu-id="97f1f-107">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97f1f-108">dbparaminput 以外</span><span class="sxs-lookup"><span data-stu-id="97f1f-108">dbParamInput</span></span></p></td>
<td><p><span data-ttu-id="97f1f-109">1</span><span class="sxs-lookup"><span data-stu-id="97f1f-109">1</span></span></p></td>
<td><p><span data-ttu-id="97f1f-110">（默认值）将信息传递到过程。</span><span class="sxs-lookup"><span data-stu-id="97f1f-110">(Default) Passes information to the procedure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97f1f-111">dbParamInputOutput</span><span class="sxs-lookup"><span data-stu-id="97f1f-111">dbParamInputOutput</span></span></p></td>
<td><p><span data-ttu-id="97f1f-112">3</span><span class="sxs-lookup"><span data-stu-id="97f1f-112">3</span></span></p></td>
<td><p><span data-ttu-id="97f1f-113">将信息传入和传出过程。</span><span class="sxs-lookup"><span data-stu-id="97f1f-113">Passes information both to and from the procedure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97f1f-114">dbParamOutput</span><span class="sxs-lookup"><span data-stu-id="97f1f-114">dbParamOutput</span></span></p></td>
<td><p><span data-ttu-id="97f1f-115">2</span><span class="sxs-lookup"><span data-stu-id="97f1f-115">2</span></span></p></td>
<td><p><span data-ttu-id="97f1f-116">以 SQL 中输出参数的形式从过程中返回信息。</span><span class="sxs-lookup"><span data-stu-id="97f1f-116">Returns information from the procedure as an output parameter in SQL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97f1f-117">dbParamReturnValue</span><span class="sxs-lookup"><span data-stu-id="97f1f-117">dbParamReturnValue</span></span></p></td>
<td><p><span data-ttu-id="97f1f-118">4</span><span class="sxs-lookup"><span data-stu-id="97f1f-118">4</span></span></p></td>
<td><p><span data-ttu-id="97f1f-119">从过程传递返回值。</span><span class="sxs-lookup"><span data-stu-id="97f1f-119">Passes the return value from a procedure.</span></span></p></td>
</tr>
</tbody>
</table>

