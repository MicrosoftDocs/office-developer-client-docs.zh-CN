---
title: Rowset 属性 (ADO)
TOCTitle: Rowset Property (ADO)
ms:assetid: 1a1cb3ef-8f3c-30c1-3eb0-8618fdcacd53
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248946(v=office.15)
ms:contentKeyID: 48543515
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 95a33fb3d24e5cdbf608d268781be0dd536fa315
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467237"
---
# <a name="rowset-property-ado"></a><span data-ttu-id="5592c-102">Rowset 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="5592c-102">Rowset Property (ADO)</span></span>


<span data-ttu-id="5592c-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5592c-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="5592c-104">通过 **ADORecordsetConstruction** 对象获取或设置一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="5592c-104">Gets or sets an OLE DB **Rowset** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="5592c-105">当您使用 put\_行集，行集转换为 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="5592c-105">When you use put\_Rowset, the rowset is turned into an ADO **Recordset** object.</span></span>

<span data-ttu-id="5592c-106">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="5592c-106">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="5592c-107">语法</span><span class="sxs-lookup"><span data-stu-id="5592c-107">Syntax</span></span>

<span data-ttu-id="5592c-108">HRESULT get\_行集 (\[out，retval\] IUnknown\* \* ppRowset);</span><span class="sxs-lookup"><span data-stu-id="5592c-108">HRESULT get\_Rowset(\[out, retval\] IUnknown\*\* ppRowset);</span></span>

<span data-ttu-id="5592c-109">HRESULT 放置\_行集 (\[的\]IUnknown\* pRowset);</span><span class="sxs-lookup"><span data-stu-id="5592c-109">HRESULT put\_Rowset(\[in\] IUnknown\* pRowset);</span></span>

## <a name="parameters"></a><span data-ttu-id="5592c-110">参数</span><span class="sxs-lookup"><span data-stu-id="5592c-110">Parameters</span></span>

  - <span data-ttu-id="5592c-111">*ppRowset*</span><span class="sxs-lookup"><span data-stu-id="5592c-111">*ppRowset*</span></span>

  - <span data-ttu-id="5592c-112">指向 OLE DB **Rowset** 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="5592c-112">Pointer to an OLE DB **Rowset** object.</span></span>

  - <span data-ttu-id="5592c-113">*PRowset*</span><span class="sxs-lookup"><span data-stu-id="5592c-113">*PRowset*</span></span>

  - <span data-ttu-id="5592c-114">一个 OLE DB **Rowset** 对象。</span><span class="sxs-lookup"><span data-stu-id="5592c-114">An OLE DB **Rowset** object.</span></span>

## <a name="return-values"></a><span data-ttu-id="5592c-115">返回值</span><span class="sxs-lookup"><span data-stu-id="5592c-115">Return Values</span></span>

<span data-ttu-id="5592c-116">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="5592c-116">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="5592c-117">应用于</span><span class="sxs-lookup"><span data-stu-id="5592c-117">Applies To</span></span>

[<span data-ttu-id="5592c-118">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="5592c-118">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

