---
title: 行属性-ActiveX 数据对象 (ADO)
TOCTitle: Row Property (ADO)
ms:assetid: 1c2b0e27-7232-4b1c-826c-9dc15d758851
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248959(v=office.15)
ms:contentKeyID: 48543562
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 05d97bb411c4199677f512d9412653ca5a4b4fe1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466955"
---
# <a name="row-property-ado"></a><span data-ttu-id="cb66a-102">Row 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="cb66a-102">Row Property (ADO)</span></span>


<span data-ttu-id="cb66a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="cb66a-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="cb66a-104">获取或设置 **ADORecordConstruction** 对象的 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="cb66a-104">Gets or sets an OLE DB **Row** object from/on an **ADORecordConstruction** object.</span></span> <span data-ttu-id="cb66a-105">当您使用**放置\_行**设置**Row**对象，行转换为 ADO **Record**对象。</span><span class="sxs-lookup"><span data-stu-id="cb66a-105">When you use **put\_Row** to set a **Row** object, a row is turned into an ADO **Record** object.</span></span> <span data-ttu-id="cb66a-106">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="cb66a-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb66a-107">语法</span><span class="sxs-lookup"><span data-stu-id="cb66a-107">Syntax</span></span>

<span data-ttu-id="cb66a-108">HRESULT get\_行 (\[out，retval\] IUnknown\* \* ppRow);</span><span class="sxs-lookup"><span data-stu-id="cb66a-108">HRESULT get\_Row(\[out, retval\] IUnknown\*\* ppRow);</span></span>

<span data-ttu-id="cb66a-109">HRESULT 放置\_行 (\[的\]IUnknown\* pRow);</span><span class="sxs-lookup"><span data-stu-id="cb66a-109">HRESULT put\_Row(\[in\] IUnknown\* pRow);</span></span>

## <a name="parameters"></a><span data-ttu-id="cb66a-110">参数</span><span class="sxs-lookup"><span data-stu-id="cb66a-110">Parameters</span></span>

  - <span data-ttu-id="cb66a-111">*ppRow*</span><span class="sxs-lookup"><span data-stu-id="cb66a-111">*ppRow*</span></span>

  - <span data-ttu-id="cb66a-112">指向 OLE DB **Row** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="cb66a-112">Pointer to an OLE DB **Row** object.</span></span>

  - <span data-ttu-id="cb66a-113">*PRow*</span><span class="sxs-lookup"><span data-stu-id="cb66a-113">*PRow*</span></span>

  - <span data-ttu-id="cb66a-114">一个 OLE DB **Row** 对象。</span><span class="sxs-lookup"><span data-stu-id="cb66a-114">An OLE DB **Row** object.</span></span>

## <a name="return-values"></a><span data-ttu-id="cb66a-115">返回值</span><span class="sxs-lookup"><span data-stu-id="cb66a-115">Return Values</span></span>

<span data-ttu-id="cb66a-116">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="cb66a-116">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="cb66a-117">应用于</span><span class="sxs-lookup"><span data-stu-id="cb66a-117">Applies To</span></span>

[<span data-ttu-id="cb66a-118">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="cb66a-118">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

