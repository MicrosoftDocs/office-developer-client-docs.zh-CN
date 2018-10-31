---
title: FetchProgress 事件 (ADO)
TOCTitle: FetchProgress Event (ADO)
ms:assetid: 09145d9a-ea5e-b41c-6c54-33ec83e642a9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248828(v=office.15)
ms:contentKeyID: 48543114
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a898ad02d551e0c4de02597761ccd3076fc5eb77
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862275"
---
# <a name="fetchprogress-event-ado"></a><span data-ttu-id="7016a-102">FetchProgress 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="7016a-102">FetchProgress Event (ADO)</span></span>


<span data-ttu-id="7016a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="7016a-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="7016a-104">**FetchProgress** 事件在持续时间很长的异步操作中定期调用，以报告当前又另外将多少行检索到了 [Recordset](recordset-object-ado.md) 中。</span><span class="sxs-lookup"><span data-stu-id="7016a-104">The **FetchProgress** event is called periodically during a lengthy asynchronous operation to report how many more rows have currently been retrieved into the [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="7016a-105">语法</span><span class="sxs-lookup"><span data-stu-id="7016a-105">Syntax</span></span>

<span data-ttu-id="7016a-106">FetchProgress*进度*， *MaxProgress*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="7016a-106">FetchProgress*Progress*, *MaxProgress*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="7016a-107">参数</span><span class="sxs-lookup"><span data-stu-id="7016a-107">Parameters</span></span>

  - <span data-ttu-id="7016a-108">*Progress*</span><span class="sxs-lookup"><span data-stu-id="7016a-108">*Progress*</span></span>

  - <span data-ttu-id="7016a-109">**长整型** 值，指示提取操作当前检索的记录数。</span><span class="sxs-lookup"><span data-stu-id="7016a-109">A **Long** value indicating the number of records that have currently been retrieved by the fetch operation.</span></span>

  - <span data-ttu-id="7016a-110">*MaxProgress*</span><span class="sxs-lookup"><span data-stu-id="7016a-110">*MaxProgress*</span></span>

  - <span data-ttu-id="7016a-111">**长整型** 值，指示预期检索到的最多记录数。</span><span class="sxs-lookup"><span data-stu-id="7016a-111">A **Long** value indicating the maximum number of records expected to be retrieved.</span></span>

  - <span data-ttu-id="7016a-112">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="7016a-112">*adStatus*</span></span>

  - <span data-ttu-id="7016a-113">[EventStatusEnum](eventstatusenum.md) 状态值。</span><span class="sxs-lookup"><span data-stu-id="7016a-113">An [EventStatusEnum](eventstatusenum.md) status value.</span></span>

  - <span data-ttu-id="7016a-114">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="7016a-114">*pRecordset*</span></span>

  - <span data-ttu-id="7016a-115">**Recordset** 对象，即要为其检索记录的对象。</span><span class="sxs-lookup"><span data-stu-id="7016a-115">A **Recordset** object that is the object for which the records are being retrieved.</span></span>

## <a name="remarks"></a><span data-ttu-id="7016a-116">说明</span><span class="sxs-lookup"><span data-stu-id="7016a-116">Remarks</span></span>

<span data-ttu-id="7016a-117">当子**Recordset**中使用**FetchProgress** ，都可以识别的*进度*和*MaxProgress*参数值派生基础[Cursor Service](microsoft-cursor-service-for-ole-db-ado-service-component.md)行集。</span><span class="sxs-lookup"><span data-stu-id="7016a-117">When using **FetchProgress** with a child **Recordset**, be aware that the *Progress* and *MaxProgress* parameter values are derived from the underlying [Cursor Service](microsoft-cursor-service-for-ole-db-ado-service-component.md) rowset.</span></span> <span data-ttu-id="7016a-118">返回的值代表基础行集中的记录总数，而不仅仅是当前章节中的记录数。</span><span class="sxs-lookup"><span data-stu-id="7016a-118">The values returned represent the total number of records in the underlying rowset, not just the number of records in the current chapter.</span></span>


> [!NOTE]
> <span data-ttu-id="7016a-119">[!注释] 若要在 Microsoft Visual Basic 中使用 **FetchProgress** ，需要 Visual Basic 6.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7016a-119">To use **FetchProgress** with Microsoft Visual Basic, Visual Basic 6.0 or later is required.</span></span>


