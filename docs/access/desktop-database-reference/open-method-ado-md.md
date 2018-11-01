---
title: Open 方法 (ADO MD)
TOCTitle: Open Method (ADO MD)
ms:assetid: 12395ff6-fe07-325a-2b69-007aa0b11ee6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248894(v=office.15)
ms:contentKeyID: 48543335
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d9b39fa77700fcd1553738d359b8efd7097c183a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25870273"
---
# <a name="open-method-ado-md"></a><span data-ttu-id="619c4-102">Open 方法 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="619c4-102">Open Method (ADO MD)</span></span>


<span data-ttu-id="619c4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="619c4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="619c4-104">检索多维查询的结果并将结果返回到单元格集。</span><span class="sxs-lookup"><span data-stu-id="619c4-104">Retrieves the results of a multidimensional query and returns the results to a cellset.</span></span>

## <a name="syntax"></a><span data-ttu-id="619c4-105">语法</span><span class="sxs-lookup"><span data-stu-id="619c4-105">Syntax</span></span>

<span data-ttu-id="619c4-106">*单元格集*。打开*源*， *ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="619c4-106">*Cellset*.Open*Source*, *ActiveConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="619c4-107">参数</span><span class="sxs-lookup"><span data-stu-id="619c4-107">Parameters</span></span>

  - <span data-ttu-id="619c4-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="619c4-108">*Source*</span></span>

  - <span data-ttu-id="619c4-109">可选。</span><span class="sxs-lookup"><span data-stu-id="619c4-109">Optional.</span></span> <span data-ttu-id="619c4-110">一个 **Variant** 值，计算后得到有效的多维查询（如多维表达式 (MDX) 查询）。</span><span class="sxs-lookup"><span data-stu-id="619c4-110">A **Variant** that evaluates to a valid multidimensional query, such as a Multidimensional Expression (MDX) query.</span></span> <span data-ttu-id="619c4-111">*源*参数对应于[Source](source-property-ado-md.md)属性。</span><span class="sxs-lookup"><span data-stu-id="619c4-111">The *Source* argument corresponds to the [Source](source-property-ado-md.md) property.</span></span> <span data-ttu-id="619c4-112">有关 MDX 的更多信息，请参阅 Microsoft Data Access Components SDK 中的 OLE DB for OLAP 文档。</span><span class="sxs-lookup"><span data-stu-id="619c4-112">For more information about MDX, see the OLE DB for OLAP documentation in the Microsoft Data Access Components SDK.</span></span>

  - <span data-ttu-id="619c4-113">*ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="619c4-113">*ActiveConnection*</span></span>

  - <span data-ttu-id="619c4-114">可选。</span><span class="sxs-lookup"><span data-stu-id="619c4-114">Optional.</span></span> <span data-ttu-id="619c4-115">一个 **Variant** 值，计算后得到字符串，该字符串指定一个有效的 ADO [Connection](connection-object-ado.md) 对象变量名或一个连接定义。</span><span class="sxs-lookup"><span data-stu-id="619c4-115">A **Variant** that evaluates to a string specifying either a valid ADO [Connection](connection-object-ado.md) object variable name or a definition for a connection.</span></span> <span data-ttu-id="619c4-116">*ActiveConnection*参数指定要在其中打开[Cellset](cellset-object-ado-md.md)对象的连接。</span><span class="sxs-lookup"><span data-stu-id="619c4-116">The *ActiveConnection* argument specifies the connection in which to open the [Cellset](cellset-object-ado-md.md) object.</span></span> <span data-ttu-id="619c4-117">如果传递此参数的连接定义，ADO 将使用指定的参数打开新连接。</span><span class="sxs-lookup"><span data-stu-id="619c4-117">If you pass a connection definition for this argument, ADO opens a new connection using the specified parameters.</span></span> <span data-ttu-id="619c4-118">*ActiveConnection*参数对应于将[ActiveConnection](activeconnection-property-ado-md.md)属性。</span><span class="sxs-lookup"><span data-stu-id="619c4-118">The *ActiveConnection* argument corresponds to the [ActiveConnection](activeconnection-property-ado-md.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="619c4-119">备注</span><span class="sxs-lookup"><span data-stu-id="619c4-119">Remarks</span></span>

<span data-ttu-id="619c4-120">如果省略 **Open** 方法的任一参数，并且在尝试打开 **Cellset** 之前不设置其对应的属性值，则该方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="619c4-120">The **Open** method generates an error if either of its parameters is omitted and its corresponding property value has not been set prior to attempting to open the **Cellset**.</span></span>

