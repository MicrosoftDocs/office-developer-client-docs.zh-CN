---
title: FetchProgress 事件 (ADO)
TOCTitle: FetchProgress event (ADO)
ms:assetid: 09145d9a-ea5e-b41c-6c54-33ec83e642a9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248828(v=office.15)
ms:contentKeyID: 48543114
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d863f51e7836acdc577ecd720df77114ed66f067
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293180"
---
# <a name="fetchprogress-event-ado"></a><span data-ttu-id="d7c65-102">FetchProgress 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d7c65-102">FetchProgress event (ADO)</span></span>

<span data-ttu-id="d7c65-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d7c65-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d7c65-104">**FetchProgress** 事件在持续时间很长的异步操作中定期调用，以报告当前又另外将多少行检索到了 [Recordset](recordset-object-ado.md) 中。</span><span class="sxs-lookup"><span data-stu-id="d7c65-104">The **FetchProgress** event is called periodically during a lengthy asynchronous operation to report how many more rows have currently been retrieved into the [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="d7c65-105">语法</span><span class="sxs-lookup"><span data-stu-id="d7c65-105">Syntax</span></span>

<span data-ttu-id="d7c65-106">FetchProgress*进度*、 *MaxProgress*、 *adStatus*、 *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="d7c65-106">FetchProgress*Progress*, *MaxProgress*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="d7c65-107">参数</span><span class="sxs-lookup"><span data-stu-id="d7c65-107">Parameters</span></span>

|<span data-ttu-id="d7c65-108">参数</span><span class="sxs-lookup"><span data-stu-id="d7c65-108">Parameter</span></span>|<span data-ttu-id="d7c65-109">描述</span><span class="sxs-lookup"><span data-stu-id="d7c65-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="d7c65-110">*Progress*</span><span class="sxs-lookup"><span data-stu-id="d7c65-110">*Progress*</span></span> |<span data-ttu-id="d7c65-111">**长整型** 值，指示提取操作当前检索的记录数。</span><span class="sxs-lookup"><span data-stu-id="d7c65-111">A **Long** value indicating the number of records that have currently been retrieved by the fetch operation.</span></span>|
|<span data-ttu-id="d7c65-112">*MaxProgress*</span><span class="sxs-lookup"><span data-stu-id="d7c65-112">*MaxProgress*</span></span> |<span data-ttu-id="d7c65-113">**长整型** 值，指示预期检索到的最多记录数。</span><span class="sxs-lookup"><span data-stu-id="d7c65-113">A **Long** value indicating the maximum number of records expected to be retrieved.</span></span>|
|<span data-ttu-id="d7c65-114">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="d7c65-114">*adStatus*</span></span> |<span data-ttu-id="d7c65-115">[EventStatusEnum](eventstatusenum.md) 状态值。</span><span class="sxs-lookup"><span data-stu-id="d7c65-115">An [EventStatusEnum](eventstatusenum.md) status value.</span></span>|
|<span data-ttu-id="d7c65-116">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="d7c65-116">*pRecordset*</span></span> |<span data-ttu-id="d7c65-117">**Recordset** 对象，即要为其检索记录的对象。</span><span class="sxs-lookup"><span data-stu-id="d7c65-117">A **Recordset** object that is the object for which the records are being retrieved.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d7c65-118">注解</span><span class="sxs-lookup"><span data-stu-id="d7c65-118">Remarks</span></span>

<span data-ttu-id="d7c65-p101">将 **FetchProgress** 用于子 **Recordset** 时，请注意 *Progress* 和 *MaxProgress* 参数值是从基础 [Cursor Service](microsoft-cursor-service-for-ole-db-ado-service-component.md) 行集派生的。返回的值代表基础行集中的记录总数，而不仅仅是当前章节中的记录数。</span><span class="sxs-lookup"><span data-stu-id="d7c65-p101">When using **FetchProgress** with a child **Recordset**, be aware that the *Progress* and *MaxProgress* parameter values are derived from the underlying [Cursor Service](microsoft-cursor-service-for-ole-db-ado-service-component.md) rowset. The values returned represent the total number of records in the underlying rowset, not just the number of records in the current chapter.</span></span>

> [!NOTE]
> <span data-ttu-id="d7c65-121">[!注释] 若要在 Microsoft Visual Basic 中使用 **FetchProgress** ，需要 Visual Basic 6.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d7c65-121">To use **FetchProgress** with Microsoft Visual Basic, Visual Basic 6.0 or later is required.</span></span>


