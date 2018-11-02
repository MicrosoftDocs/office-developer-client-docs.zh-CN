---
title: Open 方法 (ADO MD)
TOCTitle: Open method (ADO MD)
ms:assetid: 12395ff6-fe07-325a-2b69-007aa0b11ee6
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248894(v=office.15)
ms:contentKeyID: 48543335
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 98cceed03af8ba939579d1542421b375e0db64a7
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927528"
---
# <a name="open-method-ado-md"></a><span data-ttu-id="18069-102">Open 方法 (ADO MD)</span><span class="sxs-lookup"><span data-stu-id="18069-102">Open method (ADO MD)</span></span>


<span data-ttu-id="18069-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="18069-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="18069-104">检索多维查询的结果并将结果返回到单元格集。</span><span class="sxs-lookup"><span data-stu-id="18069-104">Retrieves the results of a multidimensional query and returns the results to a cellset.</span></span>

## <a name="syntax"></a><span data-ttu-id="18069-105">语法</span><span class="sxs-lookup"><span data-stu-id="18069-105">Syntax</span></span>

<span data-ttu-id="18069-106">*单元格集*。打开*源*， *ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="18069-106">*Cellset*.Open*Source*, *ActiveConnection*</span></span>

## <a name="parameters"></a><span data-ttu-id="18069-107">参数</span><span class="sxs-lookup"><span data-stu-id="18069-107">Parameters</span></span>

  - <span data-ttu-id="18069-108">*Source*</span><span class="sxs-lookup"><span data-stu-id="18069-108">*Source*</span></span>

  - <span data-ttu-id="18069-109">可选。</span><span class="sxs-lookup"><span data-stu-id="18069-109">Optional.</span></span> <span data-ttu-id="18069-110">一个 **Variant** 值，计算后得到有效的多维查询（如多维表达式 (MDX) 查询）。</span><span class="sxs-lookup"><span data-stu-id="18069-110">A **Variant** that evaluates to a valid multidimensional query, such as a Multidimensional Expression (MDX) query.</span></span> <span data-ttu-id="18069-111">*源*参数对应于[Source](source-property-ado-md.md)属性。</span><span class="sxs-lookup"><span data-stu-id="18069-111">The *Source* argument corresponds to the [Source](source-property-ado-md.md) property.</span></span> <span data-ttu-id="18069-112">有关 MDX 的更多信息，请参阅 Microsoft Data Access Components SDK 中的 OLE DB for OLAP 文档。</span><span class="sxs-lookup"><span data-stu-id="18069-112">For more information about MDX, see the OLE DB for OLAP documentation in the Microsoft Data Access Components SDK.</span></span>

  - <span data-ttu-id="18069-113">*ActiveConnection*</span><span class="sxs-lookup"><span data-stu-id="18069-113">*ActiveConnection*</span></span>

  - <span data-ttu-id="18069-114">可选。</span><span class="sxs-lookup"><span data-stu-id="18069-114">Optional.</span></span> <span data-ttu-id="18069-115">一个 **Variant** 值，计算后得到字符串，该字符串指定一个有效的 ADO [Connection](connection-object-ado.md) 对象变量名或一个连接定义。</span><span class="sxs-lookup"><span data-stu-id="18069-115">A **Variant** that evaluates to a string specifying either a valid ADO [Connection](connection-object-ado.md) object variable name or a definition for a connection.</span></span> <span data-ttu-id="18069-116">*ActiveConnection*参数指定要在其中打开[Cellset](cellset-object-ado-md.md)对象的连接。</span><span class="sxs-lookup"><span data-stu-id="18069-116">The *ActiveConnection* argument specifies the connection in which to open the [Cellset](cellset-object-ado-md.md) object.</span></span> <span data-ttu-id="18069-117">如果传递此参数的连接定义，ADO 将使用指定的参数打开新连接。</span><span class="sxs-lookup"><span data-stu-id="18069-117">If you pass a connection definition for this argument, ADO opens a new connection using the specified parameters.</span></span> <span data-ttu-id="18069-118">*ActiveConnection*参数对应于将[ActiveConnection](activeconnection-property-ado-md.md)属性。</span><span class="sxs-lookup"><span data-stu-id="18069-118">The *ActiveConnection* argument corresponds to the [ActiveConnection](activeconnection-property-ado-md.md) property.</span></span>

## <a name="remarks"></a><span data-ttu-id="18069-119">备注</span><span class="sxs-lookup"><span data-stu-id="18069-119">Remarks</span></span>

<span data-ttu-id="18069-120">如果省略 **Open** 方法的任一参数，并且在尝试打开 **Cellset** 之前不设置其对应的属性值，则该方法将生成错误。</span><span class="sxs-lookup"><span data-stu-id="18069-120">The **Open** method generates an error if either of its parameters is omitted and its corresponding property value has not been set prior to attempting to open the **Cellset**.</span></span>

