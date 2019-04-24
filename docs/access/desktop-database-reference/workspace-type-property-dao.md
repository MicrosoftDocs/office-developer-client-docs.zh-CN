---
title: Workspace 属性 (DAO)
TOCTitle: Type Property
ms:assetid: 89e59280-d2cd-b6a2-16c5-9f14f42fdd99
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197086(v=office.15)
ms:contentKeyID: 48546177
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e698963d60809e8d88c4ff87532fb7b74cff275c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311303"
---
# <a name="workspacetype-property-dao"></a><span data-ttu-id="713b3-102">Workspace 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="713b3-102">Workspace.Type property (DAO)</span></span>


<span data-ttu-id="713b3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="713b3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="713b3-104">设置或返回一个值，该值指示对象的操作类型或数据类型。</span><span class="sxs-lookup"><span data-stu-id="713b3-104">Sets or returns a value that indicates the operational type or data type of an object.</span></span> <span data-ttu-id="713b3-105">只读 **Integer**。</span><span class="sxs-lookup"><span data-stu-id="713b3-105">Read-only **Integer**.</span></span>

## <a name="syntax"></a><span data-ttu-id="713b3-106">语法</span><span class="sxs-lookup"><span data-stu-id="713b3-106">Syntax</span></span>

<span data-ttu-id="713b3-107">*表达式*。类型</span><span class="sxs-lookup"><span data-stu-id="713b3-107">*expression* .Type</span></span>

<span data-ttu-id="713b3-108">*表达式*一个代表**Workspace**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="713b3-108">*expression* A variable that represents a **Workspace** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="713b3-109">注解</span><span class="sxs-lookup"><span data-stu-id="713b3-109">Remarks</span></span>

<span data-ttu-id="713b3-110">对于 **Workspace** 对象，可能的设置和返回值如下。</span><span class="sxs-lookup"><span data-stu-id="713b3-110">For a **Workspace** object, the possible settings and return values are as follows.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="713b3-111">常量</span><span class="sxs-lookup"><span data-stu-id="713b3-111">Constant</span></span></p></th>
<th><p><span data-ttu-id="713b3-112">Workspace 类型</span><span class="sxs-lookup"><span data-stu-id="713b3-112">Workspace type</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="713b3-113"><strong>dbUseJet</strong></span><span class="sxs-lookup"><span data-stu-id="713b3-113"><strong>dbUseJet</strong></span></span></p></td>
<td><p><span data-ttu-id="713b3-114"><strong>Workspace</strong> 连接到 Microsoft Access 数据库引擎。</span><span class="sxs-lookup"><span data-stu-id="713b3-114">The <strong>Workspace</strong> is connected to the Microsoft Access database engine.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="713b3-115"><strong>dbUseODBC</strong></span><span class="sxs-lookup"><span data-stu-id="713b3-115"><strong>dbUseODBC</strong></span></span></p></td>
<td><p><span data-ttu-id="713b3-116"><strong>Workspace</strong> 连接到 ODBC 数据源。</span><span class="sxs-lookup"><span data-stu-id="713b3-116">The <strong>Workspace</strong> is connected to an ODBC data source.</span></span></p></td>
</tr>
</tbody>
</table>

