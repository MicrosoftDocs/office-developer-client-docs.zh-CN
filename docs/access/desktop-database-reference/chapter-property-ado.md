---
title: Chapter 属性 (ADO)
TOCTitle: Chapter property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3d7523a930feed7431bf8be0bbb7222a4b305483
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949395"
---
# <a name="chapter-property-ado"></a><span data-ttu-id="2bbf5-102">Chapter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="2bbf5-102">Chapter property (ADO)</span></span>

<span data-ttu-id="2bbf5-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2bbf5-103">**Applies to**: Access 2013, Office 2013</span></span>
 
<span data-ttu-id="2bbf5-104">从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-104">Gets or sets an OLE DB **Chapter** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="2bbf5-105">当您使用**放置\_章**设置**Chapter**对象，行的子集处于到 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-105">When you use **put\_Chapter** to set the **Chapter** object, a subset of rows is turned into an ADO **Recordset** object.</span></span> <span data-ttu-id="2bbf5-106">这将设置**Rowset**对象的当前一章。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-106">This sets the current chapter of the **Rowset** object.</span></span> <span data-ttu-id="2bbf5-107">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-107">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bbf5-108">语法</span><span class="sxs-lookup"><span data-stu-id="2bbf5-108">Syntax</span></span>

<span data-ttu-id="2bbf5-109">HRESULT get\_章 (\[out，retval\]长\*plChapter);</span><span class="sxs-lookup"><span data-stu-id="2bbf5-109">HRESULT get\_Chapter(\[out, retval\] long\* plChapter);</span></span>

<span data-ttu-id="2bbf5-110">HRESULT 放置\_章 (\[的\]长 lChapter);</span><span class="sxs-lookup"><span data-stu-id="2bbf5-110">HRESULT put\_Chapter(\[in\] long lChapter);</span></span>

## <a name="parameters"></a><span data-ttu-id="2bbf5-111">参数</span><span class="sxs-lookup"><span data-stu-id="2bbf5-111">Parameters</span></span>

|<span data-ttu-id="2bbf5-112">参数</span><span class="sxs-lookup"><span data-stu-id="2bbf5-112">Parameter</span></span>|<span data-ttu-id="2bbf5-113">说明</span><span class="sxs-lookup"><span data-stu-id="2bbf5-113">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="2bbf5-114">*plChapter*</span><span class="sxs-lookup"><span data-stu-id="2bbf5-114">*plChapter*</span></span> |<span data-ttu-id="2bbf5-115">指向子集的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-115">Pointer to the handle of a chapter.</span></span>|
|<span data-ttu-id="2bbf5-116">*LChapter*</span><span class="sxs-lookup"><span data-stu-id="2bbf5-116">*LChapter*</span></span> |<span data-ttu-id="2bbf5-117">子集的句柄。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-117">Handle of a chapter.</span></span>|

## <a name="return-values"></a><span data-ttu-id="2bbf5-118">返回值</span><span class="sxs-lookup"><span data-stu-id="2bbf5-118">Return values</span></span>

<span data-ttu-id="2bbf5-119">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="2bbf5-119">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="2bbf5-120">应用于</span><span class="sxs-lookup"><span data-stu-id="2bbf5-120">Applies To</span></span>

[<span data-ttu-id="2bbf5-121">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="2bbf5-121">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

