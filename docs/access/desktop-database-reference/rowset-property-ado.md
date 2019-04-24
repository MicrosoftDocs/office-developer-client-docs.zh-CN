---
title: Rowset 属性 (ADO)
TOCTitle: Rowset property (ADO)
ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15)
ms:contentKeyID: 48543515
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: be2a4855b3411a11ddd5a76225acaa52344877a4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306739"
---
# <a name="rowset-property-ado"></a><span data-ttu-id="bc261-102">Rowset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="bc261-102">Rowset property (ADO)</span></span>

<span data-ttu-id="bc261-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bc261-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bc261-104">通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc261-104">Gets or sets an OLE DB **Rowset** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="bc261-105">使用 put\_行集时, 行集将转换为 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="bc261-105">When you use put\_Rowset, the rowset is turned into an ADO **Recordset** object.</span></span>

<span data-ttu-id="bc261-106">读/写。</span><span class="sxs-lookup"><span data-stu-id="bc261-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="bc261-107">语法</span><span class="sxs-lookup"><span data-stu-id="bc261-107">Syntax</span></span>

<span data-ttu-id="bc261-108">HRESULT get\_Rowset (\[out, retval\] IUnknown\* \* ppRowset);</span><span class="sxs-lookup"><span data-stu-id="bc261-108">HRESULT get\_Rowset(\[out, retval\] IUnknown\*\* ppRowset);</span></span>

<span data-ttu-id="bc261-109">HRESULT put\_行集\[(\]在\* IUnknown pRowset 中);</span><span class="sxs-lookup"><span data-stu-id="bc261-109">HRESULT put\_Rowset(\[in\] IUnknown\* pRowset);</span></span>

## <a name="parameters"></a><span data-ttu-id="bc261-110">参数</span><span class="sxs-lookup"><span data-stu-id="bc261-110">Parameters</span></span>

|<span data-ttu-id="bc261-111">参数</span><span class="sxs-lookup"><span data-stu-id="bc261-111">Parameter</span></span>|<span data-ttu-id="bc261-112">描述</span><span class="sxs-lookup"><span data-stu-id="bc261-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="bc261-113">*ppRowset*</span><span class="sxs-lookup"><span data-stu-id="bc261-113">*ppRowset*</span></span> |<span data-ttu-id="bc261-114">指向 OLE DB **Rowset** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="bc261-114">Pointer to an OLE DB **Rowset** object.</span></span>|
|<span data-ttu-id="bc261-115">*PRowset*</span><span class="sxs-lookup"><span data-stu-id="bc261-115">*PRowset*</span></span> |<span data-ttu-id="bc261-116">一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="bc261-116">An OLE DB **Rowset** object.</span></span>|

## <a name="return-values"></a><span data-ttu-id="bc261-117">返回值</span><span class="sxs-lookup"><span data-stu-id="bc261-117">Return values</span></span>

<span data-ttu-id="bc261-118">此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。</span><span class="sxs-lookup"><span data-stu-id="bc261-118">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="bc261-119">适用于</span><span class="sxs-lookup"><span data-stu-id="bc261-119">Applies to</span></span>

[<span data-ttu-id="bc261-120">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="bc261-120">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

