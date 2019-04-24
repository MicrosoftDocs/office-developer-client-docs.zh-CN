---
title: 章节属性 (ADO)
TOCTitle: Chapter property (ADO)
ms:assetid: d7c9478e-487f-7023-1dd8-5313433dbc5e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250085(v=office.15)
ms:contentKeyID: 48548014
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b4f4efc2ffab9f7996b2d805658b985badbaf87e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296393"
---
# <a name="chapter-property-ado"></a><span data-ttu-id="c7c82-102">章节属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="c7c82-102">Chapter property (ADO)</span></span>

<span data-ttu-id="c7c82-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7c82-103">**Applies to**: Access 2013, Office 2013</span></span>
 
<span data-ttu-id="c7c82-104">从 **ADORecordsetConstruction** 对象获取（或对它设置）OLE DB **Chapter** 对象。</span><span class="sxs-lookup"><span data-stu-id="c7c82-104">Gets or sets an OLE DB **Chapter** object from/on an **ADORecordsetConstruction** object.</span></span> <span data-ttu-id="c7c82-105">当您使用 **"\_放置章节**" 设置**章节**对象时, 会将行的子集转换为 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="c7c82-105">When you use **put\_Chapter** to set the **Chapter** object, a subset of rows is turned into an ADO **Recordset** object.</span></span> <span data-ttu-id="c7c82-106">这将设置**行集**对象的当前章节。</span><span class="sxs-lookup"><span data-stu-id="c7c82-106">This sets the current chapter of the **Rowset** object.</span></span> <span data-ttu-id="c7c82-107">读/写。</span><span class="sxs-lookup"><span data-stu-id="c7c82-107">Read/write.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7c82-108">语法</span><span class="sxs-lookup"><span data-stu-id="c7c82-108">Syntax</span></span>

<span data-ttu-id="c7c82-109">HRESULT get\_章节 (\[out, retval\] long\* plChapter);</span><span class="sxs-lookup"><span data-stu-id="c7c82-109">HRESULT get\_Chapter(\[out, retval\] long\* plChapter);</span></span>

<span data-ttu-id="c7c82-110">HRESULT put\_章 (\[\] long lChapter);</span><span class="sxs-lookup"><span data-stu-id="c7c82-110">HRESULT put\_Chapter(\[in\] long lChapter);</span></span>

## <a name="parameters"></a><span data-ttu-id="c7c82-111">参数</span><span class="sxs-lookup"><span data-stu-id="c7c82-111">Parameters</span></span>

|<span data-ttu-id="c7c82-112">参数</span><span class="sxs-lookup"><span data-stu-id="c7c82-112">Parameter</span></span>|<span data-ttu-id="c7c82-113">描述</span><span class="sxs-lookup"><span data-stu-id="c7c82-113">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="c7c82-114">*plChapter*</span><span class="sxs-lookup"><span data-stu-id="c7c82-114">*plChapter*</span></span> |<span data-ttu-id="c7c82-115">指向子集的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="c7c82-115">Pointer to the handle of a chapter.</span></span>|
|<span data-ttu-id="c7c82-116">*LChapter*</span><span class="sxs-lookup"><span data-stu-id="c7c82-116">*LChapter*</span></span> |<span data-ttu-id="c7c82-117">子集的句柄。</span><span class="sxs-lookup"><span data-stu-id="c7c82-117">Handle of a chapter.</span></span>|

## <a name="return-values"></a><span data-ttu-id="c7c82-118">返回值</span><span class="sxs-lookup"><span data-stu-id="c7c82-118">Return values</span></span>

<span data-ttu-id="c7c82-119">此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。</span><span class="sxs-lookup"><span data-stu-id="c7c82-119">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="c7c82-120">应用于</span><span class="sxs-lookup"><span data-stu-id="c7c82-120">Applies To</span></span>

[<span data-ttu-id="c7c82-121">ADORecordsetConstruction</span><span class="sxs-lookup"><span data-stu-id="c7c82-121">ADORecordsetConstruction</span></span>](adorecordsetconstruction-interface-ado.md)

