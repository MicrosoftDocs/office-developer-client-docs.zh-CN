---
title: onError 事件 (RDS)
TOCTitle: onError event (RDS)
ms:assetid: e26a3f7f-0f00-919a-65ad-bf39ffb83e92
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250153(v=office.15)
ms:contentKeyID: 48548292
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9fc51522d143306d9625cdc07251edfe1dddf22d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712174"
---
# <a name="onerror-event-rds"></a><span data-ttu-id="dcc90-102">onError 事件 (RDS)</span><span class="sxs-lookup"><span data-stu-id="dcc90-102">onError event (RDS)</span></span>

<span data-ttu-id="dcc90-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="dcc90-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dcc90-104">只要在操作期间发生错误，便会调用 **onError** 事件。</span><span class="sxs-lookup"><span data-stu-id="dcc90-104">The **onError** event is called whenever an error occurs during an operation.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcc90-105">语法</span><span class="sxs-lookup"><span data-stu-id="dcc90-105">Syntax</span></span>

<span data-ttu-id="dcc90-106">onError*SCode*，*说明*，*源*， *CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="dcc90-106">onError*SCode*, *Description*, *Source*, *CancelDisplay*</span></span>

## <a name="parameters"></a><span data-ttu-id="dcc90-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="dcc90-107">Parameters</span></span>

|<span data-ttu-id="dcc90-108">参数</span><span class="sxs-lookup"><span data-stu-id="dcc90-108">Parameter</span></span>|<span data-ttu-id="dcc90-109">说明</span><span class="sxs-lookup"><span data-stu-id="dcc90-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="dcc90-110">*SCode*</span><span class="sxs-lookup"><span data-stu-id="dcc90-110">*SCode*</span></span> |<span data-ttu-id="dcc90-111">指示错误的状态代码的整数。</span><span class="sxs-lookup"><span data-stu-id="dcc90-111">An integer that indicates the status code of the error.</span></span>|
|<span data-ttu-id="dcc90-112">*Description*</span><span class="sxs-lookup"><span data-stu-id="dcc90-112">*Description*</span></span> |<span data-ttu-id="dcc90-113">**字符串型** ，指示错误的说明。</span><span class="sxs-lookup"><span data-stu-id="dcc90-113">A **String** that indicates a description of the error.</span></span>|
|<span data-ttu-id="dcc90-114">*Source*</span><span class="sxs-lookup"><span data-stu-id="dcc90-114">*Source*</span></span> |<span data-ttu-id="dcc90-115">**字符串型** ，指示导致错误的查询或命令。</span><span class="sxs-lookup"><span data-stu-id="dcc90-115">A **String** that indicates the query or command that caused the error.</span></span>|
|<span data-ttu-id="dcc90-116">*CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="dcc90-116">*CancelDisplay*</span></span> |<span data-ttu-id="dcc90-117">**Boolean** 值，如果设置为 **True** ，则禁止在对话框中显示错误。</span><span class="sxs-lookup"><span data-stu-id="dcc90-117">A **Boolean** value, which if set to **True**, that prevents the error from being displayed in a dialog box.</span></span>|

