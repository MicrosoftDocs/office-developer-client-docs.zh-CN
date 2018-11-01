---
title: Cancel 方法 (RDS)
TOCTitle: Cancel Method (RDS)
ms:assetid: 08f667c2-7a3f-c2e7-7bdf-3eb533defa33
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248827(v=office.15)
ms:contentKeyID: 48543109
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8455496e8d426d26f56b902d9a089d236bde1a6a
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868742"
---
# <a name="cancel-method-rds"></a><span data-ttu-id="cab68-102">Cancel 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="cab68-102">Cancel Method (RDS)</span></span>


<span data-ttu-id="cab68-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cab68-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cab68-104">用于取消执行挂起的异步方法调用。</span><span class="sxs-lookup"><span data-stu-id="cab68-104">Cancels execution of a pending, asynchronous method call.</span></span>

## <a name="syntax"></a><span data-ttu-id="cab68-105">语法</span><span class="sxs-lookup"><span data-stu-id="cab68-105">Syntax</span></span>

<span data-ttu-id="cab68-106">*RDS*。</span><span class="sxs-lookup"><span data-stu-id="cab68-106">*RDS*.</span></span> <span data-ttu-id="cab68-107">*DataControl*。取消</span><span class="sxs-lookup"><span data-stu-id="cab68-107">*DataControl*.Cancel</span></span>

## <a name="remarks"></a><span data-ttu-id="cab68-108">备注</span><span class="sxs-lookup"><span data-stu-id="cab68-108">Remarks</span></span>

<span data-ttu-id="cab68-109">当调用 **Cancel** 时， [ReadyState](readystate-property-rds.md) 会自动设置为 **adcReadyStateLoaded** ，并且 [Recordset](recordset-object-ado.md) 将为空。</span><span class="sxs-lookup"><span data-stu-id="cab68-109">When you call **Cancel**, [ReadyState](readystate-property-rds.md) is automatically set to **adcReadyStateLoaded**, and the [Recordset](recordset-object-ado.md) will be empty.</span></span>

