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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28715002"
---
# <a name="row-property-ado"></a><span data-ttu-id="31910-102">Row 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="31910-102">Row property (ADO)</span></span>

<span data-ttu-id="31910-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="31910-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="31910-104">获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="31910-104">Gets or sets an OLE DB **Row** object from/on an **ADORecordConstruction** object.</span></span> <span data-ttu-id="31910-105">当您使用**放置\_行**设置**Row**对象，行转换为 ADO **Record**对象。</span><span class="sxs-lookup"><span data-stu-id="31910-105">When you use **put\_Row** to set a **Row** object, a row is turned into an ADO **Record** object.</span></span> <span data-ttu-id="31910-106">读/写。</span><span class="sxs-lookup"><span data-stu-id="31910-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="31910-107">语法</span><span class="sxs-lookup"><span data-stu-id="31910-107">Syntax</span></span>

<span data-ttu-id="31910-108">HRESULT get\_行 (\[out，retval\] IUnknown\* \* ppRow);</span><span class="sxs-lookup"><span data-stu-id="31910-108">HRESULT get\_Row(\[out, retval\] IUnknown\*\* ppRow);</span></span>

<span data-ttu-id="31910-109">HRESULT 放置\_行 (\[的\]IUnknown\* pRow);</span><span class="sxs-lookup"><span data-stu-id="31910-109">HRESULT put\_Row(\[in\] IUnknown\* pRow);</span></span>

## <a name="parameters"></a><span data-ttu-id="31910-110">Parameters</span><span class="sxs-lookup"><span data-stu-id="31910-110">Parameters</span></span>

|<span data-ttu-id="31910-111">参数</span><span class="sxs-lookup"><span data-stu-id="31910-111">Parameter</span></span>|<span data-ttu-id="31910-112">说明</span><span class="sxs-lookup"><span data-stu-id="31910-112">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="31910-113">*ppRow*</span><span class="sxs-lookup"><span data-stu-id="31910-113">*ppRow*</span></span> |<span data-ttu-id="31910-114">指向 OLE DB **Row** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="31910-114">Pointer to an OLE DB **Row** object.</span></span>|
|<span data-ttu-id="31910-115">*PRow*</span><span class="sxs-lookup"><span data-stu-id="31910-115">*PRow*</span></span> |<span data-ttu-id="31910-116">一个 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="31910-116">An OLE DB **Row** object.</span></span>|

## <a name="return-values"></a><span data-ttu-id="31910-117">返回值</span><span class="sxs-lookup"><span data-stu-id="31910-117">Return values</span></span>

<span data-ttu-id="31910-118">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="31910-118">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="31910-119">适用于</span><span class="sxs-lookup"><span data-stu-id="31910-119">Applies to</span></span>

[<span data-ttu-id="31910-120">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="31910-120">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

