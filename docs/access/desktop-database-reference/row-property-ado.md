---
title: 行属性-ActiveX 数据对象 (ADO)
TOCTitle: Row property (ADO)
ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15)
ms:contentKeyID: 48543562
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9b4beaa742bfc46ecd32fc04733c3e6ddaf12aa2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306480"
---
# <a name="row-property-ado"></a><span data-ttu-id="b68b6-102">Row 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="b68b6-102">Row property (ADO)</span></span>

<span data-ttu-id="b68b6-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="b68b6-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b68b6-104">获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="b68b6-104">Gets or sets an OLE DB **Row** object from/on an **ADORecordConstruction** object.</span></span> <span data-ttu-id="b68b6-105">当您使用 **"\_放置行**" 设置**row**对象时, 会将行转换为 ADO **Record**对象。</span><span class="sxs-lookup"><span data-stu-id="b68b6-105">When you use **put\_Row** to set a **Row** object, a row is turned into an ADO **Record** object.</span></span> <span data-ttu-id="b68b6-106">读/写。</span><span class="sxs-lookup"><span data-stu-id="b68b6-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="b68b6-107">语法</span><span class="sxs-lookup"><span data-stu-id="b68b6-107">Syntax</span></span>

<span data-ttu-id="b68b6-108">HRESULT get\_行 (\[out、retval\] IUnknown\* \* ppRow);</span><span class="sxs-lookup"><span data-stu-id="b68b6-108">HRESULT get\_Row(\[out, retval\] IUnknown\*\* ppRow);</span></span>

<span data-ttu-id="b68b6-109">HRESULT put\_行 (\[在\] IUnknown\* pRow 中);</span><span class="sxs-lookup"><span data-stu-id="b68b6-109">HRESULT put\_Row(\[in\] IUnknown\* pRow);</span></span>

## <a name="parameters"></a><span data-ttu-id="b68b6-110">参数</span><span class="sxs-lookup"><span data-stu-id="b68b6-110">Parameters</span></span>

|<span data-ttu-id="b68b6-111">参数</span><span class="sxs-lookup"><span data-stu-id="b68b6-111">Parameter</span></span>|<span data-ttu-id="b68b6-112">描述</span><span class="sxs-lookup"><span data-stu-id="b68b6-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="b68b6-113">*ppRow*</span><span class="sxs-lookup"><span data-stu-id="b68b6-113">*ppRow*</span></span> |<span data-ttu-id="b68b6-114">指向 OLE DB **Row** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b68b6-114">Pointer to an OLE DB **Row** object.</span></span>|
|<span data-ttu-id="b68b6-115">*PRow*</span><span class="sxs-lookup"><span data-stu-id="b68b6-115">*PRow*</span></span> |<span data-ttu-id="b68b6-116">一个 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="b68b6-116">An OLE DB **Row** object.</span></span>|

## <a name="return-values"></a><span data-ttu-id="b68b6-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b68b6-117">Return values</span></span>

<span data-ttu-id="b68b6-118">此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。</span><span class="sxs-lookup"><span data-stu-id="b68b6-118">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="b68b6-119">适用于</span><span class="sxs-lookup"><span data-stu-id="b68b6-119">Applies to</span></span>

[<span data-ttu-id="b68b6-120">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="b68b6-120">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

