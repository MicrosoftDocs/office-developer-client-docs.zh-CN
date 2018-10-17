---
title: FetchComplete 事件 (ADO)
TOCTitle: FetchComplete Event (ADO)
ms:assetid: 4863d5b5-7d77-bdef-c511-f85c9e6dec9d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249224(v=office.15)
ms:contentKeyID: 48544621
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 299fec4a831bbde5d3fd2d58e0f76edb2acea0f8
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467598"
---
# <a name="fetchcomplete-event-ado"></a><span data-ttu-id="286ca-102">FetchComplete 事件 (ADO)</span><span class="sxs-lookup"><span data-stu-id="286ca-102">FetchComplete Event (ADO)</span></span>


<span data-ttu-id="286ca-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="286ca-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="286ca-104">**FetchComplete** 事件在持续时间很长的异步操作中的所有记录都已检索到 [Recordset](recordset-object-ado.md) 中之后发生。</span><span class="sxs-lookup"><span data-stu-id="286ca-104">The **FetchComplete** event is called after all the records in a lengthy asynchronous operation have been retrieved into the [Recordset](recordset-object-ado.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="286ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="286ca-105">Syntax</span></span>

<span data-ttu-id="286ca-106">FetchComplete*pError*， *adStatus* *pRecordset*</span><span class="sxs-lookup"><span data-stu-id="286ca-106">FetchComplete*pError*, *adStatus*, *pRecordset*</span></span>

## <a name="parameters"></a><span data-ttu-id="286ca-107">参数</span><span class="sxs-lookup"><span data-stu-id="286ca-107">Parameters</span></span>

  - <span data-ttu-id="286ca-108">*pError*</span><span class="sxs-lookup"><span data-stu-id="286ca-108">*pError*</span></span>

  - <span data-ttu-id="286ca-p101">[Error](error-object-ado.md) 对象。如果 **adStatus** 的值为 **adStatusErrorsOccurred** ，则此参数描述所发生的错误，否则不设置此参数。</span><span class="sxs-lookup"><span data-stu-id="286ca-p101">An [Error](error-object-ado.md) object. It describes the error that occurred if the value of **adStatus** is **adStatusErrorsOccurred**; otherwise it is not set.</span></span>

  - <span data-ttu-id="286ca-111">*adStatus*</span><span class="sxs-lookup"><span data-stu-id="286ca-111">*adStatus*</span></span>

  - [<span data-ttu-id="286ca-112">EventStatusEnum</span><span class="sxs-lookup"><span data-stu-id="286ca-112">EventStatusEnum</span></span>](eventstatusenum.md)
    
    <span data-ttu-id="286ca-113">在此事件返回之前，将该参数设置为 **adStatusUnwantedEvent** 可以阻止随后进行通知。</span><span class="sxs-lookup"><span data-stu-id="286ca-113">Before this event returns, set this parameter to **adStatusUnwantedEvent** to prevent subsequent notifications.</span></span>

  - <span data-ttu-id="286ca-114">*pRecordset*</span><span class="sxs-lookup"><span data-stu-id="286ca-114">*pRecordset*</span></span>

  - <span data-ttu-id="286ca-p102">**Recordset** 对象。为其检索记录的对象。</span><span class="sxs-lookup"><span data-stu-id="286ca-p102">A **Recordset** object. The object for which the records were retrieved.</span></span>

## <a name="remarks"></a><span data-ttu-id="286ca-117">备注</span><span class="sxs-lookup"><span data-stu-id="286ca-117">Remarks</span></span>

<span data-ttu-id="286ca-118">若要在 Microsoft Visual Basic 中使用 **FetchComplete** ，需要 Visual Basic 6.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="286ca-118">To use **FetchComplete** with Microsoft Visual Basic, Visual Basic 6.0 or later is required.</span></span>
