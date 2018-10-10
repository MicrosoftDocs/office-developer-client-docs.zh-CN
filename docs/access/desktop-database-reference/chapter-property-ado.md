---
title: Chapter 属性 (ADO)
TOCTitle: Chapter Property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f02b20aef2b76ff00ce23b8597132dc22b414993
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468099"
---
# <a name="chapter-property-ado"></a><span data-ttu-id="3a163-102">Chapter 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="3a163-102">Chapter Property (ADO)</span></span>


<span data-ttu-id="3a163-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="3a163-103">**Applies to**: Access 2013 | Office 2013</span></span>
 

<span data-ttu-id="3a163-104">从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。</span><span class="sxs-lookup"><span data-stu-id="3a163-104">Gets or sets an OLE DB **Chapter** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="3a163-105">当您使用**放置\_章**设置**Chapter**对象，行的子集处于到 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="3a163-105">When you use **put\_Chapter** to set the **Chapter** object, a subset of rows is turned into an ADO **Recordset** object.</span></span> <span data-ttu-id="3a163-106">这将设置**Rowset**对象的当前一章。</span><span class="sxs-lookup"><span data-stu-id="3a163-106">This sets the current chapter of the **Rowset** object.</span></span> <span data-ttu-id="3a163-107">为可读/写属性。</span><span class="sxs-lookup"><span data-stu-id="3a163-107">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="3a163-108">语法</span><span class="sxs-lookup"><span data-stu-id="3a163-108">Syntax</span></span>

<span data-ttu-id="3a163-109">HRESULT get\_章 (\[out，retval\]长\*plChapter);</span><span class="sxs-lookup"><span data-stu-id="3a163-109">HRESULT get\_Chapter(\[out, retval\] long\* plChapter);</span></span>

<span data-ttu-id="3a163-110">HRESULT 放置\_章 (\[的\]长 lChapter);</span><span class="sxs-lookup"><span data-stu-id="3a163-110">HRESULT put\_Chapter(\[in\] long lChapter);</span></span>

## <a name="parameters"></a><span data-ttu-id="3a163-111">参数</span><span class="sxs-lookup"><span data-stu-id="3a163-111">Parameters</span></span>

  - <span data-ttu-id="3a163-112">*plChapter*</span><span class="sxs-lookup"><span data-stu-id="3a163-112">*plChapter*</span></span>

  - <span data-ttu-id="3a163-113">指向子集的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="3a163-113">Pointer to the handle of a chapter.</span></span>

  - <span data-ttu-id="3a163-114">*LChapter*</span><span class="sxs-lookup"><span data-stu-id="3a163-114">*LChapter*</span></span>

  - <span data-ttu-id="3a163-115">子集的句柄。</span><span class="sxs-lookup"><span data-stu-id="3a163-115">Handle of a chapter.</span></span>

## <a name="return-values"></a><span data-ttu-id="3a163-116">返回值</span><span class="sxs-lookup"><span data-stu-id="3a163-116">Return Values</span></span>

<span data-ttu-id="3a163-117">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="3a163-117">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="3a163-118">应用于</span><span class="sxs-lookup"><span data-stu-id="3a163-118">Applies To</span></span>

[<span data-ttu-id="3a163-119">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="3a163-119">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

