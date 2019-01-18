---
title: RowPosition 属性 (ADO)
TOCTitle: RowPosition property (ADO)
ms:assetid: b87f14b0-136b-0564-3e12-f9d5ecc4f7c8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249887(v=office.15)
ms:contentKeyID: 48547325
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 84d3ad7cc5b3d43b15ac1113f6fa00932678ebc3
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720959"
---
# <a name="rowposition-property-ado"></a><span data-ttu-id="3d8df-102">RowPosition 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3d8df-102">RowPosition property (ADO)</span></span>

<span data-ttu-id="3d8df-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3d8df-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3d8df-104">通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **RowPosition** 对象。</span><span class="sxs-lookup"><span data-stu-id="3d8df-104">Gets or sets an OLE DB **RowPosition** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="3d8df-105">当您使用**放置\_RowPosition**设置**RowPosition**对象，生成的**Recordset**对象使用**RowPosition**对象来确定当前行。</span><span class="sxs-lookup"><span data-stu-id="3d8df-105">When you use **put\_RowPosition** to set the **RowPosition** object, the resulting **Recordset** object uses the **RowPosition** object to determine the current row.</span></span>

<span data-ttu-id="3d8df-106">读/写。</span><span class="sxs-lookup"><span data-stu-id="3d8df-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="3d8df-107">语法</span><span class="sxs-lookup"><span data-stu-id="3d8df-107">Syntax</span></span>

<span data-ttu-id="3d8df-108">HRESULT get\_RowPosition (\[out，retval\] IUnknown\* \* ppRowPos);</span><span class="sxs-lookup"><span data-stu-id="3d8df-108">HRESULT get\_RowPosition(\[out, retval\] IUnknown\*\* ppRowPos);</span></span>

<span data-ttu-id="3d8df-109">HRESULT 放置\_RowPosition (\[的\]IUnknown\* pRowPos);</span><span class="sxs-lookup"><span data-stu-id="3d8df-109">HRESULT put\_RowPosition(\[in\] IUnknown\* pRowPos);</span></span>

## <a name="parameters"></a><span data-ttu-id="3d8df-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="3d8df-110">Parameters</span></span>

|<span data-ttu-id="3d8df-111">参数</span><span class="sxs-lookup"><span data-stu-id="3d8df-111">Parameter</span></span>|<span data-ttu-id="3d8df-112">说明</span><span class="sxs-lookup"><span data-stu-id="3d8df-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="3d8df-113">*ppRowPos*</span><span class="sxs-lookup"><span data-stu-id="3d8df-113">*ppRowPos*</span></span> |<span data-ttu-id="3d8df-114">指向 OLE DB **RowPosition** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="3d8df-114">Pointer to an OLE DB **RowPosition** object.</span></span>|
|<span data-ttu-id="3d8df-115">*PRowPos*</span><span class="sxs-lookup"><span data-stu-id="3d8df-115">*PRowPos*</span></span> |<span data-ttu-id="3d8df-116">一个 OLE DB **RowPosition** 对象。</span><span class="sxs-lookup"><span data-stu-id="3d8df-116">An OLE DB **RowPosition** object.</span></span>|

## <a name="return-values"></a><span data-ttu-id="3d8df-117">返回值</span><span class="sxs-lookup"><span data-stu-id="3d8df-117">Return values</span></span>

<span data-ttu-id="3d8df-118">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="3d8df-118">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d8df-119">备注</span><span class="sxs-lookup"><span data-stu-id="3d8df-119">Remarks</span></span>

<span data-ttu-id="3d8df-p102">设置此属性时，如果 **RowPosition** 对象上的 **Rowset** 对象与 **Recordset** 对象上的 **Rowset** 对象不同，则前者将覆盖后者。 **RowPosition** 的当前 **Chapter** 也是如此。</span><span class="sxs-lookup"><span data-stu-id="3d8df-p102">When this property is set, if the **Rowset** object on the **RowPosition** object is different from the **Rowset** object on the **Recordset** object, the former overrides the latter. The same behavior applies to the current **Chapter** of the **RowPosition** as well.</span></span>

## <a name="applies-to"></a><span data-ttu-id="3d8df-122">适用于</span><span class="sxs-lookup"><span data-stu-id="3d8df-122">Applies to</span></span>

[<span data-ttu-id="3d8df-123">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="3d8df-123">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

