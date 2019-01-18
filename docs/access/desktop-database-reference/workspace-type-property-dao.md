---
title: Workspace.Type 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 89e59280-d2cd-b6a2-16c5-9f14f42fdd99
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197086(v=office.15)
ms:contentKeyID: 48546177
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e698963d60809e8d88c4ff87532fb7b74cff275c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28722681"
---
# <a name="workspacetype-property-dao"></a><span data-ttu-id="bfab2-102">Workspace.Type 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="bfab2-102">Workspace.Type property (DAO)</span></span>


<span data-ttu-id="bfab2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="bfab2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bfab2-p101">设置或返回一个值，该值指示对象的操作类型或数据类型。只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="bfab2-p101">Sets or returns a value that indicates the operational type or data type of an object. Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfab2-106">语法</span><span class="sxs-lookup"><span data-stu-id="bfab2-106">Syntax</span></span>

<span data-ttu-id="bfab2-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="bfab2-107">*expression* .Type</span></span>

<span data-ttu-id="bfab2-108">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="bfab2-108">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfab2-109">注解</span><span class="sxs-lookup"><span data-stu-id="bfab2-109">Remarks</span></span>

<span data-ttu-id="bfab2-110">对于 **Workspace** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="bfab2-110">For a **Workspace** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bfab2-111">常量</span><span class="sxs-lookup"><span data-stu-id="bfab2-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="bfab2-112">Workspace 类型</span><span class="sxs-lookup"><span data-stu-id="bfab2-112">Workspace type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfab2-113"><strong>dbUseJet</strong></span><span class="sxs-lookup"><span data-stu-id="bfab2-113"><strong>dbUseJet</strong></span></span></p></td>
<td><p><span data-ttu-id="bfab2-114"><strong>Workspace</strong> 连接到 Microsoft Access 数据库引擎。</span><span class="sxs-lookup"><span data-stu-id="bfab2-114">The <strong>Workspace</strong> is connected to the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfab2-115"><strong>dbUseODBC</strong></span><span class="sxs-lookup"><span data-stu-id="bfab2-115"><strong>dbUseODBC</strong></span></span></p></td>
<td><p><span data-ttu-id="bfab2-116"><strong>Workspace</strong> 连接到 ODBC 数据源。</span><span class="sxs-lookup"><span data-stu-id="bfab2-116">The <strong>Workspace</strong> is connected to an ODBC data source.</span></span></p></td>
</tr>
</tbody>
</table>

