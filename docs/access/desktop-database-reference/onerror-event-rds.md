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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288474"
---
# <a name="onerror-event-rds"></a><span data-ttu-id="60446-102">onError 事件 (RDS)</span><span class="sxs-lookup"><span data-stu-id="60446-102">onError event (RDS)</span></span>

<span data-ttu-id="60446-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="60446-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="60446-104">只要在操作期间发生错误，便会调用 **onError** 事件。</span><span class="sxs-lookup"><span data-stu-id="60446-104">The **onError** event is called whenever an error occurs during an operation.</span></span>

## <a name="syntax"></a><span data-ttu-id="60446-105">语法</span><span class="sxs-lookup"><span data-stu-id="60446-105">Syntax</span></span>

<span data-ttu-id="60446-106">onError*SCode*、 *Description*、 *Source*、 *CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="60446-106">onError*SCode*, *Description*, *Source*, *CancelDisplay*</span></span>

## <a name="parameters"></a><span data-ttu-id="60446-107">参数</span><span class="sxs-lookup"><span data-stu-id="60446-107">Parameters</span></span>

|<span data-ttu-id="60446-108">参数</span><span class="sxs-lookup"><span data-stu-id="60446-108">Parameter</span></span>|<span data-ttu-id="60446-109">描述</span><span class="sxs-lookup"><span data-stu-id="60446-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="60446-110">*SCode*</span><span class="sxs-lookup"><span data-stu-id="60446-110">*SCode*</span></span> |<span data-ttu-id="60446-111">指示错误的状态代码的整数。</span><span class="sxs-lookup"><span data-stu-id="60446-111">An integer that indicates the status code of the error.</span></span>|
|<span data-ttu-id="60446-112">*Description*</span><span class="sxs-lookup"><span data-stu-id="60446-112">*Description*</span></span> |<span data-ttu-id="60446-113">**字符串型** ，指示错误的说明。</span><span class="sxs-lookup"><span data-stu-id="60446-113">A **String** that indicates a description of the error.</span></span>|
|<span data-ttu-id="60446-114">*Source*</span><span class="sxs-lookup"><span data-stu-id="60446-114">*Source*</span></span> |<span data-ttu-id="60446-115">**字符串型** ，指示导致错误的查询或命令。</span><span class="sxs-lookup"><span data-stu-id="60446-115">A **String** that indicates the query or command that caused the error.</span></span>|
|<span data-ttu-id="60446-116">*CancelDisplay*</span><span class="sxs-lookup"><span data-stu-id="60446-116">*CancelDisplay*</span></span> |<span data-ttu-id="60446-117">**Boolean** 值，如果设置为 **True** ，则禁止在对话框中显示错误。</span><span class="sxs-lookup"><span data-stu-id="60446-117">A **Boolean** value, which if set to **True**, that prevents the error from being displayed in a dialog box.</span></span>|

