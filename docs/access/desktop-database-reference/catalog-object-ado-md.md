---
title: Catalog 对象 (ADO MD)
TOCTitle: Catalog Object (ADO MD)
ms:assetid: 708c4082-3589-7f3b-5ea3-f3705f3d3ff1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249445(v=office.15)
ms:contentKeyID: 48545559
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 68af66ad00567e06649df6003eeac482eacd6686
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467320"
---
# <a name="catalog-object-ado-md"></a><span data-ttu-id="a4d41-102">Catalog 对象 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="a4d41-102">Catalog Object (ADO MD)</span></span>


<span data-ttu-id="a4d41-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a4d41-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="a4d41-104">包含特定于多维数据提供程序 (MDP) 的多维架构信息（即，多维数据集和基础维、层次结构、级别和成员）。</span><span class="sxs-lookup"><span data-stu-id="a4d41-104">Contains multidimensional schema information (that is, cubes and underlying dimensions, hierarchies, levels, and members) specific to a multidimensional data provider (MDP).</span></span>

## <a name="remarks"></a><span data-ttu-id="a4d41-105">说明</span><span class="sxs-lookup"><span data-stu-id="a4d41-105">Remarks</span></span>

<span data-ttu-id="a4d41-106">使用 **Catalog** 对象的集合和属性，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a4d41-106">With the collections and properties of a **Catalog** object, you can do the following:</span></span>

  - <span data-ttu-id="a4d41-107">通过将 [ActiveConnection](activeconnection-property-ado-md.md) 属性设置为标准 ADO [Connection](connection-object-ado.md) 对象或有效的连接字符串来打开目录。</span><span class="sxs-lookup"><span data-stu-id="a4d41-107">Open the catalog by setting the [ActiveConnection](activeconnection-property-ado-md.md) property to a standard ADO [Connection](connection-object-ado.md) object or to a valid connection string.</span></span>

  - <span data-ttu-id="a4d41-108">使用 **Name** 属性标识 [Catalog](name-property-ado-md.md) 。</span><span class="sxs-lookup"><span data-stu-id="a4d41-108">Identify the **Catalog** with the [Name](name-property-ado-md.md) property.</span></span>

  - <span data-ttu-id="a4d41-109">使用 [CubeDefs](cubedefs-collection-ado-md.md) 集合遍历目录中的多维数据集。</span><span class="sxs-lookup"><span data-stu-id="a4d41-109">Iterate through the cubes in a catalog using the [CubeDefs](cubedefs-collection-ado-md.md) collection.</span></span>
